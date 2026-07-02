# tracking-site <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Package Tracking</title>

<style>
body{
    font-family:Arial,sans-serif;
    background:#f4f6f8;
}
.container{
    max-width:600px;
    margin:60px auto;
    background:#fff;
    padding:30px;
    border-radius:10px;
    box-shadow:0 4px 12px rgba(0,0,0,.15);
}
input,button{
    width:100%;
    padding:14px;
    margin-top:12px;
    font-size:16px;
    box-sizing:border-box;
}
button{
    background:#0b5ed7;
    color:white;
    border:none;
    cursor:pointer;
}
button:hover{
    background:#084298;
}
.result{
    display:none;
    background:#eef7ff;
    padding:15px;
    margin-top:20px;
    border-radius:8px;
}
.error{
    display:none;
    color:red;
    margin-top:15px;
}
</style>

</head>
<body>

<div class="container">

<h1>Package Tracking</h1>

<p>Enter your package number.</p>

<input id="tracking" placeholder="Package Number">

<button onclick="trackPackage()">Track Package</button>

<div class="result" id="result">
<h2>Tracking Details</h2>

<p><strong>Package Number:</strong> <span id="number"></span></p>

<p><strong>Status:</strong> In Transit</p>

<p><strong>Destination Address:</strong></p>

<p>
153606700 Road<br>
Montrose, Colorado 81401
</p>

<p><strong>Estimated Delivery:</strong> Within 2–4 Business Days</p>

</div>

<div class="error" id="error">
Invalid Package Number.
</div>

</div>

<script>

const validPackages = ["000617"];

function trackPackage(){

let number = document.getElementById("tracking").value.trim();

if(validPackages.includes(number)){

document.getElementById("number").textContent = number;
document.getElementById("result").style.display = "block";
document.getElementById("error").style.display = "none";

}else{

document.getElementById("result").style.display = "none";
document.getElementById("error").style.display = "block";

}

}

</script>

</body>
</html>
