---
toc: False
comments: False
layout: default
title: Data Table
description: Data Table
---

<h1>Data</h1>

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>ID</th>
        </tr>
    </thead>
    <tbody id="result">
    </tbody>
</table>

<script type="module">
    const url = 'http://127.0.0.1:8086/api/users/';
    // prepare HTML result container for new output
    const resultContainer = document.getElementById("result");
    const options = {
        mode: 'cors', // no-cors, cors, same-origin
        credentials: 'include', // include, same-origin, omit
        headers: {
            'Content-Type': 'application/json'
        },
        method: 'GET', // Override the method property
        cache: 'no-cache', // Set the cache property
    };

    // fetch the API
    fetch(url, options)
        // response is a RESTful "promise" on any successful fetch
        .then(response => {
            // check for response errors and display
            if (response.status !== 200) {
                const errorMsg = 'Database response error: ' + response.status;
                window.location.href = "http://127.0.0.1:4200/student/2024/01/31/403error.html";
                console.log(errorMsg);
                const tr = document.createElement("tr");
                const td = document.createElement("td");
                td.innerHTML = errorMsg;
                tr.appendChild(td);
                resultContainer.appendChild(tr);
                return;
            }
            // valid response will contain JSON data
            response.json().then(data => {
                console.log(data);
                for (const row of data) {
                    // tr and td build out for each row
                    const tr = document.createElement("tr");
                    const name = document.createElement("td");
                    const id = document.createElement("td");
                    // data is specific to the API
                    name.innerHTML = row.name;
                    id.innerHTML = row.uid;
                    // this builds td's into tr
                    tr.appendChild(name);
                    tr.appendChild(id);
                    // append the row to table
                    resultContainer.appendChild(tr);
                }
            })
            // catch fetch errors (i.e., ACCESS to server blocked)
            .catch(err => {
                window.location.href = "http://127.0.0.1:4200/student/2024/01/30/403error.html"
                console.error(err);
                const tr = document.createElement("tr");
                const td = document.createElement("td");
                td.innerHTML = err + ": " + url;
                tr.appendChild(td);
                resultContainer.appendChild(tr);
            ;
            });
        });
</script>

<button onclick="deleteUser()">Delete My Account</button>

<script>
    function deleteUser() {
        // You can add your logic for deleting the user here
        console.log("in function");
        const url = 'http://127.0.0.1:8086/api/users/';
        const options = {
            mode: 'cors', // no-cors, cors, same-origin
            credentials: 'include', // include, same-origin, omit
            headers: {
                'Content-Type': 'application/json'
            },
            method: 'DELETE', // Override the method property
            cache: 'no-cache', // Set the cache property
        };
        fetch(url, options)
        // response is a RESTful "promise" on any successful fetch
        .then(response => {
            // check for response errors and display
            if (response.status !== 200) {
                const errorMsg = 'Database response error: ' + response.status;
                window.location.href = "http://127.0.0.1:4200/student/2024/01/31/403error.html";
                console.log(errorMsg);
                const tr = document.createElement("tr");
                const td = document.createElement("td");
                td.innerHTML = errorMsg;
                tr.appendChild(td);
                resultContainer.appendChild(tr);
                return;
            }
            // valid response will contain JSON data
            response.json().then(data => {
                console.log("worked");
                console.log(data);
                 window.location.href = "http://127.0.0.1:4200/student/2024/01/30/DataTable.html";
            })
            // catch fetch errors (i.e., ACCESS to server blocked)
            .catch(err => {
                console.error(err);
                const tr = document.createElement("tr");
                const td = document.createElement("td");
                td.innerHTML = err + ": " + url;
                tr.appendChild(td);
                resultContainer.appendChild(tr);
            ;
            });
        });

        
    }
        
</script>

<label for="myTextField">Enter UID for user refrence</label>
<input type="text" id="uid" name="uid">

<label for="myTextField">Enter the new Password</label>
<input type="text" id="password" name="password">

<label for="myTextField">Enter the new name</label>
<input type="text" id="name" name="name">

<button type="button" onclick="update_user()">Update Account</button>


<script>
    function update_user(){
      const url = 'http://127.0.0.1:8086/api/users/';
      const body = {
        uid: document.getElementById("uid").value,
        password: document.getElementById("password").value,
        name: document.getElementById("name").value,
      };
      console.log(body);
      const AuthOptions = {
                  mode: 'cors', // no-cors, *cors, same-origin
                  credentials: 'include', // include, same-origin, omit
                  headers: {
                      'Content-Type': 'application/json',
                  },
                  method: 'PUT', // Override the method property
                  cache: 'no-cache', // Set the cache property
                  body: JSON.stringify(body)
              };
        // fetch the API
        fetch(url, AuthOptions)
          // response is a RESTful "promise" on any successful fetch
          .then(response => {
            // check for response errors and display
            if (response.status !== 200) {
                window.location.href = "http://127.0.0.1:4200/student/2024/01/31/403error.html";
            }
            // valid response will contain JSON data
            response.json().then(data => {
              // insert whatever code you want here
              window.location.href="http://127.0.0.1:4200/student/2024/01/30/DataTable.html"; // reload pge
            })
        })
        // catch fetch errors (ie ACCESS to server blocked)
        .catch(err => {
          console.log(err)
        });
    }
</script>