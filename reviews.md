<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ReciPies</title>
    <style>
      @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
      body {
        font-family: 'Poppins', sans-serif;
      }
      header {
          background-color: #333;
          color: #fff;
          padding: 20px;
          font-size: 20px;
          display: flex;
          justify-content: center;
          align: center;
          text-align: center;
          width: 1400px;
          height: 75px;
          position: absolute;
          top: -10px;
        }
        header a {
          color: #fff;
          text-decoration: none;
          margin: 0 10px;
          align: center;
          font-size: 16px;
          padding: 10px;
        }
        header a:hover {
          text-decoration: underline;
        }
        header h1 {
          font-size: 24px;
          margin: 0;
          padding: 10px;
        }
        header h2 {
          font-size: 24px;
          margin: 0;
          padding: 10px;
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
        #favouriteButton {
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
    </style>
</head>
<body>
  <div class="main-container">
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
    <!-- <div id="review">
        <button onclick="return_to_search();">Return To Search</button>
        <h1>Review</h1>
        <br>
        <b>User Name: </b>
        <p id="userName"></p>
        <br>
        <b>Comments: </b>
        <p id="comments"></p>
    </div> -->
    <div id="recipe" style="display:none">
        <h2>Leave a Comment & Rating</h2>
        <div>
            <input id="rating" type="text" placeholder="Rate out of 10">
            <input id="comment" type="text" placeholder="Add a short comment about your experience with this recipe">
            <input id="name" type="text" placeholder="Name">
            <input id="email" type="text" placeholder="example@test.com">
            <button id="submitReview" onclick="addReview(this)">Submit Review</button>
        </div>
        <br>
        <div id="results">
        </div>
    </div>
<script>
    var logged_in = false;
    var recipies = {};
    function return_to_search() {
        document.getElementById("search_page").style["display"] = "flex";
        document.getElementById("instructions").style.display = "none";
    };
    function open_instructions(object) {
        var instructions = recipies[object];
        document.getElementById("search_page").style["display"] = "none";
        document.getElementById("instructions").style.display = "flex";
        document.getElementById("youWillNeed").innerHTML = instructions[1];
        document.getElementById("method").innerHTML = instructions[0];
    };
    /////////////////////////
    function add_review(object) {
        var T = document.getElementById("recipe");
        T.style.display = "block";
        /// var instructions = recipies[object];
        alert("review"); 
        document.getElementById("search_page").style["display"] = "none";
        document.getElementById("review").style.display = "flex";
        document.getElementById("userName").innerHTML = "Soham Kamat";
        document.getElementById("comments").innerHTML = "Excellent";
    };
    //sk code changes 
    // var loadOnce = 0;
    var context, title, ingredients, elem, instructions = null;
    // var correctguesses, incorrectguesses = [];
    // var bodyparts = 0;
    // var gameover = false;
    function debug(x) {
      document.getElementById("demo").innerHTML = x;
    }
    function updateState(res) {
        elem = document.getElementById('title');
        elem.innerHTML = res.title;
        elem = document.getElementById('ingredients');
        elem.innerHTML = res.ingredients;
        elem = document.getElementById('instructions');
        elem.innerHTML = res.instructions;
    }
    function addReview(id) {
        let msg = "";
        debug(msg);
        msg = "You are in addReview function";
        debug(msg);
        receipeId = id.value;
        alert(receipeId)
        context = this.context;
    }
    //////////////////////////////////
    function favourite_recipe() {
        if (!logged_in) {
            alert("You must be logged in!")
        } else {
        };
    }
    document.getElementById("searchButton").addEventListener("click", () => {
        document.getElementById("results").style.overflow = "hidden";
        document.getElementById("results").innerHTML = `<div class="lds-roller"><div></div><div></div><div></div><div></div><div></div><div></div><div></div><div></div></div>`;
        var content = document.getElementById("searchBar").value;
        fetch("https://recipies.duckdns.org/api/search/", {
            "method": "POST",
            "headers": {
                "content-type": "application/json"
            },
            "body": JSON.stringify({
                "item": content
            })
        }).then(Response => {
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
                                <button onclick="add_review('${instruction_id}')">Review</button>
                                <button onclick="favourite_recipe('${instruction_id}');" id="favouriteButton"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-fill" viewBox="0 0 16 16">
  <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
</svg> Favourite</button>        
                            </div>
                        `
                    });
                    document.getElementById("results").innerHTML = html;
                } else {
                    document.getElementById("results").innerHTML = "We found no items for this query!";
                }
            }).catch(E => {
                document.getElementById("results").innerHTML = "We found no items for this query!";
            })
        }).catch(E => {
            document.getElementById("results").innerHTML = "We found no items for this query!";
        })
    })
</script>
<br><br><br><br><br><br><br><br><br><br><br><br><br>