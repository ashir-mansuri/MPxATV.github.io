<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Info with QR Code</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        .container {
            width: 400px;
            border: 1px solid #ccc;
            border-radius: 10px;
            background-color: #fff;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .logo, .product-image, .barcode {
            margin: 10px auto;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            width: 100%;
            background-color: #ccc;
            border-radius: 10px;
            color: #fff;
        }

        .details {
            margin: 20px 0;
            text-align: left;
        }

        .details h2, .details p {
            margin: 5px 0;
        }

        .details h2 {
            font-size: 18px;
        }

        .qr-code {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Company Logo Section -->
        <div class="logo">Company Logo</div>

        <!-- Product Image Section -->
        <div class="product-image">Product Image</div>

        <!-- Product Details Section -->
        <div class="details">
            <h2>Atelier Vierkant</h2>
            <p><strong>Product Name:</strong> Sample Product</p>
            <p><strong>Article Number:</strong> 12345</p>
            <p><strong>Dimensions:</strong> 50cm x 50cm x 100cm</p>
            <p><strong>Selling Price:</strong> $999.99</p>
        </div>

        <!-- Barcode Section -->
        <div class="barcode">Product Barcode</div>

        <!-- QR Code -->
        <div class="qr-code">
            <canvas id="qrcode"></canvas>
        </div>
    </div>


    <script>
        const qrData = `
        Atelier Vierkant
        Product Name: Sample Product
        Article Number: 12345
        Dimensions: 50cm x 50cm x 100cm
        Selling Price: $999.99
        `;
        QRCode.toCanvas(document.getElementById('qrcode'), qrData, function (error) {
            if (error) console.error(error);
            console.log('QR Code generated!');
        });
    </script>
</body>
</html>
