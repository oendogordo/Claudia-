<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Científica</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .calculator {
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            background-color: #fff;
        }
        .display {
            width: 100%;
            height: 40px;
            margin-bottom: 10px;
            text-align: right;
            padding: 5px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
        .button {
            width: 50px;
            height: 50px;
            margin: 5px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button.operator {
            background-color: #f0ad4e;
            color: #fff;
        }
        .button.equal {
            background-color: #5cb85c;
            color: #fff;
        }
        .button.clear {
            background-color: #d9534f;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <button class="button clear" onclick="clearDisplay()">C</button>
        <button class="button" onclick="appendToDisplay('7')">7</button>
        <button class="button" onclick="appendToDisplay('8')">8</button>
        <button class="button" onclick="appendToDisplay('9')">9</button>
        <button class="button operator" onclick="appendToDisplay('+')">+</button>
        <button class="button" onclick="appendToDisplay('4')">4</button>
        <button class="button" onclick="appendToDisplay('5')">5</button>
        <button class="button" onclick="appendToDisplay('6')">6</button>
        <button class="button operator" onclick="appendToDisplay('-')">-</button>
        <button class="button" onclick="appendToDisplay('1')">1</button>
        <button class="button" onclick="appendToDisplay('2')">2</button>
        <button class="button" onclick="appendToDisplay('3')">3</button>
        <button class="button operator" onclick="appendToDisplay('*')">*</button>
        <button class="button" onclick="appendToDisplay('0')">0</button>
        <button class="button" onclick="appendToDisplay('.')">.</button>
        <button class="button operator" onclick="calculate()">=</button>
        <button class="button operator" onclick="appendToDisplay('/')">/</button>
        <button class="button" onclick="appendToDisplay('(')">(</button>
        <button class="button" onclick="appendToDisplay(')')">)</button>
        <button class="button operator" onclick="calculateSqrt()">√</button>
        <button class="button operator" onclick="calculatePower()">^</button>
        <button class="button operator" onclick="calculateSin()">sin</button>
        <button class="button operator" onclick="calculateCos()">cos</button>
        <button class="button operator" onclick="calculateTan()">tan</button>
        <button class="button operator" onclick="checkClaudia()">Claudia?</button>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').innerText += value;
        }

        function clearDisplay() {
            document.getElementById('display').innerText = '';
        }

        function calculate() {
            var expression = document.getElementById('display').innerText;
            if (expression === '1+1') {
                document.getElementById('display').innerText = 'Cláudia, namora comigo?';
            } else {
                var result = eval(expression);
                document.getElementById('display').innerText = result;
            }
        }

        function calculateSqrt() {
            var value = parseFloat(document.getElementById('display').innerText);
            var result = Math.sqrt(value);
            document.getElementById('display').innerText = result;
        }

        function calculatePower() {
            var expression = document.getElementById('display').innerText;
            var parts = expression.split('^');
            var base = parseFloat(parts[0]);
            var exponent = parseFloat(parts[1]);
            var result = Math.pow(base, exponent);
            document.getElementById('display').innerText = result;
        }

        function calculateSin() {
            var value
