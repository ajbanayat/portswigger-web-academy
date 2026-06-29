# Lab: Unprotected admin functionality

## Description

This lab has an unprotected admin panel. Delete the user "carlos".

## Walkthrough

The lab opens to a blog page, and we are tasked with deleting a user.

![Homepage](./images/02-unprotected-admin-functionality/homepage.png)

### Finding the admin page

First, let's try to find the admin page. Let's try /admin.

![Not found](./images/02-unprotected-admin-functionality/not-found.png)

That didn't work, so let's look at the robots.txt file instead.

![robots.txt file displays admin path](./images/02-unprotected-admin-functionality/robots.png)

Here is it! Now, let's see what we have available there.

![Screenshot shows we can delete users](./images/02-unprotected-admin-functionality/administrator-panel.png)

Here we can delete carlos! With that, this lab is over.

## Analysis

This lab takes us through a vertical escalation vulnerability, where users can gain access to functionality they should not have permission to access.