---
toc: False
comments: False
layout: default
title: Login
description: Login Page
---
<h1>Login</h1>

<style>
    form {
        max-width: 300px; /* Adjust the width as needed */
        margin: 0 auto; /* Center the form on the page */
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Box shadow for a subtle effect */
        padding: 20px;
        border-radius: 8px; /* Add rounded corners for a modern look */
    }

    input {
        width: 100%;
        padding: 10px;
        margin-bottom: 15px;
        box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.1); /* Inner glow effect for input fields */
        border: 1px solid #ccc;
        border-radius: 4px;
        transition: box-shadow 0.3s ease; /* Add transition for a smooth effect */
    }

    input:focus {
        outline: none; /* Remove default focus outline */
        box-shadow: 0 0 10px rgba(0, 0, 255, 0.5); /* Change box shadow on focus for emphasis */
    }

    button {
        background-color: #4CAF50;
        color: white;
        padding: 10px 15px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        box-shadow: 0 0 10px rgba(0, 128, 0, 0.5); /* Box shadow for the button */
        transition: box-shadow 0.3s ease; /* Add transition for a smooth effect */
    }

    button:hover {
        box-shadow: 0 0 15px rgba(0, 128, 0, 1); /* Change box shadow on hover for emphasis */
    }
</style>

<!-- Your existing HTML form goes here -->
<form action="javascript:login_user()">
    <!-- ... -->
</form>

<script type="module">
    // Your existing JavaScript code goes here
</script>

<form action="javascript:login_user()">
    <p><label>
        User ID:
        <input type="text" name="uid" id="uid" required="" />
    </label></p>
    <p><label>
        Password:
        <input type="password" name="password" id="password" required="" />
    </label></p>
    <p>
        <button>Login</button>
    </p>
    <p id="loginStatus" name="loginStatus">null</p>
</form>

<!-- 
Below JavaScript code is designed to handle user authentication in a web application. It's written to work with a backend server that uses JWT (JSON Web Tokens) for authentication.

The script defines a function when the page loads. This function is triggered when the Login button in the HTML form above is pressed. 
 -->
<script type="module">
    // uri variable and options object are obtained from config.js


    function login_user(){
        // Set Authenticate endpoint
        const url ='http://127.0.0.1:8086/api/users/authenticate';

        // Set the body of the request to include login data from the DOM
        const body = {
            uid: document.getElementById("uid").value,
            password: document.getElementById("password").value,
        };

        // Change options according to Authentication requirements
        const authOptions = {
            mode: 'cors', // no-cors, *cors, same-origin
            credentials: 'include', // include, same-origin, omit
            headers: {
                'Content-Type': 'application/json',
            },
            method: 'POST', // Override the method property
            cache: 'no-cache', // Set the cache property
            body: JSON.stringify(body)
        };

        // Fetch JWT
        fetch(url, authOptions)
        .then(response => {
            // handle error response from Web API
            if (!response.ok) {
                const errorMsg = 'Login error: ' + response.status;
                console.log(errorMsg);
                if (response.status == 500) {
                    document.getElementById("loginStatus").innerHTML = "incorrect username or password";
                    return;
                }
            }
            
            // Success!!!
            // Redirect to the database page
            window.location.href = "http://127.0.0.1:4200/student/2024/01/30/DataTable.html"
            ;
        })
        // catch fetch errors (ie ACCESS to server blocked)
        .catch(err => {
            window.location.href = "http://127.0.0.1:4200/student/2024/01/31/403error.html"
            console.error(err);
        });
    }

    // Attach login_user to the window object, allowing access to form action
    window.login_user = login_user;
</script>
