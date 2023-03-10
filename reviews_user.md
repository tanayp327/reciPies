<html>
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Form</title>
    <style>      
        @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
        body {
        font-family: "Poppins", sans-serif;
        background-color: #f6f6ef;
        }
        .main-container {
            border: 1px solid #c3c3c3;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            width: 100%;
        }
       .result {
            border-radius: 12px;
            border: 1px solid black;
            padding: 20px;
            max-width: 300px;
            flex-shrink: 0;
        }
        input {
            background: black;
            border: 2px solid transparent;
            outline: none;
            border-radius: 50px;
            padding-left: 10px;
            padding-right: 20px;
            padding-top: 5px;
            padding-bottom: 5px;
            color: #fff;
            transition: 0.2s;
        }
        input:focus {
            background-color: #fff;
            color: black;
            border: 2px solid black;
        }
        .lds-roller {
            display: inline-block;
            position: relative;
            width: 80px;
            height: 80px;
        }
        .lds-roller div {
            animation: lds-roller 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
            transform-origin: 40px 40px;
        }
        .lds-roller div:after {
            content: " ";
            display: block;
            position: absolute;
            width: 7px;
            height: 7px;
            border-radius: 50%;
            background: black;
            margin: -4px 0 0 -4px;
        }
        .lds-roller div:nth-child(1) {
            animation-delay: -0.036s;
        }
        .lds-roller div:nth-child(1):after {
            top: 63px;
            left: 63px;
        }
        .lds-roller div:nth-child(2) {
            animation-delay: -0.072s;
        }
        .lds-roller div:nth-child(2):after {
            top: 68px;
            left: 56px;
        }
        .lds-roller div:nth-child(3) {
            animation-delay: -0.108s;
        }
        .lds-roller div:nth-child(3):after {
            top: 71px;
            left: 48px;
        }
        .lds-roller div:nth-child(4) {
            animation-delay: -0.144s;
        }
        .lds-roller div:nth-child(4):after {
            top: 72px;
            left: 40px;
        }
        .lds-roller div:nth-child(5) {
            animation-delay: -0.18s;
        }
        .lds-roller div:nth-child(5):after {
            top: 71px;
            left: 32px;
        }
        .lds-roller div:nth-child(6) {
            animation-delay: -0.216s;
        }
        .lds-roller div:nth-child(6):after {
            top: 68px;
            left: 24px;
        }
        .lds-roller div:nth-child(7) {
            animation-delay: -0.252s;
        }
        .lds-roller div:nth-child(7):after {
            top: 63px;
            left: 17px;
        }
        .lds-roller div:nth-child(8) {
            animation-delay: -0.288s;
        }
        .lds-roller div:nth-child(8):after {
            top: 56px;
            left: 12px;
        }
        @keyframes lds-roller {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        button {
            background: black;
            border: 2px solid transparent;
            outline: none;
            border-radius: 50px;
            padding-left: 20px;
            padding-right: 20px;
            padding-top: 5px;
            padding-bottom: 5px;
            color: #fff;
            cursor: pointer;
            transition: 0.2s;
        }
        button:hover {
            background-color: #fff;
            color: black;
            border: 2px solid black;
        }
        #results {
            max-height: 500px;
            overflow: auto;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        #favoriteButton {
            background-color: yellow;
            color: black;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 5px;
            margin-top: 10px;
        }
        #nav {
            position: fixed;
            height: 100px;
            width: 100%;
            background-color: black;
            top: 0px;
            left: 0px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: inset;
        }
        p {
            font-size: 12px;
        }
        #instructions {
            display: none;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            max-width: 400px;
            border: 1px solid black;
            border-radius: 12px;
            padding: 20px;
        }
        #search_page {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        #review_page {
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
    </style>
</head>

<body>
    <!-- <div class="main-container"> -->
    <div id="search_page">
        <h1>What would you like to cook?</h1>
        <div>
            <input id="searchBar" type="text" placeholder="Type here">
            <button id="searchButton">Search</button>
        </div>
        <br>
        <div id="results">
        </div>
    </div>
    <div id="instructions">
        <button onclick="return_to_search();">Return To Search</button>
        <h1>Instructions</h1>
        <br>
        <b>You will need: </b>
        <p id="youWillNeed"></p>
        <br>
        <b>Method: </b>
        <p id="method"></p>
    </div>
    <div id="review_page">
        <button onclick="return_to_search();">Return To Search</button>
        <h1>Leave a Comment & Rating</h1>
        <div>
            <input type="hidden" id="id" name="id" readonly>        
            <b>You are reviewing: </b>
            <input type="text" id="recipe" name="recipe" readonly>
            <b>Rating: </b>
            <input id="rating" type="text" placeholder="Rate out of 10">
            <b>Comment: </b>
            <input id="comment" type="text" placeholder="Add a short comment about your experience with this recipe">
            <b>User Name : </b>            
            <input id="name" type="text" placeholder=" ">
            <button id="submitReview" onclick="create_user()">Submit Review</button>
        </div>
        <br>
        <div id="result">
        </div>
    </div>
    <!-- </div> -->
</body>
<script>
    var logged_in = false;
    var recipies = {};
    const loadOnce = 0;
    ////////////////////////
      // prepare HTML result container for new output
    const resultContainer = document.getElementById("result");
    // prepare URL's to allow easy switch from deployment and localhost
    //const url = "http://localhost:8086/api/users"
    const url = "https://recipies.duckdns.org/api/users"
    // const url = "http://192.168.122.48:8086/api/users"
    //const url = "https://flask.nighthawkcodingsociety.com/api/users"
    const create_fetch = url + '/create';
    const read_fetch = url + '/';
    const delete_fetch = url + '/delete';  
    const update_fetch = url + '/update';    
    // Load users on page entry
    read_users();
    // Display User Table, data is fetched from Backend Database
    function read_users() {
        // prepare fetch options
        const read_options = {
        method: 'GET', // *GET, POST, PUT, DELETE, etc.
        mode: 'cors', // no-cors, *cors, same-origin
        cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
        credentials: 'omit', // include, *same-origin, omit
        headers: {
            'Content-Type': 'application/json'
        },        
        };
        // fetch the data from API
        fetch(read_fetch, read_options)
        // response is a RESTful "promise" on any successful fetch
        .then(response => {
            // check for response errors
            if (response.status !== 200) {
                const errorMsg = 'Database read error: ' + response.status;
                console.log(errorMsg);
                //alert(response.status);
                // const tr = document.createElement("tr");
                // const td = document.createElement("td");
                // td.innerHTML = errorMsg;
                // tr.appendChild(td);
                // resultContainer.appendChild(tr);
                return;
            }
            // valid response will have json data
            response.json().then(data => {
                console.log(data);
                resultContainer.innerHTML = ''
                //Construct Table header
                const tr = document.createElement("tr");
                const col1 = document.createElement("td");
                const col2 = document.createElement("td")
                const col3 = document.createElement("td");
                const col4 = document.createElement("td");  
                const col5 = document.createElement("td"); 
                const col6 = document.createElement("td");                                       
                // obtain data that is specific to the API
                col1.innerHTML = "<span style='font-weight:bold'>Recipe Name</span>"; 
                col2.innerHTML = "<span style='font-weight:bold'>Review</span>";
                col3.innerHTML = "<span style='font-weight:bold'>Rating</span>"; 
                col4.innerHTML = "<span style='font-weight:bold'>User Name</span>";  
                col5.innerHTML = "<span style='font-weight:bold'>Update</span>";   
                col6.innerHTML = "<span style='font-weight:bold'>Delete</span>";                     
                // add HTML to container
                tr.appendChild(col1);
                tr.appendChild(col2);
                tr.appendChild(col3);
                tr.appendChild(col4);    
                tr.appendChild(col5);   
                tr.appendChild(col6);                     
                resultContainer.appendChild(tr); 
                //Print Reviews               
                for (let row in data) {
                console.log(data[row]);
                add_row(data[row]);
                }
            })
        })
        // catch fetch errors (ie ACCESS to server blocked)
        .catch(err => {
        console.error(err);
        alert(err);
        // const tr = document.createElement("tr");
        // const td = document.createElement("td");
        // td.innerHTML = err;
        // tr.appendChild(td);
        // resultContainer.appendChild(tr);
        });
    }
    function create_user(){
        // alert("You are in create_user function..add to DB");
        // alert(document.getElementById("recipe").value);
        // alert(document.getElementById("name").value);
        flag = document.getElementById("id").value
        if (flag == 0) {
            // New data entry        
            const body = {
                uid: document.getElementById("name").value,
                rname: document.getElementById("recipe").value,
                comment: document.getElementById("comment").value,
                rating: document.getElementById("rating").value,
            };
            const requestOptions = {
                method: 'POST',
                body: JSON.stringify(body),
                headers: {
                    "content-type": "application/json",
                    'Authorization': 'Bearer my-token',
                },
            };
            document.getElementById("id").value = "";
            document.getElementById("name").value = "";
            //document.getElementById("recipe").value = "";
            document.getElementById("comment").value = "";
            document.getElementById("rating").value = "";
            // URL for Create API
            // Fetch API call to the database to create a new user
            fetch(create_fetch, requestOptions)
            .then(response => {
                // trap error response from Web API
                if (response.status !== 200) {
                const errorMsg = 'Invalid Input - Database create error: ' + response.status;
                console.log(errorMsg);
                alert(errorMsg);
                // const tr = document.createElement("tr");
                // const td = document.createElement("td");
                // td.innerHTML = errorMsg;
                // tr.appendChild(td);
                // resultContainer.appendChild(tr);
                return;
                }
                // response contains valid result
                response.json().then(data => {
                    console.log(data);
                    //add a table row for the new/created userid
                    add_row(data);
                })
            })
        }
        else{
            // update user record
            const body = {
            id: document.getElementById("id").value,
            comment: document.getElementById("comment").value,
            rating: document.getElementById("rating").value,
            uid: document.getElementById("name").value
            };
            const requestOptions = {
                method: ['PUT'],
                body: JSON.stringify(body),
                headers: {
                    "content-type": "application/json",
                    'Authorization': 'Bearer my-token',
                },
            }; 
            // alert("update_review- before fetch");            
            fetch(update_fetch, requestOptions)
            .then(response => {
                // trap error response from Web API
                if (response.status !== 200) {
                    const errorMsg = 'Invalid Input - Database Update error: ' + response.status;
                    console.log(errorMsg);
                    alert(errorMsg);
                    return;
                }
                // response contains valid result
                response.json().then(data => {
                    // alert("update_review- valid response");
                    // alert("Record updated");
                    resultContainer.innerHTML = ''
                    // Load users on page entry
                    read_users();
                    // alert("in update end- after update_row");
                    document.getElementById("id").value = ""
                    document.getElementById("comment").value = ""
                    document.getElementById("rating").value = ""
                    document.getElementById("name").value = ""
                })
            })
        }
    }
    function add_row(data) {
        const tr = document.createElement("tr");
        const rname = document.createElement("td");
        const comment = document.createElement("td")
        const rating = document.createElement("td");
        const uid = document.createElement("td"); 
        const update_col = document.createElement("td");
        const del_col = document.createElement("td");  
        const update_button = document.createElement('input');       
        update_button.type = "button";
        update_button.value = "Update";
        update_button.onclick = function() {update_review(data.id,data.rname,data.comment,data.rating,data.uid)};
        const delete_button = document.createElement('input');
        delete_button.type = "button";
        delete_button.value = "Delete";
        delete_button.onclick = function() {delete_review(data.id)};
        update_col.appendChild(update_button);
        del_col.appendChild(delete_button); 
        // obtain data that is specific to the API
        rname.innerHTML = data.rname; 
        comment.innerHTML = data.comment;
        rating.innerHTML = data.rating; 
        uid.innerHTML = data.uid;                
        // add HTML to container
        tr.appendChild(rname);
        tr.appendChild(comment);
        tr.appendChild(rating);
        tr.appendChild(uid);       
        tr.appendChild(update_col);    
        tr.appendChild(del_col);  
        resultContainer.appendChild(tr);
    }
    function delete_review(review_id){
        //alert(review_id);
        const body = {
            id: review_id,
        };
        const requestOptions = {
            method: 'DELETE',
            body: JSON.stringify(body),
            headers: {
                "content-type": "application/json",
                'Authorization': 'Bearer my-token',
            },
        };             
        fetch(delete_fetch, requestOptions)
        .then(response => {
            // trap error response from Web API
            if (response.status !== 200) {
            const errorMsg = 'Invalid Input - Database delete error: ' + response.status;
            console.log(errorMsg);
            alert(errorMsg);
            // const tr = document.createElement("tr");
            // const td = document.createElement("td");
            // td.innerHTML = errorMsg;
            // tr.appendChild(td);
            // resultContainer.appendChild(tr);
            return;
            }
            // response contains valid result
            response.json().then(data => {
                console.log(data);
                //alert(data);           
                //delete(data);
                // alert("Record deleted");
                resultContainer.innerHTML = ''
                // Load users on page entry
                read_users();
            })
        })
    }
    function update_review(id,rname,comment,rating,uid){
        // alert("update_review");
        // alert(id);
        document.getElementById("id").value = id;
        document.getElementById("recipe").value = rname;
        document.getElementById("comment").value = comment;
        document.getElementById("rating").value = rating; 
        document.getElementById("name").value = uid; 
        // update user record working code
        // const body = {
        //     id: id,
        //     comment: comment,
        //     rating: rating,
        //     uid: uid
        // };
        // const requestOptions = {
        //     method: ['PUT'],
        //     body: JSON.stringify(body),
        //     headers: {
        //         "content-type": "application/json",
        //         'Authorization': 'Bearer my-token',
        //     },
        // }; 
        // alert("update_review- before fetch");            
        // fetch(update_fetch, requestOptions)
        // .then(response => {
        //     // trap error response from Web API
        //     if (response.status !== 200) {
        //         const errorMsg = 'Invalid Input - Database Update error: ' + response.status;
        //         console.log(errorMsg);
        //         alert(errorMsg);
        //         return;
        //     }
        //     // response contains valid result
        //     response.json().then(data => {
        //         alert("update_review- valid response");
        //         alert("in update end- after update_row");
        //     })
        // }) 
    }
    /////////////////////
    function return_to_search() {
        document.getElementById("search_page").style["display"] = "flex";
        document.getElementById("instructions").style.display = "none";
        // document.getElementById("review_page").style["display"] = "none";
        document.getElementById("review_page").style.display = "none";
    };
    function open_instructions(object) {
        var instructions = recipies[object];
        document.getElementById("search_page").style["display"] = "none";
        document.getElementById("instructions").style.display = "flex";
        document.getElementById("review_page").style["display"] = "none";
        document.getElementById("youWillNeed").innerHTML = instructions[1];
        document.getElementById("method").innerHTML = instructions[0];
    };
    function addReview(id, name) {
        // alert("You are in addReview function");
        recipe.value = name;
        document.getElementById("search_page").style["display"] = "none";
        document.getElementById("review_page").style["display"] = "flex";
        inst_Id = id;
        // alert(inst_Id);
        // alert(name);
        context = this.context;
    }
    document.getElementById("searchButton").addEventListener("click", () => {
        // alert("seach button click");
        document.getElementById("results").style.overflow = "hidden";
        document.getElementById("results").innerHTML = `<div class="lds-roller"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>`;
        var content = document.getElementById("searchBar").value;
        // alert("b4 fetching search results");
        fetch("https://recipies.duckdns.org/api/search/", {
        // fetch("http://192.168.122.48:8086/api/search/", {
            "method": "POST",
            "headers": {
                "content-type": "application/json"
            },
            "body": JSON.stringify({
                "item": content
            })
        }).then(Response => {
            //alert("after fetching search results..in response");
            document.getElementById("results").style.overflow = "auto";
            recipies = {};
            Response.json().then(Data => {
                if (Data.length > 0) {
                    var html = ``;
                    Data.forEach((v) => {
                        var instruction_id = new Date().getTime().toString() + "_" + Math.random().toString();
                        recipies[instruction_id] = [v.instructions, v.ingredients, v.title]
                        html = html + `
                            <div class="result">
                                <b>${v.title}</b>
                                <p>${v.ingredients.replaceAll("|", "\n")}</p>
                                <button onclick="open_instructions('${instruction_id}')">View Instructions</button>
                                <button onclick="addReview('${instruction_id}', '${v.title}')">Review</button>
                            </div>
                        `
                    });
                    document.getElementById("results").innerHTML = html;
                } else {
                    alert("else 1");
                    document.getElementById("results").innerHTML = "We found no items for this query!";
                }
            }).catch(E => {
                alert("catch 1");
                document.getElementById("results").innerHTML = "We found no items for this query!";
            })
        }).catch(E => {
            alert("Our Server seems to be down, please try again later!");
            document.getElementById("results").innerHTML = "We found no items for this query!";
        })
    })
</script>
</html>