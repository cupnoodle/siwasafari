---
layout: post
title:  "Error: Sign-Up Not Completed"
date:   2020-02-22 00:14:16 +0800
categories: siwa
---


Source: [Apple forum thread](https://forums.developer.apple.com/thread/122458)

## Pain

- Sign in With Apple shows this error "Sign-Up Not Completed" when we tap on continue button and after verifying Face ID.

- I have noticed the same issue on my own apps.  I cannot login, and no error is sent to the ASAuthorizationControllerDelegate. 

- I cannot find anything wrong with my account, and it's not an error in any one application.  I tested on both an existing app and a new app as shown in the screenshot.  Any advice would be helpful.

&nbsp;

----

&nbsp;

- Our team also encountered this "Sign-Up not completed" issue today. Like sloshire1 mentioned, no error is sent to the delegate. Interestingly enough, the issue only happens when the user chooses to hide their email. Just for sanity, confirmed that the user hasn't revoked Apple ID permission from Settings. Seems like this is an issue on Apple's end as he has the same Sign In with Apple issue on a completely different app as well.

----

&nbsp;

- I have the same issue but it happens whether or not the user is hiding their email.
 
- Has anyone figured out a way to debug this / get a better error message?

&nbsp;

----

&nbsp;

- I'm having the exact same issue as well? Has anybody figured it out. I'm completely stuck.

&nbsp;

----

&nbsp;  

## Keywords

- Sign in with apple
- Face ID
- REST API
- parameters
- URL
- delegate


&nbsp;  

## Recommendation

- The Sign in with Apple servers require percent encoding (or URL encoding) for its query parameters. If you are using the Sign in with Apple REST API, you must provide values with encoded spaces (`%20`) instead of plus (`+`) signs. For example, if your request URL currently looks like this—
 
.../auth/authorize?client_id=<CLIENT_ID>&redirect_uri=<REDIRECT_URI>&response_type=code+id_token&scope=name+email&response_mode=form_post&state=<STATE>&nonce=<NONCE>

Please attempt again after updating the request URL to the following—

.../authorize?client_id=<CLIENT_ID>&redirect_uri=<REDIRECT_URI>&response_type=code%20id_token&scope=name%20email&response_mode=form_post&state=<STATE>&nonce=<NONCE>

&nbsp;

----

&nbsp;  

I had this issue ("Sign Up Not Completed") and I solved it by encoding parameters (redirect_uri and response_type). Somehow, the Sign In with Apple from an iPhone/iPad using Face ID/Touch ID isn't working if the parameters aren't encoded, but the ones from a non-Apple device are working fine.


## Worldview

&nbsp;