<html>
  <head>
    <meta charset="UTF-8">
    <title>Sign Up</title>
    <style>
      .main-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin-top: -90px;
      }
      .signup-container {
        background-color: #262626;
        padding: 20px;
        margin-top: -90px;
        border-radius: 10px;
        box-shadow: 0px 0px 10px 0px #ccc;
        width: 400px;
        text-align: center;
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
        background-color: #0077ff;
        color: #fff;
        padding: 14px 20px;
        margin: 8px 0;
        border: none;
        border-radius: 4px;
        cursor: pointer;
      }
      button:hover {
        background-color: #0055cc;
      }
      .login-link a {
        color: #0077ff;
        text-align: center;
        display: block;
        text-decoration: underline;
      }
    </style>
  </head>
  <body>
    <div class="main-container">
      <div class="signup-container">
        <form id="signup-form">
          <h2>Sign Up</h2>
          <input type="text" id="name" placeholder="Name" required>
          <input type="text" id="username" placeholder="Username" required>
          <input type="password" id="password" placeholder="Password" required>
          <input type="password" id="confirm-password" placeholder="Confirm Password" required>
          <button type="submit">Submit</button>
        </form>
        <div class="login-link">
          <a href="login">Already have an account? Login here!</a>
        </div>
      </div>
    </div>
    <script>
      const form = document.getElementById('signup-form');
      form.addEventListener('submit', (event) => {
        event.preventDefault();
        const name = document.getElementById('name').value;
        const username = document.getElementById('username').value;
        const password = document.getElementById('password').value;
        const confirmPassword = document.getElementById('confirm-password').value;
        if (password !== confirmPassword) {
          alert('Passwords do not match');
          return;
        }
        const requestBody = {
          name: name,
          uid: username,
          password: password
        };
        fetch("http://192.168.7.177:8086/api/users/create", {
          method: 'POST',
          body: JSON.stringify(requestBody),
          headers: {
            'Content-Type': 'application/json'
          }
        })
        .then(response => {
          if (response.ok) {
            document.getElementById('name').value = '';
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
            document.getElementById('confirm-password').value = '';
            alert('User created successfully!');
          } else if (response.status === 409) {
            alert('Username already exists. Please choose a different username.');
          } else {
            throw new Error('Request failed.');
          }
        })
        .catch(error => console.error(error));
      });
    </script>
  </body>
</html>