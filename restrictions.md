<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>recipies</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
        body {
            font-family: 'Poppins', sans-serif;
            justify-content: center;
            align-items: center;
            display: flex;
            flex-direction: column;
            width: 100vw;
            height: 100vh;
            margin: 0px;
            padding: 0px;
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

.dropdown-check-list {
  display: inline-block;
}

.dropdown-check-list .anchor {
  position: relative;
  cursor: pointer;
  display: inline-block;
  padding: 5px 50px 5px 10px;
  border: 1px solid #ccc;
}

.dropdown-check-list .anchor:after {
  position: absolute;
  content: "";
  border-left: 2px solid black;
  border-top: 2px solid black;
  padding: 5px;
  right: 10px;
  top: 20%;
  -moz-transform: rotate(-135deg);
  -ms-transform: rotate(-135deg);
  -o-transform: rotate(-135deg);
  -webkit-transform: rotate(-135deg);
  transform: rotate(-135deg);
}

.dropdown-check-list .anchor:active:after {
  right: 8px;
  top: 21%;
}

.dropdown-check-list ul.items {
  padding: 2px;
  display: none;
  margin: 0;
  border: 1px solid #ccc;
  border-top: none;
}

.dropdown-check-list ul.items li {
  list-style: none;
}

.dropdown-check-list.visible .anchor {
  color: #0094ff;
}

.dropdown-check-list.visible .items {
  display: block;
}


    </style>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
  <div class="main-container" id="recipieapp">
    <div id="search_page">
        <h1>Select your dietary restrictions:</h1>
        <h5>(To select multiple restrictions hold control while clicking options)</h5>
        <div>
            <form>
                <!-- <div id="list1" class="dropdown-check-list" tabindex="100">
                    <span class="anchor">Select Restrictions</span>
                    <ul class="items">
                        <li><input type="checkbox" value="Vegan" v-model="restrictions"/>Vegan </li>
                        <li><input type="checkbox" value="Vegetarian" v-model="restrictions"/>Vegetarian</li>
                        <li><input type="checkbox" v-model="restrictions"/>Gluten-Free </li>
                        <li><input type="checkbox" v-model="restrictions"/>Egg-Free </li>
                        <li><input type="checkbox" v-model="restrictions"/>Dairy-Free </li>
                        <li><input type="checkbox" v-model="restrictions"/>Soy-Free </li>
                        <li><input type="checkbox" v-model="restrictions"/>Tree-Nut-Free</li>
                        <li><input type="checkbox" v-model="restrictions"/>Peanut-Free</li>
                        <li><input type="checkbox" v-model="restrictions"/>Sugar-Free</li>
                        <li><input type="checkbox" v-model="restrictions"/>Kosher</li>
                        <li><input type="checkbox" v-model="restrictions"/>Keto</li>
                    </ul>
                </div> -->
                <select multiple type="checkbox" v-model="restrictions">
                <option>vegan </option>
                <option>vegetarian </option>
                <option>gluten-free </option>
                <option>egg-free </option>
                <option>dairy-free </option>
                <option>soy-free </option>
                <option>tree-nut-free </option>
                <option>peanut-free </option>
                <option>low-sugar </option>
                <option>kosher </option>
                <option>keto-friendly </option>
                </select>

                <br><br>
                <button v-on:click="searchIt" id="searchButton">Submit</button>
            </form>
        </div>
        <br>
        Currently Selected Restrictions: 
        {% raw %}
        <div id="results"> {{restrictions}}</div>
        {% endraw %}
    </div>
    <div id="instructions">
    </div>
  </div>
</body>
<script>

var app = new Vue({
    el: '#recipieapp',
    data: {
        restrictions: []
    },
    methods: {
        searchIt: function(){
            alert('will search for:' + this.restrictions)

            fetch("https://recipies.duckdns.org/api/dietsearch/", {
                "method": "POST",
                "headers": {
                    "content-type": "application/json"
                },
                "body": JSON.stringify({
                    "restrictions": this.restrictions
                })
            }).then(Response => {
                alert("Hurray!")
            })
        }
    }
});
<!-- var checkList = document.getElementById('list1'); -->
<!-- checkList.getElementsByClassName('anchor')[0].onclick = function(evt) { -->
  <!-- if (checkList.classList.contains('visible')) -->
    <!-- checkList.classList.remove('visible'); -->
  <!-- else -->
    <!-- checkList.classList.add('visible'); -->
<!-- } -->
</script>
