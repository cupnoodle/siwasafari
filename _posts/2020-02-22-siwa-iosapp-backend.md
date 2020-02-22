---
layout: post
title:  "Sign in with Apple (iOS App + Backend verification) API returns error “invalid_client"
date:   2020-02-22 18:10:16 +0800
categories: siwa
---


Source: [StackOverflow thread](https://stackoverflow.com/questions/57809927/sign-in-with-apple-ios-app-backend-verification-api-returns-error-invalid-c)

## Pain

- **Here I'm confused**. In order to make this call, the backend needs to provide a bunch of parameters:

- B, however, still doesn't work. Today I revoked the key for A and created a new one and now it doesn't work anymore with the new one, but still with the old one, even though I deleted it on the Dev Portal. I'm so confused.

```
{
    "error": "invalid_client"
}
```

- I wonder if Apple needs some time indexing or something like that. I just want to understand how this works.


&nbsp;

----

&nbsp;

I'm having the same issue with invalid_client, what kind of value did you provide for the user agent header?


Thanks, still can't get this thing to work. I am pretty certain my token (secret) is created correctly, did you do anything else in the dev console other than creating the key for Apple Sign in and attaching it to a bundle identifier?

----

&nbsp;  

## Keywords

- sign in with apple
- backend
- JWT (JSON Web Token)
- Key
- Bundle ID


&nbsp;  

## Recommendation

There are several reasons why it could happen:

1. client_id for web should be Service id. For apps it should be App bundle id. (Even if you use native apple dialog get code and later pass it to a webserver and then use it to request token API.) sub in JWT call should be the same as client_id. See the answer there Apple forum

2. Your JWT library does not support encryption required by Apple sign-in. They use the JWT standard for this, using an elliptic curve algorithm with a P-256 curve and SHA256 hash. In other words, they use the ES256 JWT algorithm. Some JWT libraries don’t support elliptic curve methods, so make sure yours does before you start trying this out. ES256 and invalid_client

3. Dates in token. Try to set the following
```
 expires: DateTime.UtcNow.AddDays(2), // expiry can be a maximum of 6 months
 issuedAt: DateTime.UtcNow.AddDays(-1),
 notBefore: DateTime.UtcNow.AddDays(-1),
```
It failed with invalid_client on my webserver, since Apple considered it as a certificate from the future, when I had:
```
 expires: DateTime.UtcNow.AddMinutes(5), // expiry can be a maximum of 6 months
 issuedAt: DateTime.UtcNow,
 notBefore: DateTime.UtcNow,
```

It's also important to specify the User-Agent header when you call the token API. It's also worth mentioning that curl can throw this error, while it will work fine when you call it from a web server.

&nbsp;

## Worldview

&nbsp;