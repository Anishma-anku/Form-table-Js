# Form-table-Js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script>
        function publishToTable() {
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const age= document.getElementById('age').value;
            const contact= document.getElementById('contact').value;
            const error = document.getElementById('error');
            error.innerHTML = (!name || !email || !age || !contact) ? 'All values are required.' : '';
            if (name && email && age && contact) {
                const tableElement = document.getElementById('table');
                const trElement = document.createElement('tr');
                const tbodyElement = document.createElement('tbody');
                const nameEle = document.createElement('td');
                const emailEle = document.createElement('td');
                const ageEle = document.createElement('td');
                const contactEle = document.createElement('td');
                nameEle.innerHTML = name;
                emailEle.innerHTML = email;
                ageEle.innerHTML = age;
                contactEle.innerHTML = contact;


                trElement.appendChild(nameEle);
                trElement.appendChild(emailEle);
                trElement.appendChild(ageEle);
                trElement.appendChild(contactEle);

                tbodyElement.appendChild(trElement);
                tableElement.appendChild(tbodyElement);

                document.getElementById("name").value ="";
                document.getElementById("age").value ="";
                document.getElementById("email").value ="";
                document.getElementById("contact").value ="";
            }
        }
    </script>
    
    <body>
        
         <style>
            div.complete {
                position: fixed;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                padding: 10%;
                overflow: auto;
            }
    
            /* div.form {
                height: 500px;
            } */
    
            label {
                margin: 10px;
                display: block;
                font-size: 22px;
                font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans';
            }
    
            input {
                padding: 10px;
                width: 100%;
            }
    
            span {
                color: red;
                position: fixed;
                left: 50%;
                transform: translate(-50%, -50%);
            }
    
            button {
                padding: 10px;
                margin-top: 50px;
                left: 50%;
                position: fixed;
                transform: translate(-50%, -50%);
                font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans';
            }
    
            div#tables {
                margin-top: 100px;
                height: 300px;
                overflow: auto;
            }
    
            table,
            th,
            td {
                border: 1px solid red;
                border-collapse: collapse;
                font-size: 32px;
                font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans';
                padding: 10px;
            }
    
            th {
                width: 20%;
            }
        </style> 
        <div class="complete">
            <div class="form">
                <label>Name: </label><input id="name" type="text">
                <label>Email:</label> <input id="email" type="text"></label>
                <label>Age:</label> <input id="age" type="text"></label>
                <label>Contact:</label> <input id="contact" type="text"></label>
                <span id="error"></span>
                <button onclick="publishToTable()">Submit</button>
            </div>
            <div id="tables">
                <table id="table">
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Email</th>
                            <th>Age</th>
                            <th>Contact</th>
                        </tr>
                    </thead>
                </table>
            </div>
        </div>
    </body>
</head>

</html>
