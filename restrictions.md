<div class="dropdown">
  <button class="dropdown-button">Select Options</button>
  <div class="dropdown-content">
    <input type="checkbox" id="option1" name="option1" value="Option 1">
    <label for="option1">Vegan</label><br><br>
    <input type="checkbox" id="option2" name="option2" value="Option 2">
    <label for="option2">Vegetarian</label><br><br>
    <input type="checkbox" id="option3" name="option3" value="Option 3">
    <label for="option3">Gluten Free</label><br><br>
    <input type="checkbox" id="option4" name="option3" value="Option 3">
    <label for="option3">Lactose Intolerant</label><br><br>
  </div>
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</div>

<style>
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-button {
  background-color: #444;
  color: white;
  padding: 16px;
  border: none;
  cursor: pointer;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown-content input[type="checkbox"] {
  margin-right: 10px;
}

.dropdown:hover .dropdown-content {
  display: block;
}
</style>