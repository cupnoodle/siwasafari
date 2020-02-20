---
layout: post
title:  "Backend integration of Sign in with Apple"
date:   2020-02-20 17:56:16 +0800
categories: siwa
---


Source: [StackOverflow thread](https://stackoverflow.com/questions/58271336/backend-integration-of-sign-in-with-apple)

## Pain

- The first problem is that the sdk provide that value as a Data.

- Is it right to convert it to string with String(data: authCode, encoding: .utf8) or I need to use authCode .map { data in String(format: "%02.2hhx", data) } like with the push notification token?

- I think the correct way should be the first one but **I'm not sure**.

- The problem is that I keep getting {"error":"invalid_client"}. I have the same error even if I provide a random string as "code", that's why I think this could be an issue on how this code is generated but I'm not sure.

- Does someone has an idea I can try?


&nbsp;  

## Keywords
- ruby
- php
- Elliptic Curve Digital Signature Algorithm (ECDSA)
- library
- SDK
- backend

&nbsp;  

## Recommendation

- I've encountered a similar issue and I'm not sure on the reason why but I was not able to sign with "Elliptic Curve Digital Signature Algorithm (ECDSA) with the P-256 curve and the SHA-256 hash algorithm" while using php. Thus I tried creating the token on ruby which worked properly.

- First install jwt to your locale with gem install jwt then use the script below.

- Just so you know the token created with this script will expire in 6 months. You can change this by editing exp parameter yet 6 months is the upper limit Apple allows.
&nbsp;

## Worldview

&nbsp;