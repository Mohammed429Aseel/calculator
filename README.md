
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sample Form</title>
    <link rel="stylesheet" href="styles.css">
    <script src="script.js" defer></script>
</head>
<body>
    <form id="Calculator">
       <label for="number1">Number 1:</label>
       <input type="number" id="number1" name="number1" required>
         <label for="number2">Number 2:</label> 
         <input type="number" id="number2" name="number2" required>
         <label for ="operation">Operation:</label>
         <select id="operation" name="operation">
            <option value="+">Add</option>
            <option value="-">Subtract</option>
            <option value="*">Multiply</option> 
            <option value="/">Divide</option>
         </select>
            <button type="button" id="calculateButton">Calculate</button>
            <button type="button" id="clearButton">Clear</button>
            <div id="result"></div>
            <script>
                const calculateButton = document.getElementById('calculateButton');
                const clearButton = document.getElementById('clearButton');
                const resultDiv = document.getElementById('result');
                calculateButton.addEventListener('click', function() {
                    const number1 = parseFloat(document.getElementById('number1').value);
                    const number2 = parseFloat(document.getElementById('number2').value);
                    const operation = document.getElementById('operation').value;
                    let result;
                    switch(operation) {
                        case '+':
                            result = number1 + number2;
                            break;
                        case '-':
                            result = number1 - number2;
                            break;
                        case '*':
                            result = number1 * number2;
                            break;
                        case '/':
                            result = number1 / number2;
                            break;
                        default:
                            result = 'Invalid operation';
                    }
                    resultDiv.textContent = 'Result: ' + result;
                });

                clearButton.addEventListener('click', function() {
                    document.getElementById('number1').value = '';
                    document.getElementById('number2').value = '';
                    resultDiv.textContent = '';
                });
                
            </script>
    </form>
</body>
</html>

