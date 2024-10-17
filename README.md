<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cart Quantity</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        #container {
            text-align: center;
        }
        button {
            margin: 5px;
            padding: 5px 10px;
        }
    </style>
</head>
<body>
    <div id="container">
        <h2>Cart Quantity</h2>
        <p>Quantity: <span id="quantity">0</span></p>
        <button onclick="addToCart(1)">Add to Cart</button>
        <button onclick="addToCart(2)">+2</button>
        <button onclick="addToCart(3)">+3</button>
        <button onclick="resetCart()">Reset</button>
    </div>

    <script>
        let quantity = 0;
        const quantityElement = document.getElementById('quantity');

        function updateDisplay() {
            quantityElement.textContent = quantity;
        }

        function addToCart(amount) {
            quantity += amount;
            updateDisplay();
        }

        function resetCart() {
            quantity = 0;
            updateDisplay();
        }
    </script>
</body>
</html>
