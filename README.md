<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Football Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background:football no-repeat center center fixed;
            background-size: cover;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #fff;
        }

        .login-box {
            background: rgba(0, 0, 0, 0.7);
            padding: 40px;
            border-radius: 15px;
            text-align: center;
            width: 100%;
            max-width: 400px;
        }

        .input-field {
            margin: 15px 0;
        }

        .input-field input {
            width: 100%;
            padding: 15px;
            border: 1px solid #fff;
            border-radius: 5px;
            background: transparent;
            color: #fff;
            font-size: 16px;
        }

        .login-btn {
            width: 100%;
            padding: 15px;
            border: none;
            background-color: #ffcc00;
            color: #fff;
            font-size: 18px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }

        .login-btn:hover {
            background-color: #ff9900;
        }

    </style>
</head>
<body>
    <div class="login-box">
        <h2>Login</h2>
        <form id="loginForm">
            <div class="input-field">
                <input type="email" id="email" placeholder="Email" required>
            </div>
            <div class="input-field">
                <input type="password" id="password" placeholder="Password" required>
            </div>
            <button type="submit" class="login-btn">Log In</button>
        </form>
        <p id="message"></p>
    </div>

    <script>
        // Handle login functionality
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault();

            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            const userData = localStorage.getItem("userData");

            if (userData) {
                const user = JSON.parse(userData);

                if (user.email === email && user.password === password) {
                    // Redirect to the form page after successful login
                    window.location.href = 'form_page.html';
                } else {
                    document.getElementById('message').textContent = "Invalid login details!";
                }
            } else {
                document.getElementById('message').textContent = "No account found!";
            }
        });
    </script>
</body>
</html>
