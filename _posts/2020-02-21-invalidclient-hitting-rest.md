---
layout: post
title:  "Invalid_client on hitting REST API with iOS App authorizationCode & identityToken_"
date:   2020-02-21 17:23:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/thread/120695)

## Pain

- I'm trying to get Sign In with Apple integrated into a native iOS app, and am running into troubles trying to validate the data coming back in ASAuthorizationAppleIDCredential over the REST API on my app's server-side.

- When I submit the post request, I constantly get invalid_client on grant_type of authorization_code. **No further error response is present at all, so I'm grasping at straws a bit**.

- If anyone has experience fetching the code/secret from native, and then verifying these over the REST API from a server, I'd be very appreciative to hear any insights.

&nbsp;  

----

&nbsp;  
- This article is the **missing documentation that Apple is lacking currently**, would definitely reccomend giving it a read over if you are similarily trying to validate client tokens on your own server.

- I had misunderstood the provided Sign In with Apple API's and was trying to use the web token API to do this job for me, when you really need to use the auth/token endpoint to grab Apple's public key, and decode the identityToken signed JWT using that.

----

&nbsp;  

- I always get the error `invalid_client`.
 
- I don't understand how can i pass this error. Can you xplain what you did ?
 
- **I don't unserstand your solution**... or how i should use your php plugin

----

&nbsp;

How does this reply help. The reply does not go into the issue with auth/token endpoint. That endpoint requires a client_secret and a client_id, and it looks like Apple does not like one of the two. Why?

&nbsp;  
## Keywords

- REST
- API
- Sign in with Apple
- server-side
- native
- web token
- public key
- JWT (JSON Web Token)
- PHP
- secret
- token
- Endpoint

&nbsp;  

## Recommendation

- The ID token is not the client secret to use when invoking the token endpoint. See the section "Creating the Client Secret" at https://developer.apple.com/documentation/signinwithapplerestapi/generate_and_validate_tokens

&nbsp;

----

- After digging further online, I managed to find a blog post by Curtis Herbert here: https://blog.curtisherbert.com/so-theyve-signed-in-with-apple-now-what/

&nbsp;

## Worldview
- Apple's documentation is lacking
- Error message should be helpful

&nbsp;