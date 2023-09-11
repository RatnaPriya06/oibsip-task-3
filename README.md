# oibsip-task-3
Converting temperature to Celsius or Fahrenheit

convertor.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="converter">
        <h1>Temperature Converter</h1>
        <label for="inputTemp">Enter Temperature:</label>
        <input type="number" id="inputTemp" placeholder="Enter temperature..." />
        <select id="inputUnit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
        </select>
        <button id="convertButton">Convert</button>
        <p id="result"></p>
    </div>
    <script src="script.js"></script>
</body>
</html>

styles.css

body {
    font-family: Arial, sans-serif;
    background-color: #020202;
    text-align: center;
    margin: 0;
    padding: 0;
}

.converter {
    background-color: #000000;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(255, 255, 255, 0.626);
    padding: 20px;
    margin: 100px auto;
    max-width: 500px;
}

h1 {
    color:#fff;
    font-size: 24px;
}

label {
    color:#fff;
    font-size: 18px;
}

input[type="number"] {
    width: 95%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #000000;
    border-radius: 5px;
}

select {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #000000;
    border-radius: 5px;
}

button {
    background-color: #0077ff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    font-size: 18px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

p#result {
    color:#fff;
    font-size: 24px;
    font-weight: bold;
    margin-top: 20px;
}

script.js

document.getElementById("convertButton").addEventListener("click", function() {
    // Get user input
    const inputTemp = parseFloat(document.getElementById("inputTemp").value);
    const inputUnit = document.getElementById("inputUnit").value;

    // Perform conversion
    let result;
    if (inputUnit === "celsius") {
        // Convert Celsius to Fahrenheit
        result = (inputTemp * 9/5) + 32;
    } else {
        // Convert Fahrenheit to Celsius
        result = (inputTemp - 32) * 5/9;
    }

    // Display the result
    document.getElementById("result").textContent = `Result: ${result.toFixed(2)}° ${inputUnit === "celsius" ? "Celsius" : "Fahrenheit"}`;
});
