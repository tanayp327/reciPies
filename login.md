<style>
  body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
  }
  .main-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin-top: -150px;
  }
  .login-container {
    background-color: #201c1c;
    padding: 20px;
    border-radius: 10px;
    width: 400px;
    text-align: center;
    box-shadow: 0px 0px 10px 0px #ccc;
  }
  form {
    margin-top: 10px;
  }
  input {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
    border: none;
    border-bottom: 2px solid #ccc;
    background-color: #fff;
    color: #444;
  }
  button {
    width: 100%;
    background-color: #0070f3;
    color: #fff;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #3066be;
  }
  .signup-link a {
    color: #0070f3;
    text-align: center;
    display: block;
    text-decoration: underline;
  }
</style>


<body>
  <div class="main-container">
    <div class="login-container">
      <form>
        <h2>Login</h2>
        <input type="text" id="input-field" placeholder="Username" required>
        <input type="password" id = "password-field" placeholder="Password" required>
        <button type="submit" onclick="submitForm()">Submit</button>
      </form>
          <div class="signup-link">
            <a href="signup">Don't have an account? Sign Up here!</a>
          </div>
        </div>
    </div>
</body>

<script>
  
function submitForm() {
  const username = document.querySelector('#input-field').value;
  const password = document.querySelector('#password-field').value;

  const xhr = new XMLHttpRequest();
  xhr.open('POST', '/api/users/create', true);
  xhr.setRequestHeader('Content-Type', 'application/json');
  xhr.onload = function() {
    if (xhr.status === 200) {
      console.log(xhr.responseText);
    } else {
      console.error(xhr.responseText);
    }
  };
  xhr.send(JSON.stringify({
    name: username,
    password: password,
  }));
}
</script>
