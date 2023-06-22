---
author: "nullagent"
date: 2023-04-22
title: "WTF is a KDF? "
description: 'Cybersecurity dispatch from a French prison'
image: kdf-images/prison-flames.jpg
tags: ['linux', 'app', 'privacy']
categories: [
  'crypto'
]
---

Earlier this week a letter from an activist imprisoned in France was [posted to the internet](https://nantes.indymedia.org/posts/87395/une-lettre-divan-enferme-a-la-prison-de-villepinte-perquisitions-et-disques-durs-dechiffres/). Contained within Ivan Alococo’s dispatch from the Villepinte prison was [a startling revelation](https://twitter.com/rechelon/status/1648094323186241536). Police had cracked his LUKS hard drive password. A feat that once was impossible can now be accomplished in a few months by harnessing [as many as 10,000 servers](https://kolektiva.social/@cedar/110214532879538171) with modern GPUs. At the root of this breach is a cryptographic function that is showing its age, PBKDF2.

This episode is a wake up call to learn wtf is a KDF?

## What is a KDF?

In modern computing when applications provide strong file encryption they frequently use passwords to protect files. For passwords to be strong they must contain a lot of entropy and generally appear as random as possible. Obviously humans tend to use characters and phrases from their native language combined with memorable patterns or rules that help them remember these passwords.

Key derivation functions (KDFs) are tools that allow us to improve the entropy derived from the types of keys and passwords applications typically use. By performing a series of hashing and salting `PBKDF2` seasons the user's input with entropy sufficient for use in private keys for algorithms like AES and NaCl.

Many [types of KDFs exist](https://crypto.stackexchange.com/a/40767). Specialized KDFs are also used to [generate keys from Diffie-Helman](https://soatok.blog/2021/11/17/understanding-hkdf/) output and to create cryptographic random numbers.

In the case of this French prisoner they were using Linux's most popular hard drive encryption tool, LUKS, which was using a `PBKDF2` to generate AES keys. In Ubuntu 18.04 this is the default configuration. `PBKDF2` is a password based KDF designed to be resistant to CPU based attacks and dates back to 2000. It was first mentioned as an [internet standard in RFC-2898 in September 2000](https://www.rfc-editor.org/rfc/rfc2898#section-5.2).

## A startling revelation

Since the time PBKDF2 was designed, we've seen the rise of powerful GPUs become common place. To defend against this rising [onslaught of GPU hashing power](https://blog.elcomsoft.com/2020/08/breaking-luks-encryption/) is a relatively new algorithm, argon2.


{{<picture src="kdf-images/argon2-vs-pbkdf2.jpeg" type="png" alt="argon2 sneaks up on pbkdf2" caption="argon2 sneaks up on pbkdf2" class="float-right">}}


## How does Argon2 Work?

The cryptographic power of argon2 is sublte but brilliant. Instead of focusing on CPU time by requiring large numbers of hash iterations, argon2 wages war on your GPUs memory capacity. When hashing a password with argon2 an application developer can dial up the amount of RAM that is required to complete the computation. In so doing it starves the globs of highly parallel computation cores in a GPU reducing the total processing power the GPU can bring to bear.

Why does this work? On modern GPUs the exact number of threads that are active in parallel varies between models and is dependent on the amount of GPU ram required per thread. Small operations on typical GPUs may see as many as 2000 threads running in parallel. Meanwhile even the largest cloud GPUs max out around 80GB of on board memory. If argon2 is configured to use 1GB to compute password hashes then even an [NVIDIA A100](https://www.nvidia.com/en-us/data-center/a100/) would only be able to try 80 passwords in parallel instead of the orders of magnitude more cores that would be active when attacking PBKDF2 hashed passwords.

{{<picture src="kdf-images/a100.webp" type="webp" alt="Diagram of NVIDIA A100 GPU" caption="Diagram of NVIDIA A100 GPU" class="float-right">}}

## Argon2 and you . . .

If you're a developer who builds secure apps and this is your first time hearing about argon2 its probably a good time to review your code. On nodejs check for uses of crypto.pbkdf2 that should be upgraded.

If you're a Linux user, more likely than not your LUKS partitions will already using `argon2id`. You can check by running the `lsblk` command to find the name of an active partition. Then running:

`sudo cryptsetup luksDump /dev/<YOUR_PARTITION_HERE>`

If you do happen to be using an outdated algorithm you should update it! Matthew Garrett, a Linux developer, has written a great [guide to updating old LUKS partitions](https://mjg59.dreamwidth.org/66429.html).

### Is PBKDF2 broken?

On the face of it, no. PBKDF2 is not fundamentally broken. It's safe so long as the user always has [a 13 character or longer actually-random™ password](https://www.reddit.com/r/linux/comments/12q51ce/comment/jgpvsqc/?utm_source=share&utm_medium=web2x&context=3). The choice of pbkdf2 vs argon2 is of course domain and application dependant. It remains unclear exactly how authorities accessed Ivan’s hard drive.  So this is more a wake up call to use strong passwords and the best KDFs that fit the use case.

## Using argon2 in nodejs

{{<picture src="kdf-images/crypto-example.png" type="webp" alt="Example argon2 password KDF" caption="Example argon2 password KDF" class="float-right" link="https://github.com/datapartyjs/dataparty-crypto/blob/master/examples/example-password-argon2.js">}}


At the hacker collective, [dataparty](https://dataparty.xyz), we've been building a secure configuration feature that we intend to use to make a secure, decentralized database management tool. We'd recently relied upon pbkdf2 but with the news of Ivan's letter from a French prison we've taken the time to upgrade to argon2 in our nodejs codebases.

You can see how we upgraded to argon2 by [reading through this feature request](https://github.com/datapartyjs/dataparty-api/issues/71) and the [PRs referenced within](https://github.com/datapartyjs/dataparty-crypto/pull/16).

## Nodejs vs. Browser

We had some trouble getting the nodejs focused module [`argon2`](https://www.npmjs.com/package/argon2) and the browser module [`argon2-browser`](https://www.npmjs.com/package/argon2-browser) to play nice together. Sadly these libraries do not both use the same API. We made a wrapper function in [`@dataparty/crypto`](https://medium.com/r/?url=https%3A%2F%2Fgithub.com%2Fdatapartyjs%2Fdataparty-crypto) that allows you to use the same API for both modules. We've posted a complete example for nodejs usage on github:

[`dataparty-crypto/example-password-argon2.js` at master · `@dataparty/crypto`](https://github.com/datapartyjs/dataparty-crypto/blob/master/examples/example-password-argon2.js)

Meanwhile we've added an argon2 example to our [browser example](https://github.com/datapartyjs/dataparty-crypto/blob/master/examples/index.html#L98-L124).

## Support

Find this story helpful? [Buy us a coffee](https://ko-fi.com/dataparty) or give a follow:

 * https://ko-fi.com/dataparty
 * https://github.com/datapartyjs
 * https://dataparty.xyz
 * Join our discord https://discord.gg/JrYQ3f4Pxz


##

## Changes

 (23-04-2023)
 * Clarify [types of KDFs](#what-is-a-kdf)
 * Add [link to commercial LUKS cracking cloud](#a-startling-revelation)
 * Add ["Is PBKDF2 broken?"](#is-pbkdf2-broken) section
 * Add link to [HKDF explainer](#what-is-a-kdf)
##

## Mailing List
{{< rawhtml >}}
<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-071822.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{clear:left; font:14px Helvetica,Arial,sans-serif; 
    max-width: 75%;
  }
	/* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
    <form action="https://xyz.us21.list-manage.com/subscribe/post?u=7cfbc2e5276396fb5f543a2ed&amp;id=5ea825f5ee&amp;f_id=007bc2e1f0" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_self">
        <div id="mc_embed_signup_scroll"></div>
        
  <div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
    
  <div class="mc-field-group">
    <label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
  </label>
    <input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL" required>
    <span id="mce-EMAIL-HELPERTEXT" class="helper_text"></span>
  </div>

  <div id="mce-responses" class="clear foot">
    <div class="response" id="mce-error-response" style="display:none"></div>
    <div class="response" id="mce-success-response" style="display:none"></div>
  </div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->

  <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_7cfbc2e5276396fb5f543a2ed_5ea825f5ee" tabindex="-1" value=""></div>
      <div class="optionalParent">
          <div class="clear foot">
              <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
          </div>
      </div>
  </div>

</form>
</div>
<!--End mc_embed_signup-->
{{< /rawhtml >}}

