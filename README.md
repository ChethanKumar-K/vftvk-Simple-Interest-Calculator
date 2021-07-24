<!DOCTYPE html>
    <head>
    <title>Simple Interest calculator</title>
    <script src="script.js"></script>
    <link rel="stylesheet" type="text/css" href="style.css">
    </head>
    <body>
    <div class="maindiv">
        <h1>Simple Interest Calculator</h1>

        Amount <input type="number"  id="principal" onclick="validateamount()">  <br/>
        Rate <input type="range"  id="rate" min="1" max="20" step="0.25" value="10.25" onchange="updateRate()">  <br/>
        <span id="rate_val">10.25%</span>
        No. of Years <input type="number"  id="years">  <br/>
        <select id="years">
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
            <option value="6">6</option>
            <option value="7">7</option>
            <option value="8">8</option>
            <option value="9">9</option>
            <option value="10">10</option>
        </select>
        <button onclick="compute()">Compute Interest</button>
        <span id="result"></span><br>
        <footer>
            &#169; This calculator belongs to --Chethan--
        </footer>
    </div>
    </body>
</html>
body {background-color:black;font-family:arial;color:white}
h1{color:green;font-family:verdana}
.maindiv{
    background-color:white;
    color:black;
    width:300px;
    padding:20px;
    border-radius:25px;
    align:center;
}
function validateamount()
{
    var principal = document.getElementById("principal").value;
    var morethanzero = parseInt("principal")>0;
    if(!morethanzero)
    {
        alert("Enter a positive number");
        document.getElementById("principal").focus();
    }
}
function updateRate()
{
    var rateval = document.getElementById("rate").value;
    document.getElementById("rate_val").innerText=rateval+"%";
}

function compute()
{
    var principal = document.getElementById("principal").value;
    var rate = document.getElementById("rate").value;
    var years = document.getElementById("years").value;
    var interest = principal*years*rate/100;
    var year = newDate().getFullYear()+parseInt(years);
    document.getElementById("result").innerHTML="If you deposit <mark>"+principal+"<mark> <br>"+
    "at an interest <mark>"+rate+"%"+"</mark>,<br>"+
    "You will receive an interest of <mark>"+interest+"</mark>,<br>"+
    "In the year <mark>"+year+"</mark>";
}
