# Admin Registration

## Type

Improper Input Validation

## Description

This exploit demonstrates the use of Burp Suite to gain `administrative privileges` by `manipulating an HTTP request` during user registration. The process involves modifying the submitted user credentials so that the new user's role is set to `"admin"` instead of the default `"customer"` role.

## What do I need?

- user modal
- user registration
- Burpsuite

## My Way

- I go to "**User Registration**" in **/register**

![alt text](register.png)

- type credentials for dummy

![alt text](dummy.png)

- I click on register

- Now I go to the **HTTP history** in **proxy**
- I see my **POST** to **/api/Users**
![alt text](history.png)
- I can see in the Response I get the role **customers**

- Can I set role?

- I create another user

- Now I activate **burpsuite interceptor** in tab **proxy** and click on register
![alt text](register-2.png)

- And I set the **role** in **my Request**:

    ```json
    {
        "email": "admin@admin.de",
        "password": "123456",
        "passwordRepeat": "123456",
        "role": "admin",
        "securityQuestion": {
            "id": 2,
            "question": "Mother's maiden name?"
            "createdAt": "2024-08-09T11:26:48.973Z"
            "updatedAt": "2024-08-09T11:26:48.973Z"
        },
        "securityAnswer": "sfdfdsggfds"
    }
    ```

- I click on forward and got to history
![alt text](admin.png)

- Now I check if I really have admin rights by going to **/administration**
![alt text](image.png)

- **It worked!**
