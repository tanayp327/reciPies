<div class="dropdown">
  <button class="dropdown-button">Select Options</button>
  <div class="dropdown-content">
    <input type="checkbox" id="Vegan">
    <label for="Vegan">Vegan</label><br><br>
    <input type="checkbox" id="Vegetarian">
    <label for="Vegetarian">Vegetarian</label><br><br>
    <input type="checkbox" id="Gluten Free">
    <label for="Gluten Free">Gluten Free</label><br><br>
    <input type="checkbox" id="Lactose Intolerant">
    <label for="Lactose Intolerant">Lactose Intolerant</label><br><br>
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