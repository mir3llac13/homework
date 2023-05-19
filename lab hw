
<!DOCTYPE html>
<html>
<head>
    <title>Student Registration</title>
</head>
<body>
    <h2>Student Registration Form</h2>
    <form method="POST" action="process_form.php">
        <label for="full_name">Full Name:</label>
        <input type="text" name="full_name" required><br><br>
        
        <label for="email">Email Address:</label>
        <input type="email" name="email" required><br><br>
        
        <label>Gender:</label><br>
        <input type="radio" name="gender" value="Male" required>
        <label for="gender_male">Male</label><br>
        <input type="radio" name="gender" value="Female" required>
        <label for="gender_female">Female</label><br><br>
        
        <input type="submit" value="Submit">
    </form>
</body>
</html>

<?php
// Establish database connection
$servername = "localhost";
$username = "your_username";
$password = "your_password";
$dbname = "your_database_name";

$conn = new mysqli($servername, $username, $password, $dbname);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Retrieve form data
$full_name = $_POST['full_name'];
$email = $_POST['email'];
$gender = $_POST['gender'];

// Validate form data
if (empty($full_name) || empty($email) || empty($gender)) {
    die("Please fill in all required fields.");
}

// Insert data into the database
$sql = "INSERT INTO students (full_name, email, gender) VALUES ('$full_name', '$email', '$gender')";

if ($conn->query($sql) === TRUE) {
    echo "Registration successful!";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}

// Close the database connection
$conn->close();
?>

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(255),
    email VARCHAR(255),
    gender ENUM('Male', 'Female')
);



