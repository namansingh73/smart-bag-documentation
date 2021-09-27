# Frontend

## Controllers

### Authentication Controller

> **Location** : `./controller/authController`
>
> **Parameters** : `(req,res,next)` where `req` is the request, `res` is the response and `next` is the next middleware in the function call.

1.  **signup**

    > **Return** : Returns a success message in case of successful signup which stores the newly created user in the database and redirects the user to landing page of the website else returns an error.

    ```
    exports.signUp = async(req,res,next)=>{

    };
    ```

2.  **login**

    > **Return** : Returns a success message in case of successful login and redirects to the landing page else returns an error.

    ```
    exports.login = async(req,res,next)=>{

    };
    ```

3.  **logout**

    > **Returns** : It corrupts the login cookie to allow the user to logout and redirects to the login page else returns an error.

    ```
    exports.logout = (req,res,next) => {

    };
    ```

4.  **isLoggedIn**

    > **Returns** : It checks if the requested user is logged in or not. If true then it stores the user in a local variable else redirects to the login page else returns an error.

    ```
    exports.isLoggedIn = async (req,res,next)=>{

    };
    ```

5.  **forgotPassword**

    > **Returns** : It sends password reset mail to the user who forgot his password and the corresponding link redirects to the reset password page else returns an error.

    ```
    exports.forgotPassword = async (req,res,next)=>{

    };
    ```

6.  **resetPassword**

    > **Returns** : It allows the user to set a new password for his account in case the user forgot the password and save the new password in the database else returns an error.

    ```
    exports.resetPassword = async (req,res,next)=>{

    };
    ```

&nbsp;

### Cart Controller

> **Location** : `./controller/cartController`
>
> **Parameters** : `(req,res,next)` where `req` is the request, `res` is the response and `next` is the next middleware in the function call.

1.  **addCart**

    > **Return** : Returns success if it adds the corresponding to the cart if not already present else it just updates the currently set quantity of the product else in case of failed execution, it returns an error.

    ```
    exports.addCart = async(req,res,next)=>{

    };
    ```

2.  **clearCart**

    > **Return** : Returns a success message if it successfully clears the cart ie making the cart empty else returns an eror.

    ```
    exports.clearCart = async(req,res,next)=>{

    };
    ```

3.  **cartSaveChanges**

    > **Returns** : Returns success message upon successfully saving the changed values in the database else returns an error.

    ```
    exports.cartSaveChanges = (req,res,next) => {

    };
    ```

4.  **addAllFromSmart**

    > **Returns** : Returns success message upon successfully adding all items from the user's order histroy directly into the cart else returns an error.

    ```
    exports.addAllFromSmart = async (req,res,next)=>{

    };
    ```

&nbsp;

### View Controller

> **Location** : `./controller/viewController`
>
> **Parameters** : `(req,res,next)` where `req` is the request, `res` is the response and `next` is the next middleware in the function call.

> **View Controller** uses **PUG** templating library to render the webpages. **PUG** documentation : https://pugjs.org/api/getting-started.html

1.  **home**

    > **Return** : Renders the landing page of the website which fetches data from the following **URLs** :
    >
    > **Recommendations** : `https://smart-groceries.herokuapp.com/productRecommendation?userId=${req.user.userId}`
    >
    > **All Products** : `https://smart-groceries.herokuapp.com/getProductList`

    ```
    exports.home = async(req,res,next)=>{

    };
    ```

2.  **cart**

    > **Return** : Renders the cart page which fetches data from **User's** information in the database using the attribute **req.user.inCart**.

    ```
    exports.cart = async(req,res,next)=>{

    };
    ```

3.  **previousOrder**

    > **Returns** : Renders the page which contains previous orders of the user and it fetch data from the **URL**:
    >
    > **Previous order history** : `https://smart-groceries.herokuapp.com/getUserOrderHistory?userId=${req.user.userId}`

    ```
    exports.previousOrder = (req,resmnext) => {

    };
    ```

4.  **about**

    > **Returns** : Renders about info of the team and shows static data

    ```
    exports.about = async (req,res,next)=>{

    };
    ```

5.  **loginPage**

    > **Returns** : Renders login page of the website.

    ```
    exports.loginPage = async (req,res,next)=>{

    };
    ```

6.  **signupPage**

    > **Returns** : Renders signup page of the website.

    ```
    exports.signupPage = async (req,res,next)=>{

    };
    ```

7.  **forgotPassword**

    > **Returns** : Renders forgot password page of the website.

    ```
    exports.forgotPassword = async (req,res,next)=>{

    };
    ```

8.  **resetPassword**

    > **Returns** : Renders reset password page of the website.

    ```
    exports.resetPassword = async (req,res,next)=>{

    };
    ```

&nbsp;
