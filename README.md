Here's a simple calculator program created using HTML, CSS, and JavaScript:

Calculator Program
*HTML Code*
```
<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        #calculator {
            width: 300px;
            margin: 50px auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        #display {
            width: 100%;
            height: 40px;
            margin-bottom: 20px;
            padding: 10px;
            border: none;
            border-radius: 10px;
            font-size: 24px;
            text-align: right;
        }
        .button {
            width: 60px;
            height: 40px;
            margin: 5px;
            padding: 10px;
            border: none;
            border-radius: 10px;
            background-color: #f0f0f0;
            cursor: pointer;
        }
        .button:hover {
            background-color: #e0e0e0;
        }
    </style>
</head>
<body>
    <div id="calculator">
        <input type="text" id="display" disabled>
        <div>
            <button class="button" onclick="clearDisplay()">C</button>
            <button class="button" onclick="backspace()">DEL</button>
        </div>
        <div>
            <button class="button" onclick="appendNumber(7)">7</button>
            <button class="button" onclick="appendNumber(8)">8</button>
            <button class="button" onclick="appendNumber(9)">9</button>
            <button class="button" onclick="appendOperator('/')">/</button>
        </div>
        <div>
            <button class="button" onclick="appendNumber(4)">4</button>
            <button class="button" onclick="appendNumber(5)">5</button>
            <button class="button" onclick="appendNumber(6)">6</button>
            <button class="button" onclick="appendOperator('*')">*</button>
        </div>
        <div>
            <button class="button" onclick="appendNumber(1)">1</button>
            <button class="button" onclick="appendNumber(2)">2</button>
            <button class="button" onclick="appendNumber(3)">3</button>
            <button class="button" onclick="appendOperator('-')">-</button>
        </div>
        <div>
            <button class="button" onclick="appendNumber(0)">0</button>
            <button class="button" onclick="appendDecimal()">.</button>
            <button class="button" onclick="calculate()">=</button>
            <button class="button" onclick="appendOperator('+')">+</button>
        </div>
    </div>

    <script>
        let display = document.getElementById('display');
        let currentNumber = '';
        let previousNumber = '';
        let operator = '';

        function clearDisplay() {
            display.value = '';
            currentNumber = '';
            previousNumber = '';
            operator = '';
        }

        function backspace() {
            display.value = display.value.slice(0, -1);
            currentNumber = currentNumber.slice(0, -1);
        }

        function appendNumber(number) {
            currentNumber += number.toString();
            display.value += number.toString();
        }

        function appendDecimal() {
            if (!currentNumber.includes('.')) {
                currentNumber += '.';
                display.value += '.';
            }
        }

        function appendOperator(op) {
            if (currentNumber !== '') {
                previousNumber = currentNumber;
                currentNumber = '';
                operator = op;
                display.value += op;
            }
        }

        function calculate() {
            if (currentNumber !== '' && previousNumber !== '') {
                let result;
                switch (operator) {
                    case '+':
                        result = parseFloat(previousNumber) + parseFloat(currentNumber);
                        break;
                    case '-':
                        result = parseFloat(previousNumber) - parseFloat(currentNumber);
                        break;
                    case '*':
                        result = parseFloat(previousNumber) * parseFloat(currentNumber);
                        break;
                    case '/':
                        result = parseFloat(previousNumber) / parseFloat(currentNumber);
                        break;
                    default:
                        result = 0;
                }
                display.value = result.toString();
                currentNumber = result.toString();
                previousNumber = '';
                operator = '';
            }
        }
    </script>
</body>
</html>
```

*Example Usage*
1. Open the HTML file in a web browser
