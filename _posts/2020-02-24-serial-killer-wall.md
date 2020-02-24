---
layout: post
title:  "Serial Killer Wall (Grouped Pains)"
date:   2020-02-24 17:15:16 +0800
categories: siwa
---

Text in brackets `()` is my own interpretation to crisp up the pain

Keywords: 
SIWA = Sign in with Apple

## Keep on getting Invalid_client error while implementing SIWA

Error: Invalid_Client - What?
(I don't know how to solve the invalid_client error, the error message doesn't tell me how to solve it)

The result is always the same: {“error”:”invalid_client”}

It’s not working with both ids and mixed different things.
Nothing. invalid_client.
(I have spent a lot of time trying with bundle id, web service id, or changing other parameters, I don't know what to do anymore)

Can anyone help me please?  **I’m sitting here for hours and getting only invalid_client**

Always getting invalid_client error when trying to authorize token

I always getting an error when i try to hit the endpoint /auth/token

I’m actually doing the same exact thing, and getting the same error. 

I hope you’ve had progress since this (the question asked in forum) is a few weeks old now, but in case others are hitting this same problem, as I was, and finding this unanswered question

If you do this and get either invalid_grant or a success response, you’ve made progress. invalid_grant seems to be the next error in the chain, and is raised after client validation is passed.

I’m trying to validate the code on a cloud function but I always get same result “invalid_client”. 

I get now the response {“error”:”invalid_client”} from the apple server. What am I doing wrong? Could it be that I’m generating the JWT token wrong?

The problem is that I keep getting {“error”:”invalid_client”}. I have the same error even if I provide a random string as “code”, that’s why I think this could be an issue on how this code is generated but I’m not sure.

When I submit the post request, I constantly get invalid_client on grant_type of authorization_code. No further error response is present at all, **so I’m grasping at straws a bit.**

I don’t understand how can i pass this error. Can you xplain what you did ?

I have followed your tutorial step by step and I keep getting invalid client_id in my response.

When I test the client secret in https://jwt.io, I get an invalid signature error. Any idea on what might be causing this ? thanks.

I need to authentificate user and get its email. My class AppleId always returns: “invalid_client”.

Maybe i have some mistakes in my logic?

I tried to obtain a refresh token after sign in with apple via AuthenticationServices and the response was {“error”:”invalid_client”}.

I’m having the same issue with invalid_client, what kind of value did you provide for the user agent header?

Thanks, still can’t get this thing to work. I am pretty certain my token (secret) is created correctly, did you do anything else in the dev console other than creating the key for Apple Sign in and attaching it to a bundle identifier?

ere I’m confused. In order to make this call, the backend needs to provide a bunch of parameters:

B, however, still doesn’t work. Today I revoked the key for A and created a new one and now it doesn’t work anymore with the new one, but still with the old one, even though I deleted it on the Dev Portal. I’m so confused.
```
{
    "error": "invalid_client"
}
```
I wonder if Apple needs some time indexing or something like that. I just want to understand how this works.

## Keep on getting Invalid_grant error while implementing SIWA

I’m trying to implement Sign in with Apple and it’s been going fine until I tried to validate the authorization code using the Web Service Endpoint – https://appleid.apple.com/auth/token.

The error I’m getting back from the request is invalid_grant.

**I am facing the exact same problem**. I am trying to integrate this in a Django project using this https://github.com/truffls/sign-in-with-apple-using-django, **already asked this question there as well** (no one responded) https://github.com/truffls/sign-in-with-apple-using-django/issues/2 .

Others are having the same problem - https://forums.developer.apple.com/thread/118135

I’ll reply if i’ll get it working.

Hello dragosc, did you find a solution? I have the same problem and followed the same tutorial.  

Invalid_grant when exchanging authorization code obtained from 'ASAuthorizationAppleIDCredential' on the server-side

Unfortunately, this fails with an invalid_grant error.

Did you manage to figure out what was going wrong? I’m trying to implement Sign in with Apple at the moment and I’m getting “invalid_grant” when trying to validate the token.

however, I now get a 'invalid_grant'.

## Getting 'Sign up not completed' error while implementing SIWA
Sign in With Apple shows this error “Sign-Up Not Completed” when we tap on continue button and after verifying Face ID.

I have noticed the same issue on my own apps. I cannot login, and no error is sent to the ASAuthorizationControllerDelegate.

I cannot find anything wrong with my account, and it’s not an error in any one application. I tested on both an existing app and a new app as shown in the screenshot. Any advice would be helpful.

Our team also encountered this “Sign-Up not completed” issue today. Like sloshire1 mentioned, no error is sent to the delegate. Interestingly enough, the issue only happens when the user chooses to hide their email. Just for sanity, confirmed that the user hasn’t revoked Apple ID permission from Settings. Seems like this is an issue on Apple’s end as he has the same Sign In with Apple issue on a completely different app as well.
 

I have the same issue but it happens whether or not the user is hiding their email.

Has anyone figured out a way to debug this / get a better error message?

I’m having the exact same issue as well? Has anybody figured it out. I’m completely stuck.

## Error message provided by Apple isn't helpful / Don't know how to solve the error

I don’t know why the client should be invalid.

The useless error message of the world.
(I don't know how to solve the invalid_client error, the error message doesn't tell me how to solve it)

I am still experiencing the same invalid_token error though. My JWK has the right info, my key ID is correct, I am using a file I downloaded from Apple. I wish there was a debugging tool or some more explicit error code. (I followed the documentation steps but still get an error, which doesn't tell me how to solve it)

My idea is that the signing of the client_secret is wrong for some reason. (invalid_client error) Any help? (uncertainty on how to solve it)

Any ideas? Thanks in advance.

I suspect this process is failing because the authorisation code simply wasn’t created for the client ID of the Services ID. However there is no way to indicate the intended use on the native API, as far as I can see.

Is there anything else you can think could be going wrong here as I’m getting “invalid_grant” and the client_id I pass when validating is the same bundle id that I’m using in the app. **Can’t figure out what else could be going wrong here.** Thanks.

So far this post helped me so much, however, I now get a “invalid_grant”. Following : https://developer.apple.com… **I understand that I have absolutely no idea about what’s this error about** :O

Does anyone have this issue? I am not that familiar with Apple and I have no idea in which direction should I go to track that bug down..

Hi, Max. Did you end up figuring out what caused “invalid_grant”? I’m implementing Sign in with Apple right now and that’s the response I’m getting when trying to validate the authorization token.

tl;dr need to use full uri with scheme in the apple configuration portal otherwise things will fail silently with no good errors :(

I get now the response {“error”:”invalid_client”} from the apple server. What am I doing wrong? Could it be that I’m generating the JWT token wrong?

The problem is that I keep getting {“error”:”invalid_client”}. I have the same error even if I provide a random string as “code”, that’s why I think this could be an issue on how this code is generated but I’m not sure.

Does someone has an idea I can try?

When I submit the post request, I constantly get invalid_client on grant_type of authorization_code. No further error response is present at all, **so I’m grasping at straws a bit.**

I don’t understand how can i pass this error. Can you xplain what you did ?

I have followed your tutorial step by step and I keep getting invalid client_id in my response.

When I test the client secret in https://jwt.io, I get an invalid signature error. Any idea on what might be causing this ? thanks.

I need to authentificate user and get its email. My class AppleId always returns: “invalid_client”.

Maybe i have some mistakes in my logic?

I cannot find anything wrong with my account, and it’s not an error in any one application. I tested on both an existing app and a new app as shown in the screenshot. Any advice would be helpful.

Our team also encountered this “Sign-Up not completed” issue today. Like sloshire1 mentioned, no error is sent to the delegate. Interestingly enough, the issue only happens when the user chooses to hide their email. Just for sanity, confirmed that the user hasn’t revoked Apple ID permission from Settings. Seems like this is an issue on Apple’s end as he has the same Sign In with Apple issue on a completely different app as well.
 

I have the same issue but it happens whether or not the user is hiding their email.

Has anyone figured out a way to debug this / get a better error message?
 

I’m having the exact same issue as well? Has anybody figured it out. I’m completely stuck.


I’m having the same issue with invalid_client, what kind of value did you provide for the user agent header?

Thanks, still can’t get this thing to work. I am pretty certain my token (secret) is created correctly, did you do anything else in the dev console other than creating the key for Apple Sign in and attaching it to a bundle identifier?

I wonder if Apple needs some time indexing or something like that. I just want to understand how this works.

## Apple documentation / others tutorial is not helpful / unclear steps

At least he (one of the tutorial written by some blog) is here to explain to us how we can implement YOUR system (Apple doesn’t have good official documentation on how to implement Sign in with Apple)

So please, help us finally integrate YOUR system (I don't know how to solve the error to successfully implement sign in with Apple)

**I’ve read so many guides and tutorials and nothing works.**  
(keep on getting error while implementing sign in with Apple)

If I decode the client_secret jwt that I created, it looks like this, which is what the documentation says it should look like. (I followed the documentation and still getting errors)

It is unclear what client ID should be used, or how to make a Services ID for use with data from the native API.

The redirect URI parameter is also very unclear - since there is no redirect in the process. However I have found that the result is always the same, regardless of what the parameter is set to (including if it is omitted entirely).

I suspect this process is failing because the authorisation code simply wasn’t created for the client ID of the Services ID. However there is no way to indicate the intended use on the native API, as far as I can see.

**I have scoured all the documentation at length and have still not gotten anywhere.**

there is a lot of opportunity for Apple to improve their documentation.

Have you finally managed to find a workaround for this confusing apple sign in flow?

This article is the missing documentation that Apple is lacking currently, would definitely reccomend giving it a read over if you are similarily trying to validate client tokens on your own server.

I don’t unserstand your solution

How does this reply help. The reply does not go into the issue with auth/token endpoint. That endpoint requires a client_secret and a client_id, and it looks like Apple does not like one of the two. Why?

Can I obtain a refresh token with AuthenticationServices framework?

I tried to obtain a refresh token after sign in with apple via AuthenticationServices and the response was {“error”:”invalid_client”}.

I wonder if Apple needs some time indexing or something like that. I just want to understand how this works.

##  I don't know how to validate the authorization_code correctly

What is the intended approach to take an authorization code from ASAuthorizationAppleIDCredential and exchange it with the REST API?

thank you for providing the example. Would you mind let us know how you generated the key for signing JSON web token?

@billinghamj so can you please let me know the final curl request & the associated values used by you to validate the authorization_code sent from the App.

Is there anything else you can think could be going wrong here as I’m getting “invalid_grant” and the client_id I pass when validating is the same bundle id that I’m using in the app. **Can’t figure out what else could be going wrong here.** Thanks.

Is it right to convert it to string with String(data: authCode, encoding: .utf8) or I need to use authCode .map { data in String(format: “%02.2hhx”, data) } like with the push notification token? (Uncertainty)

I think the correct way should be the first one but I’m not sure. (Uncertainty)

I’m trying to get Sign In with Apple integrated into a native iOS app, and am running into troubles trying to validate the data coming back in ASAuthorizationAppleIDCredential over the REST API on my app’s server-side.

If anyone has experience fetching the code/secret from native, and then verifying these over the REST API from a server, I’d be very appreciative to hear any insights.

I had misunderstood the provided Sign In with Apple API’s and was trying to use the web token API to do this job for me

## I don't know how to decode the identityToken

How to decode ‘id_token’ from apple, that contains useful payload? I have just private key with extension .p8 (downloaded from dev page).

## I don't know how to create public key to verify the identityToken (JWT)

In order to verify JWT I need to use public key. I stuck at the moment how to create public key from modulus and exponent that I get from Apple.


## Don't know how to sign out from SIWA

With most OAuth systems a call to https://service/oauth/revoke?token={token} or along those lines should disconnect the user, I can’t find anything like this in Sign in With Apple. Is this an option? It is needed for when a user removes their account

## SIWA is confusing (with error message that doesn't tell how to fix, and it behaves very differently than others login like FB / Google)

Given that we’re being told we have to incorporate Apple Sign-In into our iOS apps (if we offer general purpose sign-in facilities)
It’s frustrating that Apple is so vague on all of this, especially as they are demanding that we use it.

Why isn't the user data being returned every time?

That’s helpful to know when developing (also confirmed), but **this is not a journey I’m prepared to to send users on**.

So basically, in case of any error on our backend while processing the initial authentication the user will be stuck forever. Maybe they’ll figure it out and reset trust on Apple ID site and maybe they will contact our support who will help them. Maybe. **Most likely they’ll just decide that “this app sucks”**. Please fix this, Apple!

It breaks existing patterns from other third party sign-ins that the user may be familiar with, which don’t have this limitation (Google, Facebook), and don’t require revoke-trust-workarounds on failure.
This just appears to be broken.


## How to authenticate subsequent REST API request to backend after sign in with Apple?
We apparently cannot automatically get a refreshed id token client side on iOS (see https://forums.developer.apple.com/thread/117867).

It’s frustrating that Apple is so vague on all of this, especially as they are demanding that we use it. I’m wrestling with the same issue: once I’ve SIWA’d a user on the device, how do I then create a server-side acount for them in my system and verify authz/authn on subsequent calls to my API? Apple says this in their “Verifying a User” doc on the REST API (https://developer.apple.com/documentation/signinwithapplerestapi/verifying_a_user):

“On success, the server issues a refresh token, which you use to obtain access tokens with future calls.”

Future calls to…what, exactly? What are these access tokens supposed to be granting access to?

I think I might throw in the towel here and just sign up with Auth0, who seem to have somehow figured this out.

The part I’m scratching my head about is the “credential.authorizationCode”. I see we get that on the inital login and I have been able to verify that code with https://appleid.apple.com/auth/token but doesn’t that code expire in an hour (at least that’s what the return payload suggests)? Wouldn’t I need to get the current code from the credential with each REST call to my server so I can verify identity on the other end? That’s what I do for Facebook login.. with each REST call from my app I attach the [FBSDKAccessToken currentAccessToken].tokenString] and verify it on my server with Facebook (I do some memcaching on the server side it’s not calling the fb servers every time).

How do I continually verify separate REST calls to my server from a user over time? What’s the proposed pattern?

Hey dank, I am facing the same issue. How are folks solving this? Did you arrive at a conclusion?

## How to refresh the token?
I was wondering how I can get a refreshed token from the device after the restart of the app or when the token is not valid anymore (it has a 600 seconds validity). Is there a way to resfresh it from the device directly?
 
The token is a JWT with a 600 seconds validity, but there is no method to get a new identityToken from the client after the login is completed (of course if the user has not revoked the authorisation)

