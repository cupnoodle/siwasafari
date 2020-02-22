---
layout: post
title:  "Apple Sign-In: How to use it for custom server endpoint authentication?"
date:   2020-02-22 01:04:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/message/386237#386237)

## Pain

- Given that we're being told we have to incorporate Apple Sign-In into our iOS apps (if we offer general purpose sign-in facilities), how can I do endpoint authentication with my custom server?

- **I see two alternatives, neither of which I like very much.**



- A few more details-- this problem seems difficult because:

1) The id tokens I get on iOS when the user signs in with Apple Sign In have a relatively short expiry duration (seems like 10 minutes).  

2) Apple throttles the frequency with which  you can use the refresh token (e.g., server-side) to generate an id token to once per 24 hours (https://developer.apple.com/documentation/signinwithapplerestapi/verifying_a_user).  

3) We apparently cannot automatically get a refreshed id token client side on iOS (see https://forums.developer.apple.com/thread/117867).


&nbsp;

----

**It's frustrating that Apple is so vague on all of this, especially as they are demanding that we use it.** I'm wrestling with the same issue: once I've SIWA'd a user on the device, how do I then create a server-side acount for them in my system and verify authz/authn on subsequent calls to my API? Apple says this in their "Verifying a User" doc on the REST API (https://developer.apple.com/documentation/signinwithapplerestapi/verifying_a_user):
 
"On success, the server issues a refresh token, which you use to obtain access tokens with future calls."
 
Future calls to...what, exactly? What are these access tokens supposed to be granting access to?
 
**I think I might throw in the towel here** and just sign up with Auth0, who seem to have somehow figured this out.

&nbsp;

&nbsp;  

## Keywords

- endpoint
- Oauth
- token
- database
- refresh token


&nbsp;  

## Recommendation

- [https://medium.com/better-programming/apple-sign-in-custom-servers-and-an-expiry-conundrum-d1ad63223870](https://medium.com/better-programming/apple-sign-in-custom-servers-and-an-expiry-conundrum-d1ad63223870)

- Auth0

&nbsp;

## Worldview

-  Apple's documentation is bad
&nbsp;