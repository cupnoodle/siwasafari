---
layout: post
title:  "How to create public RSA key using modulus and exponent for Sign In with Apple?"
date:   2020-02-21 21:06:16 +0800
categories: siwa
---


Source: [StackOverflow thread](https://stackoverflow.com/questions/57329655/how-to-create-public-rsa-key-using-modulus-and-exponent-for-sign-in-with-apple)

## Pain

- In order to verify JWT I need to use public key. **I stuck at the moment how to create public key** from modulus and exponent that I get from Apple.

&nbsp;  

## Keywords

- Sign In with Apple

- JWT (JSON Web Token)

- public key

- modulus

- exponent

&nbsp;  

## Recommendation

- To generate public key from the exponent and modulus, they need to be transformed to BigInteger, and then KeyFactory from Java security can be used.

&nbsp;

## Worldview

&nbsp;