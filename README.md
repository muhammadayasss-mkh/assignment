<!DOCTYPE html>
<html>
<head>
    <title>Form Validation</title>
</head>
<body>

<h2>Registration Form</h2>

<form onsubmit="return validateForm()">

    Name: <br>
    <input type="text" id="name"><br><br>

    Email: <br>
    <input type="text" id="email"><br><br>

    Password: <br>
    <input type="password" id="password"><br><br>

    Confirm Password: <br>
    <input type="password" id="cpassword"><br><br>

    Mobile Number: <br>
    <input type="text" id="mobile"><br><br>

    <input type="submit" value="Register">

</form>

<script>
function validateForm() {

    var name = document.getElementById("name").value;
    var email = document.getElementById("email").value;
    var password = document.getElementById("password").value;
    var cpassword = document.getElementById("cpassword").value;
    var mobile = document.getElementById("mobile").value;

    // Name not empty
    if (name == "") {
        alert("Name must not be empty");
        return false;
    }

    // Email must contain @ and .
    if (email.indexOf("@") == -1 || email.indexOf(".") == -1) {
        alert("Enter valid email");
        return false;
    }

    // Password minimum 6 characters
    if (password.length < 6) {
        alert("Password must be at least 6 characters");
        return false;
    }

    // Confirm password match
    if (password != cpassword) {
        alert("Passwords do not match");
        return false;
    }

    // Mobile number exactly 10 digits
    if (mobile.length != 10 || isNaN(mobile)) {
        alert("Mobile number must be exactly 10 digits");
        return false;
    }

    alert("Registration Successful!");
    return true;
}
</script>

</body>
</html>
