<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>OmniStay — Hotel booking in one place</title>
  <meta name="description" content="OmniStay helps people book hotels easily without creating an account. Pay, verify with your billing number, and check in smoothly." />
  <style>
    :root{
      /* Brand palette (blue + gold) */
      --bg: #0B1220;
      --card: #0F1A2F;
      --muted: #AAB4C5;
      --text: #EAF0FF;
      --line: rgba(255,255,255,.10);

      --brand1: #2F7BFF; /* primary blue */
      --brand2: #2AD2C9; /* teal accent */
      --gold: #F4C04E;   /* warm gold */
      --shadow: 0 20px 70px rgba(0,0,0,.45);
      --radius: 18px;
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
      background:
        radial-gradient(900px 500px at 10% 10%, rgba(47,123,255,.25), transparent 60%),
        radial-gradient(800px 500px at 90% 20%, rgba(42,210,201,.18), transparent 55%),
        radial-gradient(900px 650px at 60% 90%, rgba(244,192,78,.12), transparent 55%),
        var(--bg);
      color: var(--text);
      line-height:1.5;
    }

    a{color:inherit; text-decoration:none}
    .container{max-width:1100px; margin:0 auto; padding:28px 18px 70px}

    /* Top nav */
    .nav{
      display:flex; align-items:center; justify-content:space-between;
      padding:14px 0;
    }
    .brand{
      display:flex; align-items:center; gap:12px;
      font-weight:700; letter-spacing:.2px;
    }
    .brand img{
      width:38px; height:38px; border-radius:12px;
      background: rgba(255,255,255,.06);
      border: 1px solid var(--line);
      padding:6px;
    }
    .brand .name{font-size:16px}
    .brand .tag{display:block; font-size:12px; color:var(--muted); font-weight:500}

    .navlinks{display:flex; gap:18px; align-items:center; color:var(--muted); font-weight:600; font-size:14px}
    .navlinks a:hover{color:var(--text)}

    .btn{
      display:inline-flex; align-items:center; justify-content:center; gap:10px;
      padding:12px 16px;
      border-radius:999px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.06);
      color: var(--text);
      font-weight:700;
      cursor:pointer;
      transition: transform .12s ease, background .12s ease, border-color .12s ease;
      white-space:nowrap;
    }
    .btn:hover{transform: translateY(-1px); background: rgba(255,255,255,.09)}
    .btn.primary{
      border: none;
      background: linear-gradient(135deg, var(--brand1), var(--brand2));
      box-shadow: 0 12px 35px rgba(47,123,255,.22);
    }
    .btn.primary:hover{filter: brightness(1.03)}
    .btn.gold{
      border: 1px solid rgba(244,192,78,.35);
      background: rgba(244,192,78,.12);
    }

    /* Hero */
    .hero{
      margin-top:24px;
      display:grid;
      grid-template-columns: 1.15fr .85fr;
      gap:22px;
      align-items:stretch;
    }
    @media (max-width: 920px){
      .hero{grid-template-columns:1fr; }
      .navlinks{display:none;}
    }

    .heroCard{
      border: 1px solid var(--line);
      background: linear-gradient(180deg, rgba(255,255,255,.07), rgba(255,255,255,.03));
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding:28px;
      overflow:hidden;
      position:relative;
    }
    .kicker{
      display:inline-flex; align-items:center; gap:10px;
      color: var(--muted);
      font-weight:800;
      font-size:12px;
      letter-spacing:.14em;
      text-transform:uppercase;
    }
    .dot{
      width:8px;height:8px;border-radius:99px;
      background: var(--gold);
      box-shadow: 0 0 0 5px rgba(244,192,78,.18);
    }
    h1{
      margin:14px 0 10px;
      font-size:44px;
      line-height:1.05;
      letter-spacing:-.02em;
    }
    @media (max-width: 520px){
      h1{font-size:36px;}
    }
    .sub{
      color: var(--muted);
      font-size:16px;
      max-width: 58ch;
      margin:0 0 18px;
    }
    .ctaRow{display:flex; gap:12px; flex-wrap:wrap; margin-top:18px}

    .heroMini{
      border: 1px solid var(--line);
      background: rgba(15,26,47,.65);
      border-radius: var(--radius);
      padding:20px;
      box-shadow: var(--shadow);
      position:relative;
      overflow:hidden;
    }
    .miniTitle{font-weight:800; margin:0 0 8px; font-size:16px}
    .miniText{margin:0; color: var(--muted); font-size:14px}
    .miniBox{
      margin-top:16px;
      border-radius: 14px;
      border: 1px dashed rgba(255,255,255,.16);
      background: rgba(255,255,255,.04);
      padding:14px;
      color: var(--muted);
      font-size:13px;
    }
    .miniBox code{
      color: #DDE7FF;
      font-weight:800;
      background: rgba(47,123,255,.10);
      padding:2px 8px;
      border-radius: 999px;
      border:1px solid rgba(47,123,255,.18);
    }

    /* Sections */
    .section{margin-top:26px}
    .grid3{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:14px;
    }
    @media (max-width: 920px){
      .grid3{grid-template-columns:1fr;}
    }
    .card{
      border:1px solid var(--line);
      background: rgba(255,255,255,.04);
      border-radius: 16px;
      padding:18px;
    }
    .card h3{margin:0 0 8px; font-size:16px}
    .card p{margin:0; color:var(--muted); font-size:14px}
    .icon{
      width:38px;height:38px;border-radius:14px;
      display:flex;align-items:center;justify-content:center;
      border:1px solid var(--line);
      background: rgba(255,255,255,.05);
      margin-bottom:10px;
      font-weight:900;
    }

    .how{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:14px;
    }
    @media (max-width: 920px){ .how{grid-template-columns:1fr;} }
    .step{
      display:flex; gap:12px; align-items:flex-start;
      padding:16px;
      border:1px solid var(--line);
      border-radius: 16px;
      background: rgba(255,255,255,.03);
    }
    .num{
      width:34px;height:34px;border-radius:12px;
      display:flex;align-items:center;justify-content:center;
      font-weight:900;
      background: rgba(47,123,255,.12);
      border:1px solid rgba(47,123,255,.22);
      color: #DDE7FF;
      flex:0 0 auto;
    }
    .step h4{margin:0 0 4px; font-size:15px}
    .step p{margin:0; color:var(--muted); font-size:14px}

    /* Footer */
    footer{
      margin-top:32px;
      border-top: 1px solid var(--line);
      padding-top:18px;
      color: var(--muted);
      display:flex;
      justify-content:space-between;
      gap:12px;
      flex-wrap:wrap;
      font-size:13px;
    }
    footer a{color: var(--muted); text-decoration:underline; text-underline-offset: 3px}
    footer a:hover{color: var(--text)}
  </style>
</head>

<body>
  <div class="container">
    <div class="nav">
      <div class="brand">
        <!-- Put your logo file in the repo as: assets/omnistay-logo.png -->
        <img src="assets/omnistay-logo.png" alt="OmniStay logo" />
        <div>
          <div class="name">OmniStay</div>
          <span class="tag">Hotel booking in one place</span>
        </div>
      </div>

      <div class="navlinks">
        <a href="#features">Features</a>
        <a href="#how">How it works</a>
        <a href="#trust">Trust</a>
      </div>

      <a class="btn primary" href="#how">Get started</a>
    </div>

    <div class="hero">
      <div class="heroCard">
        <div class="kicker"><span class="dot"></span> SIMPLE • SECURE • FAST</div>
        <h1>Book hotels without creating an account.</h1>
        <p class="sub">
          OmniStay lets guests search hotels, pay, and access booking details using a billing phone number with secure verification.
          Hotels can confirm bookings via billing number or QR for smoother check-in.
        </p>

        <div class="ctaRow">
          <a class="btn primary" href="#how">How OmniStay works</a>
          <a class="btn gold" href="#features">View features</a>
        </div>
      </div>

      <div class="heroMini">
        <p class="miniTitle">Guest access (no sign-up)</p>
        <p class="miniText">After payment, guests verify using their billing phone number and receive access to booking and services.</p>

        <div class="miniBox">
          Example verification method:
          <div style="margin-top:10px; display:flex; gap:8px; flex-wrap:wrap;">
            <code>Billing Phone</code>
            <code>OTP</code>
            <code>QR Check-in</code>
          </div>
          <div style="margin-top:12px;">
            Tip: keep check-in fast while protecting bookings from unauthorized access.
          </div>
        </div>
      </div>
    </div>

    <div id="features" class="section">
      <div class="grid3">
        <div class="card">
          <div class="icon">🔎</div>
          <h3>Search & compare hotels</h3>
          <p>Browse available rooms, dates, pricing, and amenities in a clear and simple flow.</p>
        </div>
        <div class="card">
          <div class="icon">✅</div>
          <h3>Pay once, access instantly</h3>
          <p>After payment, guests access booking details using billing phone verification—no password needed.</p>
        </div>
        <div class="card">
          <div class="icon">🏨</div>
          <h3>Fast hotel verification</h3>
          <p>Hotels verify guests by billing number or QR code to reduce front-desk time and errors.</p>
        </div>
      </div>
    </div>

    <div id="how" class="section">
      <h2 style="margin:0 0 12px; font-size:20px;">How it works</h2>
      <div class="how">
        <div class="step">
          <div class="num">1</div>
          <div>
            <h4>Choose your stay</h4>
            <p>Select hotel, dates, and room type that fits your trip.</p>
          </div>
        </div>
        <div class="step">
          <div class="num">2</div>
          <div>
            <h4>Complete payment</h4>
            <p>Pay through the payment provider. Your booking is confirmed after successful payment.</p>
          </div>
        </div>
        <div class="step">
          <div class="num">3</div>
          <div>
            <h4>Verify with billing phone</h4>
            <p>Enter your billing phone number and verify via OTP to view booking details.</p>
          </div>
        </div>
        <div class="step">
          <div class="num">4</div>
          <div>
            <h4>Check in smoothly</h4>
            <p>Show booking and QR at the hotel for quick verification and key handover.</p>
          </div>
        </div>
      </div>
    </div>

    <div id="trust" class="section">
      <div class="grid3">
        <div class="card">
          <div class="icon">🔐</div>
          <h3>Secure verification</h3>
          <p>OTP and short-lived QR tokens help protect bookings from unauthorized access.</p>
        </div>
        <div class="card">
          <div class="icon">📄</div>
          <h3>Clear policies</h3>
          <p>Simple privacy and terms pages so users know what data is used and why.</p>
        </div>
        <div class="card">
          <div class="icon">🤝</div>
          <h3>Hotel-first workflow</h3>
          <p>Designed to make front-desk verification and service requests easy for staff.</p>
        </div>
      </div>
    </div>

    <footer>
      <div>© <span id="y"></span> OmniStay. All rights reserved.</div>
      <div style="display:flex; gap:12px; flex-wrap:wrap;">
        <a href="privacy.html">Privacy Policy</a>
        <a href="terms.html">Terms of Service</a>
        <a href="support.html">Support</a>
      </div>
    </footer>
  </div>

  <script>
    document.getElementById("y").textContent = new Date().getFullYear();
  </script>
</body>
</html>


<!--
**omnistay/omnistay** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
