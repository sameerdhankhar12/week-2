<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Tax Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        h1 {
            color: #333;
        }
        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Simple Tax Calculator</h1>
    <p>Please enter your annual income in the box below and click "Calculate" to see your estimated tax.</p>
    <input type="number" id="income" placeholder="Enter your salary">
    <button onclick="calculateTax()">Calculate</button>
    <div id="result"></div>

    <script>
        function calculateTax() {
            const income = parseFloat(document.getElementById('income').value);
            let tax = 0;

            if (income <= 15600) {
                tax = income * 0.105;
            } else if (income <= 53500) {
                tax = 15600 * 0.105 + (income - 15600) * 0.175;
            } else if (income <= 78100) {
                tax = 15600 * 0.105 + 37900 * 0.175 + (income - 53500) * 0.30;
            } else if (income <= 180000) {
                tax = 15600 * 0.105 + 37900 * 0.175 + 24600 * 0.30 + (income - 78100) * 0.33;
            } else {
                tax = 15600 * 0.105 + 37900 * 0.175 + 24600 * 0.30 + 101900 * 0.33 + (income - 180000) * 0.39;
            }

            document.getElementById('result').innerHTML = `Estimated tax: $${tax.toFixed(2)}`;
        }
    </script>
</body>
</html>
