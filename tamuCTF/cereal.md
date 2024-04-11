#CEREAL
- It is a SQLI type challange.
- When we enter into the website of the challange, we can see a login page with username and password. From the source code given in the challange, we can find that there is something called authentication.php which authenticates if the user has enetered correct credentials and gives a session called id.
- By changing session id, we will be able to login as admin and get the flag. by putting the id to ``` 0';-- ``` we find that we are able to access admin page but we are not able to get the flag, hence lets try in passwords column.
- Now to get the flag from the passwords column, and table users (we can find the details of database from php files) now we use ``` exclude ``` keyword to eliminate all the previous data and get the flag and use ``` union ``` keywoard to creat our own query with admin access.
- The following query would look like:
```
  0' except select username,email,favorite_cereal,creation_date from users where `id` = '0' union select username,email,password,creation_date from users where `id`='0'-- -
```
