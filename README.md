# Second-task-in-web-path-

In continuation of the previous part, create a web page to display the stored data (last value) of the robot’s movement

A new file called last_movement has been added, which appears as an icon to be clicked to display the last movement made by the robot. 
___________________________________________________________________________________________________________________
Code :

<?php

$servername = "localhost";
$username = "root";
$password = "";
$DBname = "robot";
$conn = mysqli_connect($servername,$username,$password,$DBname);
if(!$conn){
    die("connection failed". mysqli_connect_error().'<br>');
}
else{
    echo 'conncted successfully <br>';
}

$sql = 'SELECT direction FROM robotmove ORDER BY id DESC LIMIT 1';
$result = mysqli_query($conn, $sql);

// Fetch the result
if(mysqli_num_rows($result) == 0){
    echo "the robot has not moved".'<br>';
}
else{
    $row = mysqli_fetch_assoc($result);
    echo $row['direction'];   
}
header ("Refresh: 2 ; url=index.html"); 
exit ; 
?>


code link >> ( C:\Users\nwaf1\Downloads\apache N\htdocs\robot\last_movmennt.php ) 
___________________________________________________________________________________________________________________

The information will be updated every two seconds and the web page will be back in control

The above code will display the last movement recorded in the robot’s database, and the value zero will be assigned if the robot does not move.


End..

*** Cout << " Thank you For reading " << endl ; ***
