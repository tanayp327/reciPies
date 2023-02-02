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
    margin-top: 30px;
  }
  input {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
    border: none;
    border-bottom: 2px solid #ccc;
    background-color: #f6f6ef;
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
        <button type="submit" value="Submit">Submit</button>
      </form>
          <div class="signup-link">
            <a href="signup">Don't have an account? Sign Up here!</a>
          </div>
        </div>
    </div>
</body>