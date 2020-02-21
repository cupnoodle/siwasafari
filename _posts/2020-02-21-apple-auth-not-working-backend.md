---
layout: post
title:  "Apple Auth not working on Ruby on Rails Backend"
date:   2020-02-21 21:35:16 +0800
categories: siwa
---


Source: [Stack Overflow thread](https://stackoverflow.com/questions/59501102/apple-auth-not-working-on-ruby-on-rails-backend)

## Pain

- I need to authentificate user and get its email. My class AppleId always returns: "invalid_client".

- Maybe i have some mistakes in my logic?

&nbsp;  

## Keywords


&nbsp;  

## Recommendation

- I also had similar problem. Client_id on server should be ServiceId not AppId

- Additionally, whilst it does not deal with Rails specifically, this post might be useful: [Sign in with Apple (iOS App + Backend verification) API returns error “invalid_client”](https://stackoverflow.com/q/57809927/4200092)

&nbsp;

## Worldview

&nbsp;