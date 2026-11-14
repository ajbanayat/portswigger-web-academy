# Lab: User role controlled by request parameter, with unpredictable user IDs

## Description

Find the GUID for "carlos" and submit his API key on the user account page.

## Walkthrough

We know the vulnerability is on the account page, so let's try to log in.

![homepage](./images/05-user-role-controlled-by-request-parameter-unpredictable/home.png)

Here we have our GUID. Let's see if we can find carlos's GUID anywhere.

![account page displays our GUID](./images/05-user-role-controlled-by-request-parameter-unpredictable/account-page.png)

In the network tab of the dev tools, we can see that we are identified using an ID. Let's go back to the home page and see if we can find anything else.

![URL in dev tools has request parameter for ID](./images/05-user-role-controlled-by-request-parameter-unpredictable/account-page-dev-tools.png)

The home page has a few articles, what will we see inside? Let's click on the first one.

![article titled Cell Phone Free Zones](./images/05-user-role-controlled-by-request-parameter-unpredictable/article-1.png)

Interestingly, there is a section showing that our user is the other, and when we take a look using the dev tools, the link contains our user ID! Let's see if we can find one for carlos.

![author's html tag contains a link with our user ID](./images/05-user-role-controlled-by-request-parameter-unpredictable/author-href.png)

It turns out that the second article in the home page was written by carlos! Note down his user ID (b4aa5225-ca77-4d53-bbb6-54c06d83743d).

![carlos's author html tag contains a link with his user ID](./images/05-user-role-controlled-by-request-parameter-unpredictable/carlos-href.png)

Let's head back to our account page and replace our user ID with carlos's user ID. We've successfully entered carlos's account page! Clicking on "Submit Solution" at the top and entering carlos's GUID completes the lab.

![carlos's account page](./images/05-user-role-controlled-by-request-parameter-unpredictable/carlos-account.png)

## Analysis
This is another example of an authorization flaw that is easily exploitable by bad actors. The page does not check that we are the correct user before loading for us. The site should have checked not only that we were logged in, but also that we were the correct user.