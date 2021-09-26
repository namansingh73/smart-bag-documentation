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

####
