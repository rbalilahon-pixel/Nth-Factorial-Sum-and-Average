<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>JS Loops Calculator</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #0d0d0d;
        color: #fff;
        text-align: center;
        padding: 40px;
    }
    .container {
        width: 450px;
        margin: auto;
        background: #1a1a1a;
        padding: 25px;
        border-radius: 18px;
        box-shadow: 0 0 15px #00eaff;
        border: 2px solid #00eaff;
    }
    h2 {
        color: #00eaff;
        text-shadow: 0 0 10px #00eaff;
    }
    input {
        width: 80%;
        padding: 10px;
        border-radius: 10px;
        border: none;
        outline: none;
        font-size: 18px;
        margin-bottom: 15px;
        text-align: center;
    }
    button {
        width: 85%;
        padding: 12px;
        background: #00eaff;
        border: none;
        border-radius: 12px;
        color: #000;
        font-size: 18px;
        cursor: pointer;
        font-weight: bold;
        transition: 0.3s;
    }
    button:hover {
        background: #0099cc;
        box-shadow: 0 0 10px #00eaff;
    }
    .result {
        margin-top: 20px;
        background: #111;
        padding: 15px;
        border-radius: 10px;
        text-align: left;
        line-height: 1.8;
        border-left: 4px solid #00eaff;
    }
</style>
</head>
<body>

<div class="container">
    <h2>Loop Operations Calculator</h2>

    <input type="number" id="num" placeholder="Enter an integer value n">

    <button onclick="compute()">Compute Results</button>
    
    <div class="result" id="output"></div>
</div>

<script>
function compute() {
    let n = parseInt(document.getElementById("num").value);

    if (isNaN(n) || n < 1) {
        document.getElementById("output").innerHTML = "Please enter a valid positive integer.";
        return;
    }

    // 1. Factorial using WHILE loop
    let factorial = 1;
    let i = 1;
    while (i <= n) {
        factorial *= i;
        i++;
    }

    // 2. Sum using DO WHILE loop
    let sum = 0;
    let j = 1;
    do {
        sum += j;
        j++;
    } while (j <= n);

    // 3. Average using FOR loop
    let total = 0;
    for (let k = 1; k <= n; k++) {
        total += k;
    }
    let average = total / n;

    // Display results
    document.getElementById("output").innerHTML = `
        <b>Results for n = ${n}:</b><br><br>
        <b>1. Factorial (While Loop):</b> ${factorial}<br>
        <b>2. Sum of First n Numbers (Do While Loop):</b> ${sum}<br>
        <b>3. Average (For Loop):</b> ${average.toFixed(2)}
    `;
}
</script>

</body>
</html>
