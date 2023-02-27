<html>
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
      header {
          background-color: #333;
          color: #fff;
          padding: 20px;
          font-size: 20px;
          display: flex;
          justify-content: center;
          align: center;
          text-align: center;
          width: 1400px;
          height: 75px;
          position: absolute;
          top: 0px;
        }
        header a {
          color: #fff;
          text-decoration: none;
          margin: 0 10px;
          align: center;
          font-size: 16px;
          padding: 10px;
        }
        header a:hover {
          text-decoration: underline;
        }
        header h1 {
          font-size: 24px;
          margin: 0;
          padding: 10px;
        }
        header h2 {
          font-size: 24px;
          margin: 0;
          padding: 10px;
        }
      .login-container {
        background-color: #2E2E2E;
        padding: 20px;
        border-radius: 10px;
        height: 300px;
        width: 400px;
        align: auto;
        text-align: center;
        box-shadow: 0px 0px 10px 0px #ccc;
        color: white;
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
        background-color: white;
        color: black;
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
      <form id="login-form">
        <h2>Login</h2>
        <input type="text" id="username-field" placeholder="Username" required>
        <input type="password" id="password-field" placeholder="Password" required>
        <button type="submit">Submit</button>
      </form>
      <div class="signup-link">
        <a href="signup">Don't have an account? Sign Up here!</a>
      </div>
    </div>
  </div>

  <script>
    const form = document.getElementById('login-form');

    form.addEventListener('submit', (e) => {
    e.preventDefault();

    const username = document.getElementById('username-field').value;
    const password = document.getElementById('password-field').value;

    fetch("http://127.0.0.1:8086/api/users/login", {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({ uid: username, password: password })
    })
    .then(response => response.json())
    .then(data => {
      if (data.status === 200) {
        alert('Login successful!');
        localStorage.setItem('loggedIn', 'true');
        localStorage.setItem('username', username); // Save the username to local storage
        window.location.href = '/';
      } else {
        alert('Login failed. Please check your username and password.');
      }
    })
    .catch(error => console.error(error));
  });

</script>
</body>
</html>