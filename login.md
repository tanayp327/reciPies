<html>
  <head>
    <meta charset="UTF-8">
    <title>Login Form</title>
    <style>
      @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
      body {
        font-family: "Poppins", sans-serif;
        background-color: #f6f6ef;
      }
      .main-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }
      .login-container {
        background-color: #2E2E2E;
        padding: 20px;
        border-radius: 10px;
        height: 360px;
        width: 400px;
        align: auto;
        text-align: center;
        box-shadow: 0px 0px 10px 0px #ccc;
        color: #444;
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
        background-color: #f4f4f4;
        color: #444;
        font-family: "Poppins", sans-serif;
        box-shadow: 0px 2px 4px #888888;
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
        font-family: "Poppins", sans-serif;
      }
      button:hover {
        background-color: #3066be;
      }
      .signup-link a {
        color: #0070f3;
        text-align: center;
        display: block;
        font-family: "Poppins", sans-serif;
        text: 19px;
      }
    </style>
  </head>

  <body>
    <div class="main-container">
      <div class="login-container">
        <form>
          <h2>Login</h2>
          <input type="text" id="input-field" placeholder="Username" required>
          <input type="password" id="password-field" placeholder="Password" required>
          <button type="submit">Submit</button>
        </form>
        <div class="signup-link">
          <a href="signup">Don't have an account? Sign Up here!</a>
        </div>
      </div>
    </div>
  </body>
</html>