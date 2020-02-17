---
layout: post
title:  "Error: Invalid_Client - What?"
date:   2020-02-17 18:12:16 +0800
categories: siwa
---



Source: [Apple forum thread](https://forums.developer.apple.com/thread/124521)

## Pain

I'm facing a very bad issue because **I've read so many guides and tutorials and nothing works.**

**The result is always the same**: {"error":"invalid_client"}

Response:
{% highlight javascript %}
{  
  "error": "invalid_client"  
}
{% endhighlight %}
 

The **useless error message** of the world.

**I don’t know why the client should be invalid.**


**It’s not working** with both ids and mixed different things.  
**Nothing. invalid_client.**
 
 
**Can anyone help me please? I'm sitting here for hours and getting only invalid_client**

&nbsp; 
## Keywords
- identityToken
- invalid_client
- Javascript
- API
- JWT (Javascript Web Token)
- native

&nbsp; 
## Recommendation

I developed the solution: https://gist.github.com/patrickbussmann/877008231ef082cc5dc4ee5ca661a641
I developed a oAuth client library extension for Sign in with Apple:
https://github.com/patrickbussmann/oauth2-apple
The problem was the specific algorithm which Apple uses.

----
&nbsp;    
I think here you need to use bundle id, not service id.  
  
----
&nbsp; 

## Worldview
Error message should be useful, which guide developer on how to fix what is wrong

