# Lab: Unprotected admin functionality

* On going to `/robots.txt` we can see that `/administrator-panel` is disallowed. Simply modifying the URL with this value takes us to our required admin panel.

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
