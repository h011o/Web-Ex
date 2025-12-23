# Lab: Unprotected admin functionality

* On going to `/robots.txt` we can see that `/administrator-panel` is disallowed. Simply modifying the URL with this value takes us to our required admin panel.

***

# Lab: Unprotected admin functionality with unpredictable URL

Going through the source code we can find,

```javascript
var isAdmin = false;
if (isAdmin) {
   var topLinksTag = document.getElementsByClassName("top-links")[0];
   var adminPanelTag = document.createElement('a');
   adminPanelTag.setAttribute('href', '/admin-cc4vas');
   adminPanelTag.innerText = 'Admin panel';
   topLinksTag.append(adminPanelTag);
   var pTag = document.createElement('p');
   pTag.innerText = '|';
   topLinksTag.appendChild(pTag);
}
```

This leaks the admin panel URL: `/admin-cc4vas`

***

# Lab: User role controlled by request parameter

<img width="884" height="171" alt="image" src="https://github.com/user-attachments/assets/a7fa8d17-9a7f-4a97-9ec4-ae56f237a762" />

Alternative (Using Burp to identify the cookie):

```javascript
GET /my-account?id=wiener HTTP/2
Host: 0ab1004403686283806dd5180030008f.web-security-academy.net
Cookie: Admin=true; session=vIIAOChEuir55L4XYdm4rxRkm8QoyYkO
```
***

# Lab: User ID controlled by request parameter, with unpredictable user IDs

Logging in to the account with the given credentials gives us our API key: `p3Zv7mlXVNKBKGApgQTiKdURTtUP47FO` at the URL `/my-account?id=8fa6caf4-17c6-4293-b923-f1de6de18635`.

We can then access the blog "The history of swigging port" to find our user carlos at `/blogs?userId=e0c3e677-60df-4ba7-896a-bb2fb088aeba`, on modifying the previous URL with the new user ID we get the required API: `XubM92nECppkHjqRUhUA0NTic76EHZdo`

Note: the blogs on the website are surprisingly fire ngl

# Concepts Learned

* Insecure Direct Object Reference
* Horizontal and Vertical privelege escalation
* 
