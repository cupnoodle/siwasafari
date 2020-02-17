---
layout: post
title:  "however, I now get a 'invalid_grant'."
date:   2020-02-18 02:22:16 +0800
categories: siwa
---


Source: [Comments in this tutorial](https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple)

## Pain

- Have you finally managed to find a workaround for this confusing apple sign in flow?

----
&nbsp;

- So far this post helped me so much, however, I now get a "invalid_grant". Following : https://developer.apple.com... I understand that I have absolutely no idea about what's this error about :O

- Does anyone have this issue? I am not that familiar with Apple and I have no idea in which direction should I go to track that bug down..

---
&nbsp;
- Hi, Max. Did you end up figuring out what caused "invalid_grant"? I'm implementing Sign in with Apple right now and that's the response I'm getting when trying to validate the authorization token.

----
&nbsp;

- How to decode 'id_token' from apple, that contains useful payload? I have just private key with extension .p8 (downloaded from dev page).

---
&nbsp;
- I'm implementing 'Sign in with Apple'. How do I use my own app icon on the "Sign in with Apple" consent page instead of displaying a placeholder gray logo?

---
&nbsp;

- In case anyone else runs into this, I'll share.... Basically Apple's configuration site lets you input redirect uri's without a scheme. I put in `blah.com/callback` which it allowed. Then I had to use `blah.com/callback` as the redirect_uri which _sort of_ worked but eventually failed with a HTTP 500 error. After I went back and reconfigured my urls to be `https://blah.com/callback` I could start using that as the redirect_uri and things started working.

- tl;dr need to use full uri with scheme in the apple configuration portal otherwise things will fail silently with no good errors :(

---
&nbsp;

What is the best practice to develop, or to make automatic test?  (How to test locally)
For instance, facebook allows localhost for developpers.

&nbsp;  

## Keywords
-Sign in With Apple
-Token
-id_token
-client_secret
-payload
-.p8 key
-redirect_uri
-scope
-headers



&nbsp;  

## Recommendation

 - `name email` is the proper scope to request, and scope is completely ignored on later sign-ins

 ----
 &nbsp;

The user email and name are returned only the first time you make the request. In the authorize request you get it back like:

{"name":{"firstName":"YourFirstName","lastName":"YourLastName"},"email":"randomstring@privaterelay.appleid.com"}

where email can be either real or fake.

The token request will also make this data available with the first request, you can access it with claims["email"] for example

Hope this helps someone!!

----
&nbsp;


&nbsp;

## Worldview

&nbsp;