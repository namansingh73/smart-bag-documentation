# Frontend

## Models

1. Project contains **User** database which stores a user's information such as **Name, Email, Password, Items in Cart, ID** to give relevant and most appropriate recommendations to the logged in user.

```
    name:{
       type:String,
      required:[true,'Name is mandatory']
    },
    email:{
        unique:true,
        type:String,
        validate:[validator.isEmail,'Please enter valid Email'],
        required:[true,'Email is mandatory']
    },
    userId:{
        unique:true,
        type:Number,
        required:[true]
    },
    inCart:[
        {
            pid:{
                unique:true,
                type:String
            },
            name:{
                type:String
            },
            brand:{
                type:String
            },
            price:{
                type:Number
            },
            quantity:{
                type:Number,
                default:1
            }
        }
    ],
    password:{
        type:String,
        required:[true,'Password is mandatory'],
        minlength:8,
        select:false
    },
    passwordConfirm:{
        type:String
    },
    passwordChangedAt :{
        type:Date
    },
    passwordResetToken: String,
    passwordResetExpires: Date
```

2. User data in being stored in **MongoDB** database and all queries can be found in the **mongoose** documentation : https://www.npmjs.com/package/mongoose

## Routers

#### View Router

**The view router is providing the functionality to view the webpages**

- **/login [GET]**

  > Renders the login page which contains the login form to be filled by the already registered user to log into their account.

- **/signup [GET]**

  > Renders the signup page which contains the signup form to be filled by the user to create new account in the project.

- **/ [GET]**

  > Renders the launch page of the project which contains the product **recommendations** for the logged in user and list of all the produts being fetched from the **flask** application.

- **/home [GET]**

  > Renders the home page which contains **previous order history** of the logged in user giving him the functionality to directly buy products based on previous purchases.

- **/cart [GET]**

  > Renders the cart page which contains all those products that the logged in user added to his cart which are being fetched from the database from user's information.

- **/aboutUs [GET]**

  > Renders the **about us** page which given information about **Team name, Team Member's name, College name**.

- **/forgotpassword [GET]**

  > Renders the **Forgot Password** page which can be used to send reset password mail by the user who unexpectedly forgot his logging password.

- **/resetpassword/:token [GET]**
  > Renders the **Reset Password** page which can be used to reset the password of the account in case the user forgot his password.

#### User Router

**The user router provides rest APIs for NodeJS backend**

- **/api/v1/users/signup [POST]**

  > This API sends **POST** request to the server to create a new user in the database and sends a welcome mail to the newly registered user via **Sendgrid**.

- **/api/v1/users/login [POST]**

  > This API sends **POST** request to the server to login an already registered user.

- **/api/v1/users/logout [GET]**

  > This API sends **GET** request to log the user out of the application.

- **/api/v1/users/forgotpassword [POST]**

  > This API sends **forgot password** mail to the user which contains reset password link to allow user change hi password.

- **/api/v1/users/resetpassword/:token [PATCH]**
  > This API sends **password reset** request to the server and updates the account password of the user.

#### Cart Router

**Cart router provides rest APIs for operations on the cart**

- **/cart [POST]**

  > The following rest API sends **POST** request to the server to add the current item to the cart if not already present else it updates the quantity in the cart.

- **/clearCart [POST]**

  > This API sends **POST** request to the server to empty the current cart filled by the user.

- **/cartSaveChanges [POST]**

  > This API call sends a **POST** request to save any temporary changes in the cart such as change in quantity or removal or any product from the cart.

- **/addAllInCart [POST]**

  > This API call adds all product present in **User's order history** into the cart allowing him to directly buy all the items bought earlier.
