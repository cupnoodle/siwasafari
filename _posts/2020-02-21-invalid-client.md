---
layout: post
title:  "Invalid Client_ID"
date:   2020-02-21 21:14:16 +0800
categories: siwa
---


Source: [Github Issue](https://github.com/aaronpk/sign-in-with-apple-example/issues/4)

## Pain

-  I have followed your tutorial step by step and **I keep getting invalid client_id in my response**.

- When I test the client secret in https://jwt.io, I get an invalid signature error. Any idea on what might be causing this ? thanks.

&nbsp;

----

The same problem



&nbsp;  

## Keywords

- signature
- JWT (Json web token)

&nbsp;  

## Recommendation

- I think it is the client_secret problem?

- When I test sending the user to Apple with a bad client_id I see this error from apple:

&nbsp;

## Worldview

&nbsp;