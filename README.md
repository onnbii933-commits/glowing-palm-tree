
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Bitter Rivals | Iran & Saudi Arabia</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="Bitter Rivals explores the sectarian and geopolitical struggle between Iran and Saudi Arabia." />
  <script src="https://www.paypal.com/sdk/js?client-id=YOUR_PAYPAL_CLIENT_ID&currency=USD"></script>
  <style>
    body { font-family: Arial, sans-serif; background:#0f172a; color:#fff; margin:0 }
    .container { max-width:900px; margin:auto; padding:40px }
    h1 { font-size:42px }
    button { background:#22c55e; border:none; padding:14px 24px; font-size:18px; cursor:pointer }
  </style>
</head>
<body>
  <div class="container">
    <h1>BITTER RIVALS</h1>
    <p><strong>Iran & Saudi Arabia – The Sectarian Struggle for the Middle East</strong></p>
    <p>A deep geopolitical analysis covering revolutions, proxy wars, ideology, oil, and global power shifts.</p>
    <h2>Price: $9.99</h2>

    <div id="paypal-button-container"></div>
  </div>

  <script>
    paypal.Buttons({
      createOrder: () =>
        fetch('/api/create-order', { method: 'POST' })
          .then(res => res.json())
          .then(data => data.id),

      onApprove: (data) =>
        fetch('/api/capture-order', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ orderID: data.orderID })
        })
        .then(res => res.json())
        .then(() => window.location.href = '/success.html')
    }).render('#paypal-button-container');
  </script>
</body>
</html>
