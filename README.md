<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Essy Haven — Elevate Your Everyday Style</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --white: #fafaf8;
    --beige: #f0ebe3;
    --beige-dark: #e0d8cc;
    --gold: #c9a96e;
    --gold-light: #e8d5a3;
    --gold-dark: #9a7a47;
    --text-muted: #8a8478;
    --serif: 'Cormorant Garamond', serif;
    --sans: 'DM Sans', sans-serif;
  }
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { font-family: var(--sans); background: var(--white); color: var(--black); overflow-x: hidden; }

  nav { position: fixed; top:0; left:0; right:0; z-index:100; display:flex; justify-content:space-between; align-items:center; padding:1.4rem 5%; background: rgba(10,10,10,0.55); backdrop-filter: blur(16px); border-bottom:1px solid rgba(201,169,110,0.15); }
  .nav-logo { font-family: var(--serif); font-size: 1.7rem; font-weight:500; color:var(--gold); text-decoration:none; letter-spacing:0.08em; }
  .nav-links { display:flex; gap:2.4rem; list-style:none; }
  .nav-links a { font-size:0.78rem; letter-spacing:0.12em; text-transform:uppercase; color: rgba(250,250,248,0.75); text-decoration:none; transition: color 0.3s; }
  .nav-links a:hover { color: var(--gold); }
  .nav-actions { display:flex; gap:1.2rem; align-items:center; }
  .nav-actions a { color: rgba(250,250,248,0.75); text-decoration:none; font-size:0.78rem; letter-spacing:0.1em; text-transform:uppercase; transition: color 0.3s; }
  .nav-actions a:hover { color: var(--gold); }

  .hero { position: relative; height:100vh; min-height:600px; display:flex; align-items:center; justify-content:center; text-align:center; overflow:hidden; }
  .hero-bg { position:absolute; inset:0; background: linear-gradient(to bottom, rgba(10,10,10,0.55) 0%, rgba(10,10,10,0.3) 50%, rgba(10,10,10,0.7) 100%), url('https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1800&q=80') center/cover no-repeat; transform: scale(1.05); transition: transform 8s ease; }
  .hero:hover .hero-bg { transform: scale(1); }
  .hero-content { position: relative; z-index:2; max-width:800px; padding:0 2rem; }
  .hero-eyebrow { font-size:0.72rem; letter-spacing:0.25em; text-transform:uppercase; color:var(--gold); margin-bottom:1.4rem; }
  .hero h1 { font-family:var(--serif); font-size:clamp(3rem,8vw,6.5rem); font-weight:300; line-height:1.05; color:var(--white); margin-bottom:1.4rem; }
  .hero h1 em { font-style:italic; color:var(--gold-light); }
  .hero p { font-size:1.05rem; line-height:1.7; color:rgba(250,250,248,0.7); max-width:500px; margin:0 auto 2.8rem; }
  .hero-btns { display:flex; gap:1.2rem; justify-content:center; flex-wrap:wrap; }
  .btn-primary { padding:1rem 2.4rem; background:var(--gold); color:var(--black); font-size:0.78rem; letter-spacing:0.15em; text-transform:uppercase; text-decoration:none; font-weight:500; transition: background 0.3s, transform 0.3s; }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }
  .btn-outline { padding:1rem 2.4rem; border:1px solid rgba(250,250,248,0.5); color:var(--white); font-size:0.78rem; letter-spacing:0.15em; text-transform:uppercase; text-decoration:none; transition: border-color 0.3s, color 0.3s, transform 0.3s; }
  .btn-outline:hover { border-color:var(--gold); color:var(--gold); transform: translateY(-2px); }

  .marquee-strip { background: var(--black); color: var(--gold); padding:1rem 0; overflow:hidden; white-space:nowrap; }
  .marquee-inner { display:inline-block; animation: marquee 22s linear infinite; font-family: var(--serif); font-size:1.1rem; font-style:italic; letter-spacing:0.05em; }
  .marquee-inner span { margin:0 2.5rem; }
  .marquee-inner .sep { color: rgba(201,169,110,0.4); }
  @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }

  section { padding:7rem 5%; }
  .section-label { font-size:0.68rem; letter-spacing:0.3em; text-transform:uppercase; color:var(--gold); margin-bottom:0.8rem; }
  .section-title { font-family:var(--serif); font-size:clamp(2rem,4vw,3.4rem); font-weight:300; line-height:1.15; color:var(--black); margin-bottom:1rem; }

  .categories-grid { display:grid; grid-template-columns: repeat(auto-fill,minmax(200px,1fr)); gap:1.5rem; }
  .cat-card { position:relative; overflow:hidden; cursor:pointer; aspect-ratio:3/4; background:var(--black); }
  .cat-card img { width:100%; height:100%; object-fit:cover; transition: transform 0.6s, opacity 0.6s; opacity:0.82; }
  .cat-card:hover img { transform: scale(1.08); opacity:0.65; }
  .cat-card-overlay { position:absolute; inset:0; background: linear-gradient(to top, rgba(10,10,10,0.8) 0%, transparent 60%); display:flex; flex-direction:column; justify-content:flex-end; padding:1.8rem; }
  .cat-card-name { font-family: var(--serif); font-size:1.4rem; font-weight:400; color:var(--white); line-height:1.2; }
  .cat-card-cta { font-size:0.68rem; letter-spacing:0.18em; text-transform:uppercase; color:var(--gold); margin-top:0.6rem; display:flex; align-items:center; gap:0.5rem; }
  .cat-card:hover .cat-card-cta { gap:0.9rem; }
  .cat-card-cta::after { content:'→'; }

  .products-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(260px,1fr)); gap:2rem; }
  .product-card { background:var(--white); position:relative; transition:transform 0.4s; }
  .product-card:hover { transform: translateY(-6px); }
  .product-img-wrap { position:relative; overflow:hidden; aspect-ratio:3/4; background:var(--beige); }
  .product-img-wrap img { width:100%; height:100%; object-fit:cover; transition: transform 0.6s; }
  .product-card:hover .product-img-wrap img { transform: scale(1.06); }
  .product-actions { position:absolute; bottom:0; left:0; right:0; background: rgba(10,10,10,0.9); display:flex; justify-content:center; padding:0.9rem; transform: translateY(100%); transition: transform 0.35s; }
  .product-card:hover .product-actions { transform: translateY(0); }
  .btn-cart { background:transparent; border:1px solid var(--gold); color:var(--gold); font-size:0.72rem; letter-spacing:0.15em; text-transform:uppercase; padding:0.6rem 1.8rem; cursor:pointer; width:100%; transition:background 0.3s,color 0.3s; }
  .btn-cart:hover { background:var(--gold); color:var(--black); }

  .why { background:var(--black); color:var(--white); }
  .why-grid { display:grid; grid-template-columns: repeat(auto-fill,minmax(220px,1fr)); gap:2.5rem; margin-top:4rem; }
  .why-card { border-top:1px solid rgba(201,169,110,0.25); padding-top:2rem; transition:border-color 0.3s; }
  .why-card:hover { border-color:var(--gold); }
  .why-title { font-family:var(--serif); font-size:1.3rem; margin-bottom:0.7rem; font-weight:400; }
  .why-desc { font-size:0.88rem; line-height:1.7; color:rgba(250,250,248,0.5); }

  .testimonials { background:var(--beige); }
  .testi-grid { display:grid; grid-template-columns: repeat(auto-fill,minmax(280px,1fr)); gap:2rem; margin-top:2rem; }
  .testi-card { background:var(--white); padding:2.5rem 2rem; border-bottom:2px solid transparent; transition:border-color 0.3s, transform 0.4s; }
  .testi-card:hover { border-color:var(--gold); transform:translateY(-4px); }
  .testi-quote { font-family:var(--serif); font-size:1.05rem; line-height:1.75; font-style:italic; margin-bottom:1.8rem; color:var(--black); }
  .testi-quote::before { content:'"'; font-size:2.5rem; color:var(--gold); line-height:0; vertical-align:-0.6rem; margin-right:0.2rem; }
  .testi-author { display:flex; align-items:center; gap:1rem; }
  .testi-avatar { width:44px; height:44px; border-radius:50%; object-fit:cover; border:2px solid var(--gold-light); }
  .testi-name { font-size:0.85rem; font-weight:500; }
  .testi-role { font-size:0.75rem; color:var(--text-muted); margin-top:0.2rem; }

  footer { background:var(--black); color:rgba(250,250,248,0.5); padding:5rem 5% 3rem; }
  .footer-top { display:grid; grid-template-columns:2fr 1fr 1fr 1.5fr; gap:3rem; margin-bottom:4rem; }
  .footer-brand-logo { font-family:var(--serif); font-size:2rem; color:var(--gold); font-weight:400; letter-spacing:0.08em; margin-bottom:1rem; }
  .footer-col h4 { font-family:var(--serif); font-size:1rem; color:var(--white); font-weight:400; margin-bottom:1.4rem; letter-spacing:0.05em; }
  .footer-col ul { list-style:none; display:flex; flex-direction:column; gap:0.7rem; }
  .footer-col ul a { color: rgba(250,250,248,0.45); text-decoration:none; font-size:0.83rem; transition: color 0.3s; }
  .footer-col ul a:hover { color:var(--gold); }

  @media (max-width:900px) { .footer-top { grid-template-columns:1fr 1fr; } .nav-links { display:none; } }
  @media (max-width:580px) { section { padding:5rem 5%; } .footer-top { grid-template-columns:1fr; } }
</style>
</head>
<body>

<!-NAV-->
<nav>
  <a href="#" class="nav-logo">Essy Haven</a>
  <ul class="nav-links">
    <li><a href="#categories">Collections</a></li>
    <li><a href="#products">Shop</a></li>
    <li><a href="#why">Why Choose Us</a></li>
    <li><a href="#testimonials">Reviews</a></li>
  </ul>
  <div class="nav-actions">
    <a href="#">Search</a>
    <a href="#" id="cart-link">Cart (0)</a>
  </div>
</nav>

<!-HERO-->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">New Season · 2025 Collection</p>
    <h1>Elevate Your <em>Everyday</em> Style</h1>
    <p>Premium fashion accessories crafted for confidence and class.</p>
    <div class="hero-btns">
      <a href="#products" class="btn-primary">Shop Now</a>
      <a href="#categories" class="btn-outline">Explore Collection</a>
    </div>
  </div>
</section>

<!-MARQUEE-->
<div class="marquee-strip">
  <div class="marquee-inner">
    <span>New Arrivals</span><span class="sep">✦</span>
    <span>Premium Quality</span><span class="sep">✦</span>
    <span>Trend-Driven Designs</span><span class="sep">✦</span>
    <span>Affordable Luxury</span><span class="sep">✦</span>
    <span>Free Shipping Over $150</span><span class="sep">✦</span>
  </div>
</div>

<!-CATEGORIES, PRODUCTS, WHY, TESTIMONIALS, CTA, FOOTER -->
<!-(These sections are already styled above, ready to add content as needed) -->

</body>
</html>
