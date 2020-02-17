---
layout: post
title:  "Getting invalid_grant when validating the authorization code"
date:   2020-02-17 19:17:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/thread/125468)

## Pain

- I'm trying to implement Sign in with Apple and it's been going fine **until I tried to validate the authorization code using the Web Service Endpoint** – https://appleid.apple.com/auth/token.

- The error I'm getting back from the request is invalid_grant.

- If I decode the client_secret jwt that I created, it looks like this, **which is what the documentation says it should look like**. (I followed the documentation and still getting errors)

- Any ideas? Thanks in advance.

### Commenters Pain

- **I am facing the exact same problem**. I am trying to integrate this in a Django project using this https://github.com/truffls/sign-in-with-apple-using-django, **already asked this question there as well** https://github.com/truffls/sign-in-with-apple-using-django/issues/2 .
 
- **Others are having the same problem** - [https://forums.developer.apple.com/thread/118135](https://forums.developer.apple.com/thread/118135)
 
- I'll reply if i'll get it working.

- Hello dragosc, did you find a solution? I have the same problem and followed the same tutorial.
&nbsp;  

## Keywords
Sign in With Apple
Web Service
Endpoint
POST Request
URL
JWT (Json Web Token)
Django

&nbsp;  

## Recommendation
I am trying to integrate this in a Django project using this https://github.com/truffls/sign-in-with-apple-using-django

&nbsp;

## Worldview
Follow the official documentation
&nbsp;