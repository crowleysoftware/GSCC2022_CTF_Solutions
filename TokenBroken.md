# Token Broken

### Challenge
> Make a Request with a valid JWT token to Account/Verify end point with subject "Hacked".

When you log into the API you receive a JWT token back. Your challenge is to make a GET request to the "verify" endpoint with a valid token that has "Hacked" as the subject.

Let's first look at the token you get when you log in:

> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJHU0NDQ1RGIiwidXNlciI6InRpY3RhY21hc3RlcjMiLCJyb2xlIjoiaGFja2VyIiwiYXVkIjoiVGljVGFjVG9lIiwiYWRtaW4iOmZhbHNlLCJleHAiOiIyMDIyLTExLTA2VDEzOjQ4OjM1LjAyMjk2MDVaIn0.YikqNnMGbvywHDI9Bj83z8gJgCeO6_W9megL2UkkBYY

JWT tokens are in the format: **header.payload.signature**. You can decode them with online tools like [jwt.io](https://jwt.io/)

![](image/tokenbroken.png)

Your challenge is to put "Hacker" in the subject (sub) where "GSCCCTF" currently is. In order to do this you need to basically know two things:
1. How build a JWT token
1. The hash key

Technically, if you use [jwt.io](https://jwt.io/) you don't really need to know how to build a token, the app will do it for you. Right within that page you can edit **sub** to be "Hacked" instead of "GSCCCTF". However, if you try to submit the generated token you will find that it doesn't work. This is because the signature is wrong. The signature is a hash of the header and payload. You need to know the key and the hash algorithm in order to create the correct signature. Once you know the key you can enter it where you see *your-256-bit-secret* and the app will take care of the rest. (p.s. the timestamp also has to be valid, so set its expiration in the future if necessary)

So how do you obtain the hash key? Well if you solved "No Clue" then you already layed eyes on it. Since of course you have been looking over the Swagger docs and since of course you poked at the Admin/SiteConfig you will have noticed "jwt_KEY" is returned. Oops, someone was pretty careless to expose configuration like that:

![](image/tokenbroken2.png)

Now you can plug the key into [jwt.io](https://jwt.io/), change the **sub** to "Hacked" and you will have a valid token for sending to the /Account/Verify endpoint.

![](image/tokenbroken3.png)


