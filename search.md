<body>
  <div class="main-container">
    <div class="search-container">
      <form>
        <input type="text" id="search-bar" placeholder="Search">
        <button type="submit" value="Submit">Submit</button>
      </form>
    </div>
  </div>
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</body>

<style>
  .search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 15vh;
    width: 75vh;
    background: ;
    padding: 20px;
  }

  #search-bar {
  padding: 10px;
  margin: 10px 0;
  width: 100%;
  border: 1px solid black;
  border-radius: 4px;
  }

  .search-form {
    display: flex;
    flex-direction: column;
    align-items: center;
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