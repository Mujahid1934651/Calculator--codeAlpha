# Calculator--codeAlpha




<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
    <link rel="stylesheet" type="text/css" href="style.css">
    <h1>CALCULATOR</h1>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display"  disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendValue('/')">/</button>
            <button onclick="appendValue('*')">*</button>
            <button onclick="appendValue('-')">-</button>
            <button onclick="appendValue('+')">+</button>
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('0')">0</button>
            <button onclick="calculateResult()">=</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

.calculator {
    width: 200px;
    margin: 200px auto;
background-color:black;
    padding: 10px;
    border: 10px solid green;
    border-radius: 20px;
    box-shadow: 7 0 10px rgba(0, 0, 0, 0.1);
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    width: 100%;
    height: 40px;
    font-size: 20px;
    cursor: pointer;
}

input[type="text"]

{
    background-color:white;
    
    
    
}



let displayValue = '';

function appendValue(value) {
    displayValue += value;
    document.getElementById('display').value = displayValue;
}

function clearDisplay() {
    displayValue = '';
    document.getElementById('display').value = displayValue;
}

function deleteLast() {
    displayValue = displayValue.slice(0, -1);
    document.getElementById('display').value = displayValue;
}

function calculateResult() {
    try {
        const result = eval(displayValue);
        displayValue = result.toString();
        document.getElementById('display').value = displayValue;
    } catch (error) {
        displayValue = 'Error';
        document.getElementById('display').value = displayValue;
    }
}

