---
layout: post
title:  "Refresh the token"
date:   2020-02-22 01:42:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/message/364993#364993)

## Pain

- I was wondering how I can get a refreshed token from the device after the restart of the app or when the token is not valid anymore (it has a 600 seconds validity). Is there a way to resfresh it from the device directly?

&nbsp;

----

&nbsp;

- The token is a JWT with a 600 seconds validity, but there is no method to get a new identityToken from the client after the login is completed (of course if the user has not revoked the authorisation)



&nbsp;  

## Keywords


&nbsp;  

## Recommendation

- The tokens returned by the AppleID authorization credential should be used to create an account in your system, your server can exchange the authCode for a refresh token via the Sign in with Apple service API:
https://developer.apple.com/documentation/signinwithapplerestapi
 
Additionally, the client app can use the previously returned user identifier to fetch the credential state via this API:
https://developer.apple.com/documentation/authenticationservices/asauthorizationappleidprovider
 
If the credential state is authorized, the credential is valid.  If the state returns revoked, a new set of tokens will be generated upon user authorizing the app again.
 
The tokens returned during the authorization are ephemeral and should be used to create a session within your apps system.

&nbsp;

----

&nbsp;

I'm trying to figure out a good way to provide sessions between my app and my appserver  since Sign In with Apple won't provide them the way every other services (Google, Facebook , Twitter, AWS Cognito, etc)  do.  At first I thought I might need my own OAuth 2.0 server but the simplest thing I can think of to do is have my app server create and return new JWTs to my app.  When the user signs in with Apple, I send the identity token to my app server, verify the identity token with Apple, then create JWTs (identity/access and refresh) and return them along with the expiration back to my app.

&nbsp;

## Worldview

&nbsp;