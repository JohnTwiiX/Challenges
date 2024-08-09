# Forged Feedback

## Type

Broken Access Control

## Description

Post some feedback in another user's name.

## What do I need?

- Request
- user login

## My Way

- I log in with any account

- I go to "Customer Feedback" and enter my comment
![alt text](comment.png)

- Now I start my Burpsuite Proxy intercept and click on submit
![alt text](intercept.png)

- I can see the Request and i can change it

    ```json
    {
        "UserId": 2,
        "captchaId": 10,
        "captcha": "1",
        "comment": "That's sh*t (***in@admin.de)",
        "rating": 1
    }
    ```

- **It worked!**
