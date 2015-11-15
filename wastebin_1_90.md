# Wastebin 1 (90)

## Problem

I created a paste-sharing site the other day. Since client-side is faster, I decided to retrieve the entire database and store it client-side. No one should be able to see it, right? Prove me wrong by finding the admin password. [page](https://www.easyctf.com/static/problems/wastebin-1/index.html)

## Hint

What's wrong with storing things on the client's browser?

## Writeup

Since the "database" of users is stored client-side, you should be able to view them from the source:

```javascript
var users = [
	{ username: "admin", password: "easyctf{cr4zy_p4ssw0rds}" },
	{ username: "tom", password: "easyctf{9et_r3kt}" },
	{ username: "becky", password: "easyctf{w0w_so_s3cure}" }
];
```

The flag is the password of the admin user, or `easyctf{cr4zy_p4ssw0rds}`.

## Flag

`easyctf{cr4zy_p4ssw0rds}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/web.md
* https://github.com/DavidJacobson/EasyCTF-2015-writeup/blob/master/web.md#wastebin-1---90-pts-
