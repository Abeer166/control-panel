# control-panel
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>   control panel</title>
--------CSS------------------------
<style>
body {
  background-image: url('A2.jpeg');
}

.center {
  margin: auto;
  width: 20%;
  padding: 2px;
}

.slider {
  -webkit-appearance: none;
  width: 100%;
  height: 10px;
  border-radius: 5px;
  background: #d3d3d3;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
}
.slider:hover {
  opacity: 1;
}
.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 23px;
  height: 24px;
  border: 0;
  background: url('contrasticon.jpeg');
  cursor: pointer;
}
.slider::-moz-range-thumb {
  width: 23px;
  height: 24px;
  border: 0;
  background: url('contrasticon.jpeg');
  cursor: pointer;
}
</style>
</style>
</head>
-------------HTML----------------
//<body>

<form action="control.php" method="POST">
 <body>
<div class="center">

 <h4>control panel</h4></div><br/>
  <div class="center">

motor1  <input id="myRange" name="m1" type="range"
 min="0" max="180" step="10" value="0" class="slider"
  /> <p>Value: <span id="demo"></span></p></div><br/>


 <div class="center">
motor2  <input id="m2" name="m2" type="range"
 min="0" max="180" step="10" value="0" class="slider"
  /> <p>Value: <span id="m2m"></span></p></div><br/>

 <div class="center">

//motor3  <input id="m3" name="m3" type="range"
 min="0" max="180" step="10" value="0" class="slider"
  /><p>Value: <span id="mm"></span></p></div><br/>

 <div class="center">

motor4 <input id="m4" name="m4" type="range"
 min="0" max="180" step="10" value="0" class="slider"
  /><p>Value: <span id="m4m"></span></p></div><br/>

 <div class="center">

motor5  <input id="m5" name="m5" type="range"
 min="0" max="180" step="10" value="0" class="slider"
  /><p>Value: <span id="m5m"></span></p></div>

 <div class="center">

  motor6 <input id="m6" name="m6" type="range"
  min="0" max="180" step="10" value="0" class="slider"
   /><p>Value: <span id="m6m"></span></p></div>
  <div class="center">
  <input type="submit" value="save">
</div><br/>
----------------JS---------------------------
<script>
var slider = document.getElementById("myRange");
var output = document.getElementById("demo");
var slider2 = document.getElementById("m2");
var output2 = document.getElementById("m2m");
var slider3 = document.getElementById("m3");
var output3 = document.getElementById("mm");
var slider4 = document.getElementById("m4");
var output4 = document.getElementById("m4m");
var slider5 = document.getElementById("m5");
var output5 = document.getElementById("m5m");
var slider6 = document.getElementById("m6");
var output6 = document.getElementById("m6m");
output.innerHTML = slider.value;

slider.oninput = function() {
  output.innerHTML = this.value;
}
output2.innerHTML = slider2.value;

slider2.oninput = function() {
  output2.innerHTML = this.value;
}
output3.innerHTML = slider3.value;

slider3.oninput = function() {
  output3.innerHTML = this.value;
}
output4.innerHTML = slider4.value;

slider4.oninput = function() {
  output4.innerHTML = this.value;
}
output5.innerHTML = slider5.value;

slider5.oninput = function() {
  output5.innerHTML = this.value;
}
output6.innerHTML = slider6.value;

slider6.oninput = function() {
  output6.innerHTML = this.value;
}
</script>
</body>
</form>
</html>
Connect the database with html by php
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
<img width="1437" alt="Screen Shot 1442-11-17 at 5 47 38 PM" src="https://user-images.githubusercontent.com/56722657/123677378-b5da5c00-d84d-11eb-96b1-708d0c07b2fb.png">


<img width="1321" alt="Screen Shot 1442-11-17 at 5 56 51 PM" src="https://user-images.githubusercontent.com/56722657/123549430-a554b380-d771-11eb-9d88-9d607ea84f50.png">



