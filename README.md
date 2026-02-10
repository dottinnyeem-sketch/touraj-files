<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Touraj Files 👁️</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: black;
      color: red;
      font-family: monospace;
      flex-direction: column;
    }

    h1 {
      font-size: 3rem;
      text-shadow: 0 0 15px red;
    }

    #countdown {
      font-size: 4rem;
      margin-top: 20px;
      text-shadow: 0 0 20px red;
    }
  </style>
</head>

<body>
  <h1>THE TOURAJ FILES 👁️</h1>
  <div id="countdown">24:00:00</div>

  <script>
    const endTime = new Date().getTime() + 24 * 60 * 60 * 1000;
    const el = document.getElementById("countdown");

    function update() {
      const now = new Date().getTime();
      const diff = endTime - now;

      if (diff <= 0) {
        el.textContent = "FILES OPENED 👁️";
        return;
      }

      const h = Math.floor(diff / (1000 * 60 * 60));
      const m = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      const s = Math.floor((diff % (1000 * 60)) / 1000);

      el.textContent =
        String(h).padStart(2, "0") + ":" +
        String(m).padStart(2, "0") + ":" +
        String(s).padStart(2, "0");
    }

    update();
    setInterval(update, 1000);
  </script>
</body>
</html>
