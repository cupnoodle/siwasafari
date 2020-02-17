---
layout: post
title:  "Always getting invalid_client when trying to authorize token..."
date:   2020-02-17 18:36:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/thread/122648)

## Pain

**Always getting invalid_client** (title)

**I always getting an error** when i try to hit the endpoint `/auth/token`
 
For info i followed the great tutorial from Aaron Parecki: https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple
 
At least he is here to explain to us how we can implement YOUR system................. (Apple doesn't have good documentation on how to implement Sign in with Apple)
 
Now, my client_id is `com.xxx.xxx`, my team id is 10 characters string that I copy/paste from the web interface...
 
So please, help us finally integrate YOUR system......... (referring to Apple's sign in system)

----
&nbsp;  
(Other commenters)

**I'm actually doing the same exact thing, and getting the same error**. Good point on bundle id vs secret id.
I firgured that if you don't support Sign In with Apple on web or Android, you don't even need service id, since ASAuthorization uses bundle id. You also don't need to worry about whitelisting domains and uploading txt files, am I right?
 
**I am still experiencing the same invalid_token error though**. My JWK has the right info, my key ID is correct, I am using a file I downloaded from Apple. **I wish there was a debugging tool or some more explicit error code**_

---
&nbsp;  
  
**I hope you've had progress since this is a few weeks old now, but in case others are hitting this same problem, as I was**, and finding this unanswered question, here are my findings so far...
 
If you do this and get either `invalid_grant` or a success response, you've made progress. `invalid_grant` seems to be the next error in the chain, and is raised after client validation is passed.

&nbsp;

## Keywords
- token
- invalid_client
- Bundle id
- whitelisting
- JWK (Json Web Key)

&nbsp;  

## Recommendation

I followed the great tutorial from Aaron Parecki: https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple

----
&nbsp;  

The blog post you reference is really useful for getting started, **however it's written from the point of view of implementing the Sign In With Apple button on the web, not in your iOS app**. From your post, I think you're doing the same as me, and trying to authorise a user on your own servers by hitting the `auth/token` endpoint.
 
In this case, the `ASAuthorization` framework in your app will be making a token using your app's Bundle ID, not your services ID, and your client secret has to match that.
 
The fix for this is to generate a second client secret, using the same script and settings as per Aaron's blog post, except with your app's Bundle ID in the `sub` field of the settings. Then, when you're submitting an `authorization_code`, make sure you use the correct `client_id` in the request body, and the `client_secret` which matches that ID.

&nbsp;
## Worldview
Apple should prepare adequate documentation for developer to implement's Apple feature. 

Error message should be useful, which guide developer on how to fix what is wrong.