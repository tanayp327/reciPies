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
    // const url = "https://recipies.duckdns.org/api/users"
    const url = "http://127.0.0.1:8086/api/users"
    //const url = "https://flask.nighthawkcodingsociety.com/api/users"
    const create_fetch = url + '/create';
    const read_fetch = url + '/';
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
                alert(response.status);
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
                //Construct Table header
                const tr = document.createElement("tr");
                const col1 = document.createElement("td");
                const col2 = document.createElement("td")
                const col3 = document.createElement("td");
                const col4 = document.createElement("td");        
                // obtain data that is specific to the API
                col1.innerHTML = "<span style='font-weight:bold'>Recipe Name</span>"; 
                col2.innerHTML = "<span style='font-weight:bold'>Review</span>";
                col3.innerHTML = "<span style='font-weight:bold'>Rating</span>"; 
                col4.innerHTML = "<span style='font-weight:bold'>User Name</span>";         
                // add HTML to container
                tr.appendChild(col1);
                tr.appendChild(col2);
                tr.appendChild(col3);
                tr.appendChild(col4);        
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
    function add_row(data) {
        const tr = document.createElement("tr");
        const rname = document.createElement("td");
        const comment = document.createElement("td")
        const rating = document.createElement("td");
        const uid = document.createElement("td");        
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
        resultContainer.appendChild(tr);
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
    function favorite_recipe(id) {
        if (!id) {
            alert("Error: recipe ID not provided!")
            return;
        }
        var recipe = recipies[id];
        var title = recipe[2];
        var ingredients = recipe[1];
        var instructions = recipe[0];
        fetch("http://192.168.7.177:8086/api/favorites/favorites", {
            "method": "POST",
            "headers": {
                "content-type": "application/json"
            },
            "body": JSON.stringify({
                "title": title,
                "ingredients": ingredients,
                "instructions": instructions
            })
        }).then(Response => {
            Response.json().then(Data => {
            }).catch(E => {
                alert("Error: unable to add recipe to favorites!")
            })
        }).catch(E => {
            alert("Error: unable to add recipe to favorites!")
        })
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
        // fetch("https://recipies.duckdns.org/api/search/", {
        fetch("http://127.0.0.1:8086/api/search/", {
            "method": "POST",
            "headers": {
                "content-type": "application/json"
            },
            "body": JSON.stringify({
                "item": content
            })
        }).then(Response => {
            // alert("after fetching search results..in response");
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
                                <button onclick="favorite_recipe('${instruction_id}');" id="favoriteButton"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-fill" viewBox="0 0 16 16">
  <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
</svg> favorite</button>
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
            alert("catch 2");            
            document.getElementById("results").innerHTML = "We found no items for this query!";
        })
    })
</script>
</html>