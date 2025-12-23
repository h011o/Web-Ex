# Lab: Username enumeration via different responses

I sent the `/login` POST request to Burp Intruder and used the Sniper Attack to brute force a list of usernames.
* On sorting by length, I can see ajax having a length greater than the others.

  <img width="1364" height="205" alt="image" src="https://github.com/user-attachments/assets/41fda107-7a2a-407b-b89f-4ffd83e0255c" />

I then set the username field as the payload (`username=ajax&password=[payload]`) and started another brute force attack which recieved a status code 302 for the password `mobilemail`.

This helps us find our required username and password.

# Lab: 2FA simple bypass

This lab required exploiting a vulnerability where the 2FA system is flawed such that the verification code is prompted to be entered by the user AFTER logging in and could be skipped entirely by simple navigation across the website.

# Concepts Learned

* Status Code `302` means redirection, this means that a specific request exists while brute-forcing.
* Status Code `200` means the request was recieved and processed. 
