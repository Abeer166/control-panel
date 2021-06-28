------------------PHP------------------------
<?php

if ($_SERVER["REQUEST_METHOD"] == "POST") {
$m1 = $_POST["m1"];
$m2 = $_POST["m2"];
$m3 = $_POST["m3"];
$m4 = $_POST["m4"];
$m5 = $_POST["m5"];
$m6 = $_POST["m6"];

}
//To link in database...
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "control";

// make Contact
$conn = mysqli_connect($servername, $username, $password, $dbname);
// test the Contact
if (!$conn) {
die("Connection failed: " . mysqli_connect_error());
}

$sql = "INSERT INTO mytable (m1, m2, m3 ,m4,m5,m6)
VALUES ('$m1', '$m2', '$m3' , '$m4','$m4','$m6')";

if (mysqli_query($conn, $sql)) {
echo "The information has been sent successfully";
} else {
echo "Error: " . $sql . "<br>" . mysqli_error($conn);
}

mysqli_close($conn);

?>
