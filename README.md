# Sprint2
activity diagram register
<?php
session_start();

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
  // Retrieve the username and password from the form
  $username = $_POST['username'];
  $password = $_POST['password'];

  // TODO: Validate the username and password with your backend database

  if ($username === 'myusername' && $password === 'mypassword') {
    // Authentication succeeded
    $_SESSION['loggedin'] = true;
    $_SESSION['username'] = $username;
    header('Location: dashboard.php');
  } else {
    // Authentication failed
    $_SESSION['loggedin'] = false;
    $error_message = 'Invalid username or password';
  }
}
?>

<!DOCTYPE html>
<html>
<head>
  <title>Login</title>
</head>
<body>
  <h1>Login</h1>

  <?php if (isset($error_message)): ?>
    <p><?php echo $error_message; ?></p>
  <?php endif; ?>

  <form method="POST" action="">
    <label>Username:</label>
    <input type="text" name="username" required><br>

    <label>Password:</label>
    <input type="password" name="password" required><br>

    <button type="submit">Login</button>
  </form>
</body>
</html>

egenerate response
