---
layout: post
title:  "Invalid_grant when exchanging authorization code obtained from 'ASAuthorizationAppleIDCredential' on the server-side"
date:   2020-02-18 00:50:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/thread/118135)

## Pain
- Unfortunately, this fails with an invalid_grant error.

- Of course the identifier of the Services ID (and therefore the client ID) and the identifier of the App ID are entirely different.

- This is because it's not possible to make a Services ID with the same identifier as the App ID. **It is unclear what client ID should be used**, or **how to make a Services ID for use with data from the native API**.

- The redirect URI parameter is also very unclear - since there is no redirect in the process. However I have found that the result is always the same, regardless of what the parameter is set to (including if it is omitted entirely).

- I suspect this process is failing because the authorisation code simply wasn't created for the client ID of the Services ID. However **there is no way to indicate the intended use on the native API**, as far as I can see.

- **I have scoured all the documentation at length and have still not gotten anywhere**. 

- What is the intended approach to take an authorization code from ASAuthorizationAppleIDCredential and exchange it with the REST API?

- there is a lot of opportunity for Apple to improve their documentation.

----
&nbsp;  
- thank you for providing the example. Would you mind let us know how you generated the key for signing JSON web token?

 

----
&nbsp; 
- there is a lot of opportunity for Apple to improve their documentation.

----
&nbsp;

- I succeed on iOS 13, but I failed on watchOS 6, I wrote watch app's bundle id as client key, and told me "invalid_grant", where's wrong?

----
&nbsp;

Did you manage to figure out what was going wrong? I'm trying to implement Sign in with Apple at the moment and I'm getting "invalid_grant" when trying to validate the token.

----
&nbsp;

While validating the authorization code I am sending the following parameters with the associated values:
 
```
client_id: "App ID"  
client_secret: "App Token"  
grant_type: "authorization_code"  
code: "sent from the app"  
```
 
But still I am getting invalid_grant error
 
@billinghamj so can you please let me know the final curl request & the associated values used by you to validate the authorization_code sent from the App.

----
&nbsp;

Is there anything else you can think could be going wrong here as I'm getting "invalid_grant" and the client_id I pass when validating is the same bundle id that I'm using in the app. Can't figure out what else could be going wrong here. Thanks.

----
&nbsp;



&nbsp;  

## Keywords
- Sign in with Apple
- native API
- REST API
- App ID
- entitlement
- client ID
- client secret
- Services ID
- JWT (JSON Web Token)
- URI
- parameter
- NodeJS
- endpoint
- token
- private key )p8)
- bundle ID
- curl
- authorization code



&nbsp;  

## Recommendation

- The client_id used when calling the token endpoint should match the native app's app id. The services ID should not be used here and using that would result in failure due to mismatch between the client_id for which the authorization was granted and the one that is presenting the code for validation.
 
- The services ID is useful only for web apps where both the authorization and the grant code validation should use the services Id as the client_id.
 
- Also, redirect_uri is optional and for native apps, since the authorization grant code was not sent to a redirect_uri


----
&nbsp;

- Presumably the Services IDs/App IDs all need to be associated with the same primary App ID. The key is then associated to that group via the primary App ID too.

- For anyone else having trouble with this, this is how you can generate the client secret JWTs for different client IDs from the same key (Node JS example):

{% highlight javascript %}
const key = `  
-----BEGIN PRIVATE KEY-----  
xxx  
-----END PRIVATE KEY-----  
`;  
  
const teamId = 'xxx';  
const keyId = 'xxx';  
const webClientId = 'com.example.backend-auth-system'; // the Services ID  
const appClientId = 'com.example.MyApp'; // the App ID  
  
const jsonwebtoken = require('jsonwebtoken');  
  
// for web use  
jsonwebtoken.sign({}, key, {  
  algorithm: 'ES256',  
  expiresIn: '1d',  
  audience: 'https://appleid.apple.com',  
  subject: webClientId,  
  issuer: teamId,  
  keyid: keyId,  
});  
  
// for native use  
jsonwebtoken.sign({}, key, {  
  algorithm: 'ES256',  
  expiresIn: '1d',  
  audience: 'https://appleid.apple.com',  
  subject: appClientId,  
  issuer: teamId,  
  keyid: keyId,  
});  
{% endhighlight %}



----
&nbsp;

- For those who have the same question: the private key can be downloaded from the developer portal for only one time. It's a p8 file containing the private key string.



----
&nbsp;

I finally managed to solve it. If anyone is facing the same issue make sure the "client_id" matches the bundle identifer of the sample app that's generating the Authorization Code.

----
&nbsp;

In iOS I passed the auth code straight to my post, however billinghamj encodes with .utf8 before sending it.
 
let authorizationCode = String(data: appleIDCredential.authorizationCode!, encoding: .utf8)  
 
Make sure you take off optional words from that as well.

----
&nbsp;

I think authorizationCode is valid for 5 minutes, so make sure you are calling Apple's endpoint to verify it within this period.

&nbsp;

## Worldview

&nbsp;