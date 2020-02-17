---
layout: post
title:  "invalid_client for code validation on server"
date:   2020-02-17 19:08:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/message/390708#390708)

## Pain
I'm trying to validate the code on a cloud function **but I always get same result "invalid_client"**. Bellow you have my NodeJs function with an example key:_

**My idea is that the signing of the client_secret is wrong for some reason. Any help?** (uncertainty)

(No one answered a correct solution)

## Keywords
Cloud function
NodeJS

## Recommendation
What I can briefly note is that you are missing User-Agent header which is required by Apple.
(this doesn't solve the problem, incorrect recommendation)