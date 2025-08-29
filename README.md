<!--
  Amazon-Clone
  Single-file front-end clone (HTML + CSS + small JS) — responsive navbar, product grid, footer.
  Usage: save this file as `index.html` and open in browser.
  Replace images with real assets in the /assets folder or remote URLs.
-->

<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Amazon Clone — Frontend</title>
  <meta name="description" content="Responsive Amazon homepage clone — HTML5 & CSS3" />

  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --primary: #131921; /* amazon dark */
      --accent: #ff9900; /* amazon orange */
      --muted: #f3f3f3;
      --card: #ffffff;
      --max-w: 1200px;
      --radius: 8px;
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }

    *{box-sizing:border-box}
    body{margin:0;background:linear-gradient(180deg,#fafafa 0%, #fff 100%);color:#111}
    a{color:inherit;text-decoration:none}

    /* Container */
    .container{max-width:var(--max-w);margin:0 auto;padding:0 16px}

    /* Header */
    header{background:var(--primary);color:#fff;position:sticky;top:0;z-index:60;box-shadow:0 2px 6px rgba(0,0,0,0.08)}
    .topbar{display:flex;align-items:center;gap:20px;padding:10px 0}
    .logo{display:flex;align-items:center;gap:12px}
    .logo img{height:34px}
    .logo strong{font-weight:700;color:var(--accent);font-size:20px}

    /* Search */
    .search{flex:1;display:flex;align-items:center}
    .search input{flex:1;padding:10px 12px;border-radius:6px 0 0 6px;border:none;outline:none}
    .search button{background:var(--accent);border:none;padding:10px 16px;border-radius:0 6px 6px 0;cursor:pointer}

    /* Right actions */
    .actions{display:flex;align-items:center;gap:14px}
    .action{display:flex;flex-direction:column;font-size:12px;color:#eee}
    .cart{display:flex;align-items:center;gap:8px}

    /* Nav */
    .nav{background:#232f3e;color:#fff;padding:8px 0;font-size:14px}
    .nav ul{display:flex;gap:18px;list-style:none;margin:0;padding:0;align-items:center}
    .nav a{color:#fff;opacity:0.95}

    /* Hero */
    .hero{display:grid;grid-template-columns:1fr 320px;gap:20px;align-items:center;padding:30px 0}
    .hero .card{background:linear-gradient(180deg,#fff,#fff);padding:24px;border-radius:10px;box-shadow:0 4px 12px rgba(17,24,39,0.06)}
    .hero h1{margin:0 0 8px 0;font-size:28px}
    .hero p{margin:0;color:#444}
    .promo{height:180px;border-radius:8px;background-image:linear-gradient(90deg,#e6f0ff,#f7fbff);display:flex;align-items:center;justify-content:center}

    /* Product grid */
    .section{padding:28px 0}
    .grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
    .card-product{background:var(--card);padding:14px;border-radius:10px;box-shadow:0 2px 8px rgba(0,0,0,0.05);display:flex;flex-direction:column}
    .card-product img{width:100%;height:180px;object-fit:contain;background:var(--muted);border-radius:6px}
    .title{font-weight:600;margin:12px 0 6px 0;font-size:14px}
    .price{color:var(--primary);font-weight:700}
    .btn{margin-top:auto;padding:10px;border-radius:6px;border:none;background:var(--accent);color:#111;font-weight:600;cursor:pointer}

    /* Footer */
    footer{background:#0f1720;color:#fff;padding:30px 0;margin-top:30px}
    .footer-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
    .footer-grid h4{margin-top:0}

    /* Utilities */
    .small{font-size:13px;color:#6b7280}

    /* Responsive */
    @media (max-width:1024px){
      .grid{grid-template-columns:repeat(3,1fr)}
      .hero{grid-template-columns:1fr 260px}
    }
    @media (max-width:768px){
      .topbar{padding:12px 0}
      .search{display:none}
      .nav ul{flex-wrap:wrap;gap:12px}
      .hero{grid-template-columns:1fr}
      .grid{grid-template-columns:repeat(2,1fr)}
      .hero .card{padding:16px}
      .footer-grid{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width:480px){
      .grid{grid-template-columns:1fr}
      .logo img{height:26px}
      .logo strong{font-size:18px}
      .nav{font-size:13px}
    }

  </style>
</head>
<body>

  <header>
    <div class="container topbar">
      <div class="logo">
        <img src="https://raw.githubusercontent.com/hadiaimran1090/assets/main/amazon-logo-placeholder.png" alt="logo"/>
        <strong>Automedix</strong>
      </div>

      <div class="search">
        <input type="search" placeholder="Search products, brands and more..." aria-label="Search" />
        <button aria-label="Search">Search</button>
      </div>

      <div class="actions">
        <div class="action">
          <span style="font-size:12px;opacity:0.9">Deliver to</span>
          <strong>Pakistan</strong>
        </div>
        <div class="action" style="text-align:right">
          <span style="font-size:12px;opacity:0.9">Hello, Sign in</span>
          <strong>Account & Lists</strong>
        </div>
        <div class="cart">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" aria-hidden>
            <path d="M7 4h-2l-1 2v1h1l3 9h8l3-9h1v-1l-1-2h-11z" fill="#fff" opacity="0.9"/>
          </svg>
          <div style="text-align:left">
            <span style="font-size:12px;opacity:0.9">Cart</span>
            <strong>0</strong>
          </div>
        </div>
      </div>
    </div>

    <nav class="nav">
      <div class="container">
        <ul>
          <li><a href="#">All</a></li>
          <li><a href="#">Best Sellers</a></li>
          <li><a href="#">Electronics</a></li>
          <li><a href="#">Today's Deals</a></li>
          <li><a href="#">Customer Service</a></li>
          <li><a href="#">Gift Cards</a></li>
          <li><a href="#">Registry</a></li>
        </ul>
      </div>
    </nav>
  </header>

  <main class="container">

    <section class="hero">
      <div class="card">
        <h1>Welcome to the Amazon Clone</h1>
        <p class="small">A responsive front-end replica focused on layout, accessibility, and clean semantic HTML & CSS.</p>

        <div style="display:flex;gap:10px;margin-top:18px">
          <button class="btn" style="background:var(--primary);color:#fff">Shop Now</button>
          <button class="btn" style="background:transparent;border:1px solid #e5e7eb;color:var(--primary)">Explore</button>
        </div>

        <div style="margin-top:18px;display:flex;gap:10px;flex-wrap:wrap">
          <div style="padding:8px 12px;background:#f3f4f6;border-radius:6px">Free Delivery</div>
          <div style="padding:8px 12px;background:#f3f4f6;border-radius:6px">Secure Payments</div>
          <div style="padding:8px 12px;background:#f3f4f6;border-radius:6px">24/7 Support</div>
        </div>
      </div>

      <aside class="promo card" aria-hidden>
        <div>
          <h3 style="margin:0 0 8px 0">Deal of the Day</h3>
          <p style="margin:0">Top picks at amazing prices</p>
        </div>
      </aside>
    </section>

    <section class="section">
      <h2 style="margin:0 0 12px 0">Featured Products</h2>
      <div class="grid" aria-live="polite">

        <!-- Example product card (repeatable) -->
        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+1" alt="Product 1"/>
          <div class="title">Wireless Headphones — Over Ear</div>
          <div class="small">Brand — StudioSound</div>
          <div style="margin-top:8px" class="price">$59.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+2" alt="Product 2"/>
          <div class="title">Smart Watch Series 5</div>
          <div class="small">Brand — TimeTech</div>
          <div style="margin-top:8px" class="price">$129.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+3" alt="Product 3"/>
          <div class="title">Portable Speaker</div>
          <div class="small">Brand — BeatBox</div>
          <div style="margin-top:8px" class="price">$39.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+4" alt="Product 4"/>
          <div class="title">Noise Cancelling Earbuds</div>
          <div class="small">Brand — QuietEar</div>
          <div style="margin-top:8px" class="price">$49.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+5" alt="Product 5"/>
          <div class="title">HD Webcam</div>
          <div class="small">Brand — ClearCam</div>
          <div style="margin-top:8px" class="price">$29.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+6" alt="Product 6"/>
          <div class="title">Mechanical Keyboard</div>
          <div class="small">Brand — KeyPro</div>
          <div style="margin-top:8px" class="price">$89.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+7" alt="Product 7"/>
          <div class="title">USB-C Hub</div>
          <div class="small">Brand — ConnectX</div>
          <div style="margin-top:8px" class="price">$24.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

        <article class="card-product" tabindex="0">
          <img src="https://via.placeholder.com/320x200?text=Product+8" alt="Product 8"/>
          <div class="title">Fitness Band</div>
          <div class="small">Brand — FitLine</div>
          <div style="margin-top:8px" class="price">$19.99</div>
          <button class="btn" aria-label="Add to cart">Add to Cart</button>
        </article>

      </div>
    </section>

  </main>

  <footer>
    <div class="container">
      <div class="footer-grid">
        <div>
          <h4>Get to Know Us</h4>
          <p class="small">About • Careers • Press</p>
        </div>
        <div>
          <h4>Make Money with Us</h4>
          <p class="small">Sell on Amazon • Affiliate Program</p>
        </div>
        <div>
          <h4>Let Us Help You</h4>
          <p class="small">Your Account • Returns • Help</p>
        </div>
        <div>
          <h4>Contact</h4>
          <p class="small">email@example.com</p>
        </div>
      </div>

      <div style="margin-top:18px;text-align:center;color:#94a3b8;font-size:13px">© 2025 — Frontend Clone by You</div>
    </div>
  </footer>

  <script>
    // Small enhancement: keyboard focus styles for accessibility
    (function(){
      const body = document.body;
      function handleFirstTab(e){
        if(e.key === 'Tab'){
