<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Archmc Bloxd keyacces</title>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css" rel="stylesheet">
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #1a1a1a;
      color: white;
      text-align: center;
      position: relative;
      margin: 0;
      height: 100vh;
      overflow: hidden;
    }

    .container {
      max-width: 600px;
      margin: 0 auto;
      padding: 20px;
    }

    #logo {
      width: 100%;
      max-width: 200px;
      margin: 0 auto;
    }

    .input-section {
      margin-top: 20px;
    }

    .input-section input {
      padding: 10px;
      font-size: 16px;
      width: 100%;
      max-width: 300px;
      margin-bottom: 20px;
      border: 2px solid #f44336;
      background-color: #333;
      color: white;
    }

    .button {
      padding: 10px 20px;
      background-color: #f44336;
      color: white;
      border: none;
      font-size: 16px;
      cursor: pointer;
      margin: 10px;
      border-radius: 5px;
      transition-duration: 0.5s;
    }

    .button:hover {
      background-color: #c5362b ;
    }

    .ui-section {
      margin-top: 30px;
    }

    .ui-section .unlockable-item {
      background-color: #333;
      border: 1px solid #f44336;
      margin: 10px;
      padding: 20px;
      display: inline-block;
      width: 200px;
      color: #f44336;
      border-radius: 5px;
    }

    .credits {
      margin-top: 40px;
      font-size: 14px;
      color: #888;
    }

    #iframe-container {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: rgba(0, 0, 0, 0.8); /* Slight transparency */
      z-index: 999;
      overflow: hidden;
    }

    iframe {
      width: 100%;
      height: 100%;
      border: none;
    }

    #close-btn {
      position: absolute;
      top: 20px;
      right: 20px;
      background-color: #f44336;
      color: white;
      border: none;
      padding: 10px;
      font-size: 20px;
      cursor: pointer;
    }

    #close-btn:hover {
      background-color: #db3c30;
    }

    #signout-btn {
      position: absolute;
      bottom: 20px;
      right: 20px;
      background-color: #f44336;
      color: white;
      border: none;
      padding: 10px;
      font-size: 20px;
      cursor: pointer;
      border-radius: 5px;
      transition-duration: 0.5s;
    }

    #signout-btn:hover {
      background-color: #db3c30;
    }
  </style>
</head>
<body>

  <div class="container">
    <img id="logo" src="logo.png" alt="arch bloxd Logo">

    <div class="input-section" id="code-input-section">
      <h3>Thank You for buying the key!</h3>
      <h2>Enter the code you received</h2>
      <input type="text" id="unlock-code" placeholder="Enter Key to unlock features">
      <button class="button" onclick="submitCode()">Unlock</button>
    </div>

    <div class="ui-section" id="ui-section" style="display:none;">
      <h2>Here are the features unlocked!</h2>
      <div class="unlockable-item">50% Off Everything</div>
      <div class="unlockable-item">T-Pack</div>
      <div class="unlockable-item">Feature 3</div>
      <div class="unlockable-item">Feature 4</div>
    </div>

    <div class="button-section" style="display: none;" id="button-section">
      <button class="button" onclick="openBloxd()">Play Server</button>
      <button class="button" onclick="goToMainSite()">Go to Main Site</button>
    </div>

    <div class="credits">
      <p>Made with ❤️ by  Archmc Bloxd Team  and  Produx.</p>
    </div>
  </div>

  <button id="signout-btn" onclick="signOut()"><i class="fas fa-sign-out-alt"></i> Sign out</button>

  <div id="iframe-container">
    <iframe id="bloxd-iframe" src="https://bloxd.io/?lobby=archmc_server&g=worlds" title="Bloxd.io"></iframe>
    <button id="close-btn" onclick="closeIframe()">Close</button>
  </div>

  <script>
    const unlockCode = "81b4*^n2n2Ejnf8284";
    const storedCode = localStorage.getItem('unlockCode');

    if (storedCode === unlockCode) {
      document.getElementById('code-input-section').style.display = 'none';
      document.getElementById('ui-section').style.display = 'block';
      document.getElementById('button-section').style.display = 'block';
    }

    function submitCode() {
      const inputCode = document.getElementById('unlock-code').value;

      if (inputCode === unlockCode) {
        localStorage.setItem('unlockCode', inputCode);
        document.getElementById('code-input-section').style.display = 'none';
        document.getElementById('ui-section').style.display = 'block';
        document.getElementById('button-section').style.display = 'block';
      } else {
        alert("Invalid code. Please try again.");
      }
    }

    function openBloxd() {
      document.getElementById('iframe-container').style.display = 'block';
    }

    function closeIframe() {
      document.getElementById('iframe-container').style.display = 'none';
    }

    function goToMainSite() {
      window.location.href = "https://your-main-site.com";
    }

    function signOut() {
      localStorage.removeItem('unlockCode');
      document.getElementById('code-input-section').style.display = 'block';
      document.getElementById('ui-section').style.display = 'none';
      document.getElementById('button-section').style.display = 'none';
      document.getElementById('unlock-code').value = '';  // Clear input field
    }
  </script>
</body>
</html>
