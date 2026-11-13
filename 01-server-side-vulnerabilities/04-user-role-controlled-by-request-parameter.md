# Lab: User role controlled by request parameter

## Description

Access the admin panel and delete the user "carlos." Admins are recognized using a cookie.

## Walkthrough

We are given the credentials "wiener:peter" so let's try to log in.

![logging in using the given credentials](./images/04-user-role-controlled-by-request-parameter/login.png)

Now, we're taken to our account with nothing visibly useful. Let's try looking through the dev tools again.

![account page displays username "wiener" and a textbox to update email](./images/04-user-role-controlled-by-request-parameter/account.png)

We know admins are recognized using cookies, so we'll take a look at the Storage tab this time.

![admin cookie has a value of false](./images/04-user-role-controlled-by-request-parameter/cookie.png)

This Admin cookie seems to be it! Let's try and update the value to "true." After a quick refresh, a link to the admin panel appears up at the top.

![admin panel link appears](./images/04-user-role-controlled-by-request-parameter/admin-panel-link.png)

Here we are again! Now, we can delete "carlos" once again.

![we've accessed the admin panel](./images/04-user-role-controlled-by-request-parameter/admin-panel-cookie.png)

## Analysis
The application makes an attempt at checking authorization for the admin panel, but it was insufficient this time since we were able to manipulate the value to whatever we want. Real world systems need to have more robust methods of authentication and authorization to protect against hackers.