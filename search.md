<body>
  <div class="main-container">
    <div class="search-container">
      <form>
        <input type="text" id="search-bar" placeholder="Search">
        <button type="submit" value="Submit" onclick="search()">Submit</button>
      </form>
    </div>
    <div class="result-container"></div>
  </div>
</body>
<script>
  function search() {
    var item = document.getElementById("search-bar").value;
    var xhr = new XMLHttpRequest();
    xhr.open("POST", "http:/192.168.7.177:8086/api/item/", true);
    xhr.setRequestHeader("Content-Type", "application/json");
    xhr.onreadystatechange = function() {
    if (xhr.readyState === XMLHttpRequest.DONE && xhr.status === 200) {
      var response = JSON.parse(xhr.responseText);
      console.log(response);
      var result = document.createElement("div");
      result.innerHTML = JSON.stringify(response)
      var resultContainer = document.querySelector(".result-container");
      resultContainer.appendChild(result);
    }
  };
    xhr.send(JSON.stringify({ item: item }));
    }
</script>
<style>
   body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
    }
  .search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 15vh;
    width: 75vh;
    border: none;
    padding: 20px;
  }
  #search-bar {
  padding: 10px;
  margin: 10px 0;
  width: 100%;
  border: 1px solid black;
  border-radius: 4px;
  }
  input[type="text"] {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 4px;
    margin: 8px 0;
    box-sizing: border-box;
    font-size: 16px;
  }
  button[type="submit"] {
    width: 100%;
    background-color: #0096e6;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    align-self: center;
  }
  button[type="submit"]:hover {
    background-color: #005f9c;
  }
</style>