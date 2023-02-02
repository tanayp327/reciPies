<body>
  <div class="main-container">
    <div class="search-container">
      <form>
        <input type="text" id="search-field" placeholder="Search">
        <button type="submit" value="Submit">Submit</button>
      </form>
    </div>
  </div>
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</body>

<style>
    .search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin: 10px auto;
    position: absolute;
    top: 20px;
    left: 50%;
    transform: translate(-50%, 0);
    }

    input[type="text"] {
    width: 100%;
    padding: 12px;
    border: none;
    border-radius: 4px;
    margin: 8px 0;
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
    }

    button[type="submit"]:hover {
    background-color: #005f9c;
}
</style>