<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<body>
  <div class="main-container">
    <div class="search-container">
      <form>
        <input type="text" id="search-bar" placeholder="Search">
        <button type="submit" value="Submit" onclick="search()">Submit</button>
      </form>
    </div>
    <div class="result-container">
      <!-- placeholder for search results -->
    </div>
  </div>
</body>

<script>
  function search() {
  // get the value from the search bar
  var item = document.getElementById("search-bar").value.trim();

  // check if the search bar is empty
  if (!item) {
    alert("Please enter a search term");
    return;
  }

  // show a loading indicator or message
  var resultContainer = document.querySelector(".result-container");
  alert("Loading...");

  // make a POST request to the API
  fetch("http://recipies.duckdns.org/api/search/", {
    method: "POST",
    headers: {
      "Content-Type": "application/json"
    },
    body: JSON.stringify({ item: item })
  })
    .then(response => {
      if (!response.ok) {
        throw new Error("Network response was not ok");
      }
      return response.json();
    })
    .then(response => {
      // clear previous results
      resultContainer.innerHTML = "";

      // check if the API response is empty
      if (!response || !response.length) {
        alert("No results found");
        return;
      }

      // add each result to the container
      response.forEach(element => {
        var result = document.createElement("div");

        // sanitize the content to prevent XSS attacks
        result.textContent = element;
        resultContainer.appendChild(result);
        alert(element);
      });
    })
    .catch(error => {
      alert("Failed to make API call: " + error);
      alert("An error occurred while searching");
    });
}
</script>
<style>
  body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
  }
  .main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 5vh;
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
