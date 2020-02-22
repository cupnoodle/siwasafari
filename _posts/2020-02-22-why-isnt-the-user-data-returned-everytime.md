---
layout: post
title:  "Why isn't the user data being returned every time?"
date:   2020-02-22 16:58:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/message/380916#380916)

## Pain

- Next, I try signing in again (same everything)
 
But, I get this option
When I click "continue" the data looks like this
 
Parameters:
{"state"=>"[state]", "code"=>"[code]", "id_token"=> "[id token]"}
As you can tell, there is no user object, no email, nothing I can use!

- This bug(?) only appears when clicking Continue, which I can assume appears on devices that aren't running iOS 13. It's quite a problem on devices that aren't this small set of devices, so I hope this is either known, easily fixable, or something!

----

&nbsp;

That's helpful to know when developing (also confirmed), but this is not a journey I'm prepared to to send users on.

----

&nbsp;

So basically, in case of any error on our backend while processing the initial authentication the user will be stuck forever. Maybe they'll figure it out and reset trust on Apple ID site and maybe they will contact our support who will help them. Maybe. Most likely they'll just decide that "this app *****". Please fix this, Apple!


&nbsp;

----

&nbsp;

From my perspective:
 
- It is not privacy, because the user has already chosen to share that data with the app.
- It is not trust (cf. 'abuse', in your message above), because the user has already chosen to trust the app/site the first time round.
- It is not good UX, because it breaks existing patterns from other third party sign-ins that the user may be familiar with, which don't have this limitation (Google, Facebook), and don't require revoke-trust-workarounds on failure.
 
This just appears to be broken.

&nbsp;

----

&nbsp;

I fully agree that revoke-trust-workarounds are a complete UX disaster. Also I'm trying to reason for the current implementation myself and I totally agree that the implementations, currently known through other providers, are more resilient to implement.
 
Other than the, probably subjective, feeling of only having their e-mail address transmitted once, I can't see any privacy advantages here.
Compared to the chance of a failing webhook, or something on the server going south, the issue produced by this probably outweigh the "benefits".


&nbsp;

----

&nbsp;  

Yes, this is a very bad architecture decision.  The internet is not the same thing as the Apple internal netwoek. Sometimes it doesn't work as expected.  Regardless of the servers not handling the response or not there's a bunch of other things that can AND DO get in the way.  This is going to be very frustrating for the users that get an error and are essentially permanently unable to login to our app.   HORRIBLE user experiuence and it does nothing to further privacy.


&nbsp;

----

&nbsp;

I'd like to +1 the concerns here.  I have a native app with an AppEngine backend.. a RESTfull server.  I don't explictly need the email/name for my game though it does help me when users need support.  For those developers that do need the data think it should be supplied each time you ask for getCredentialStateForUserID or some similar command (getCredentialForUserID?)
 
The part I'm scratching my head about is the "credential.authorizationCode".  I see we get that on the inital login and I have been able to verify that code with https://appleid.apple.com/auth/token but doesn't that code expire in an hour (at least that's what the return payload suggests)?  Wouldn't I need to get the current code from the credential with each REST call to my server so I can verify identity on the other end?  That's what I do for Facebook login.. with each REST call from my app I attach the [FBSDKAccessToken currentAccessToken].tokenString] and verify it on my server with Facebook (I do some memcaching on the server side it's not calling the fb servers every time).
 
**How do I continually verify separate REST calls to my server from a user over time? What's the proposed pattern?  If there's**

 
Thanks D


&nbsp;

----

&nbsp;

Hey dank,
I am facing the same issue. How are folks solving this? Did you arrive at a conclusion?

&nbsp;

----

&nbsp;



&nbsp;

## Keywords

- framework
- Sign in with Apple (SIWA)
- parameters
- Access token
- endpoints
- JWT (JSON Web Token)
- REST API
- JSON
- webhook
- payload


&nbsp;  

## Recommendation

- The scopes are only shared once, during the intial authorization.   Once the SIWA API returns the information, it is up to the client application to store it within their sytems.   For follow up authorizations, the "user" identifier returned as part of SIWA API should be used as a means of fetching the previously shared information from your system.
 
Once SWIA API returns the information, the application should create an account in its own system, store the information and later use the "user" identifier to retrieve it for follow on authorizations.
 
Edit:
 
The data is only returned once for privacy reasons, we do not support an ongoing data sharing.

&nbsp;

----

&nbsp;

You can revoke an authorized client by going to appleid.apple.com. There's a link to unauthorize already authorized apps with SIWA. Then you can try again with the same Apple ID and you'll receive the user JSON payload again. Confirmed it works today


&nbsp;

----

While the email address isn't returned in every call, the JWT containing the email address is.
 
The email field in ASAuthorizationAppleIDCredential will be blank.

```
 /** @abstract An optional email shared by the user.  This field is populated with a value that the user authorized. 
     */  
    open var email: String? { get }  
 ```
However, you can parse the JWT to get the email.
```
    /** @abstract A JSON Web Token (JWT) used to communicate information about the identity of the user in a secure way to the app. The ID token will contain the following information: Issuer Identifier, Subject Identifier, Audxpiry Time and Issuance Time signed by Apple's identity service. 
     */  
  
    open var identityToken: Data? { get }  
```
To parse the identity token, you can use a Swift JWT Decoder library (of which there are many) or decode and parse it yourself.
 
I was able to retrieve the email each time using this technique.


&nbsp;

## Worldview

- Don't break exisiting UX / pattern
&nbsp;