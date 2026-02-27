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

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.4rem 5%;
    background: rgba(10,10,10,0.55);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(201,169,110,0.15);
    transition: background 0.4s;
  }
  .nav-logo { font-family: var(--serif); font-size: 1.7rem; font-weight: 500; color: var(--gold); letter-spacing: 0.08em; text-decoration: none; }
  .nav-links { display: flex; gap: 2.4rem; list-style: none; }
  .nav-links a { font-size: 0.78rem; letter-spacing: 0.12em; text-transform: uppercase; color: rgba(250,250,248,0.75); text-decoration: none; transition: color 0.3s; }
  .nav-links a:hover { color: var(--gold); }
  .nav-actions { display: flex; gap: 1.2rem; align-items: center; }
  .nav-actions a { color: rgba(250,250,248,0.75); text-decoration: none; font-size: 0.78rem; letter-spacing: 0.1em; text-transform: uppercase; transition: color 0.3s; }
  .nav-actions a:hover { color: var(--gold); }

  /* HERO */
  .hero { position: relative; height: 100vh; min-height: 600px; display: flex; align-items: center; justify-content: center; text-align: center; overflow: hidden; }
  .hero-bg {
    position: absolute; inset: 0;
    background: linear-gradient(to bottom, rgba(10,10,10,0.55) 0%, rgba(10,10,10,0.3) 50%, rgba(10,10,10,0.7) 100%),
      url('https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1800&q=80') center/cover no-repeat;
    transform: scale(1.05); transition: transform 8s ease;
  }
  .hero:hover .hero-bg { transform: scale(1); }
  .hero-content { position: relative; z-index: 2; max-width: 800px; padding: 0 2rem; }
  .hero-eyebrow { font-size: 0.72rem; letter-spacing: 0.25em; text-transform: uppercase; color: var(--gold); margin-bottom: 1.4rem; }
  .hero h1 { font-family: var(--serif); font-size: clamp(3rem,8vw,6.5rem); font-weight: 300; line-height: 1.05; color: var(--white); margin-bottom: 1.4rem; }
  .hero h1 em { font-style: italic; color: var(--gold-light); }
  .hero p { font-size: 1.05rem; line-height: 1.7; color: rgba(250,250,248,0.7); max-width: 500px; margin: 0 auto 2.8rem; }
  .hero-btns { display: flex; gap: 1.2rem; justify-content: center; flex-wrap: wrap; }
  .btn-primary { padding: 1rem 2.4rem; background: var(--gold); color: var(--black); font-size: 0.78rem; letter-spacing: 0.15em; text-transform: uppercase; text-decoration: none; font-weight: 500; transition: background 0.3s, transform 0.3s; }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }
  .btn-outline { padding: 1rem 2.4rem; border: 1px solid rgba(250,250,248,0.5); color: var(--white); font-size: 0.78rem; letter-spacing: 0.15em; text-transform: uppercase; text-decoration: none; transition: border-color 0.3s, color 0.3s, transform 0.3s; }
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); transform: translateY(-2px); }

  /* SECTION COMMON */
  section { padding: 7rem 5%; }
  .section-label { font-size: 0.68rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.8rem; }
  .section-title { font-family: var(--serif); font-size: clamp(2rem,4vw,3.4rem); font-weight: 300; line-height: 1.15; color: var(--black); }
  .section-subtitle { font-size: 0.95rem; color: var(--text-muted); line-height: 1.7; max-width: 480px; margin-top: 1rem; }
  .section-header { margin-bottom: 4rem; }
  .section-header.centered { text-align: center; }
  .section-header.centered .section-subtitle { margin: 1rem auto 0; }

  /* CATEGORIES */
  .categories { background: var(--beige); }
  .categories-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1.5rem; }
  .cat-card { position: relative; overflow: hidden; cursor: pointer; aspect-ratio: 3/4; background: var(--black); }
  .cat-card img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s cubic-bezier(0.22,1,0.36,1), opacity 0.6s; opacity: 0.82; }
  .cat-card:hover img { transform: scale(1.08); opacity: 0.65; }
  .cat-card-overlay { position: absolute; inset: 0; background: linear-gradient(to top, rgba(10,10,10,0.8) 0%, transparent 60%); display: flex; flex-direction: column; justify-content: flex-end; padding: 1.8rem; }
  .cat-card-name { font-family: var(--serif); font-size: 1.4rem; font-weight: 400; color: var(--white); line-height: 1.2; }
  .cat-card-cta { font-size: 0.68rem; letter-spacing: 0.18em; text-transform: uppercase; color: var(--gold); margin-top: 0.6rem; display: flex; align-items: center; gap: 0.5rem; }
  .cat-card-cta::after { content: '→'; }

  /* PRODUCTS */
  .products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 2rem; }
  .product-card { background: var(--white); position: relative; transition: transform 0.4s cubic-bezier(0.22,1,0.36,1); }
  .product-card:hover { transform: translateY(-6px); }
  .product-img-wrap { position: relative; overflow: hidden; aspect-ratio: 3/4; background: var(--beige); }
  .product-img-wrap img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s cubic-bezier(0.22,1,0.36,1); }
  .product-card:hover .product-img-wrap img { transform: scale(1.06); }
  .product-info { padding: 1.2rem 0.2rem 0.5rem; }
  .product-name { font-family: var(--serif); font-size: 1.15rem; font-weight: 400; margin-bottom: 0.4rem; }
  .product-price { font-size: 0.9rem; font-weight: 500; color: var(--black); }

  /* WHY */
  .why { background: var(--black); color: var(--white); }
  .why-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px,1fr)); gap: 2.5rem; margin-top: 4rem; }
  .why-card { border-top: 1px solid rgba(201,169,110,0.25); padding-top: 2rem; transition: border-color 0.3s; }
  .why-card:hover { border-color: var(--gold); }
  .why-icon { font-size: 2rem; margin-bottom: 1.2rem; }
  .why-title { font-family: var(--serif); font-size: 1.3rem; color: var(--white); margin-bottom: 0.7rem; font-weight: 400; }
  .why-desc { font-size: 0.88rem; color: rgba(250,250,248,0.7); line-height: 1.7; }

  /* TESTIMONIALS */
  .testimonials { background: var(--beige); }
  .testi-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px,1fr)); gap: 2rem; }
  .testi-card { background: var(--white); padding: 2.5rem 2rem; border-bottom: 2px solid transparent; transition: border-color 0.3s, transform 0.4s; }
  .testi-card:hover { border-color: var(--gold); transform: translateY(-4px); }
  .testi-quote { font-family: var(--serif); font-size: 1.05rem; line-height: 1.75; color: var(--black); font-style: italic; margin-bottom: 1.8rem; }
  .testi-quote::before { content: '"'; font-size: 2.5rem; color: var(--gold); line-height: 0; vertical-align: -0.6rem; margin-right: 0.2rem; }
  .testi-author { display: flex; align-items: center; gap: 1rem; }
  .testi-avatar { width: 44px; height: 44px; border-radius: 50%; object-fit: cover; border: 2px solid var(--gold-light); }
  .testi-name { font-size: 0.85rem; font-weight: 500; }
  .testi-role { font-size: 0.75rem; color: var(--text-muted); margin-top: 0.2rem; }

  /* FOOTER */
  footer { background: var(--black); color: rgba(250,250,248,0.5); padding: 5rem 5% 3rem; }

  /* MOBILE */
  @media (max-width: 900px) { .nav-links { display: none; } .products-grid, .why-grid, .testi-grid { grid-template-columns: 1fr; } }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Essy Haven</a>
  <ul class="nav-links">
    <li><a href="#categories">Collections</a></li>
    <li><a href="#products">Shop</a></li>
    <li><a href="#why">About</a></li>
    <li><a href="#testimonials">Reviews</a></li>
  </ul>
  <div class="nav-actions">
    <a href="#">Search</a>
    <a href="#">Cart (0)</a>
  </div>
</nav>

<!-- HERO -->
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

<!-- CATEGORIES -->
<section class="categories" id="categories">
  <div class="section-header fade-in">
    <p class="section-label">Curated for You</p>
    <h2 class="section-title">Shop by Category</h2>
    <p class="section-subtitle">Explore our carefully curated collections across every style dimension.</p>
  </div>
  <div class="categories-grid fade-in">
    <div class="cat-card"><img src="https://images.unsplash.com/photo-1596755094514-f87e34085b2c?w=600&q=80" alt="Shirts"/><div class="cat-card-overlay"><div class="cat-card-name">Shirts</div><div class="cat-card-cta">Shop Now</div></div></div>
    <div class="cat-card"><img src="https://images.unsplash.com/photo-1624378439575-d8705ad7ae80?w=600&q=80" alt="Trousers"/><div class="cat-card-overlay"><div class="cat-card-name">Trousers</div><div class="cat-card-cta">Shop Now</div></div></div>
    <div class="cat-card"><img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=600&q=80" alt="Shoes"/><div class="cat-card-overlay"><div class="cat-card-name">Shoes</div><div class="cat-card-cta">Shop Now</div></div></div>
    <div class="cat-card"><img src="https://images.unsplash.com/photo-1611591437281-460bfbe1220a?w=600&q=80" alt="Bracelets"/><div class="cat-card-overlay"><div class="cat-card-name">Bracelets</div><div class="cat-card-cta">Shop Now</div></div></div>
  </div>
</section>

<!-- WHY YOU SHOULD SHOP -->
<section class="why" id="why">
  <div class="section-header centered">
    <p class="section-label">Why Choose Us</p>
    <h2 class="section-title">Why You Should Shop With Essy Haven</h2>
  </div>
  <div class="why-grid">
    <div class="why-card"><div class="why-icon">💎</div><div class="why-title">Premium Quality</div><div class="why-desc">We provide top-tier fashion accessories crafted to perfection.</div></div>
    <div class="why-card"><div class="why-icon">🚚</div><div class="why-title">Fast Shipping</div><div class="why-desc">Quick delivery to ensure you get your items on time.</div></div>
    <div class="why-card"><div class="why-icon">💰</div><div class="why-title">Affordable Luxury</div><div class="why-desc">Luxury pieces without breaking the bank.</div></div>
    <div class="why-card"><div class="why-icon">⭐</div><div class="why-title">Customer Satisfaction</div><div class="why-desc">Our customers love us and return again and again.</div></div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials" id="testimonials">
  <div class="section-header centered">
    <p class="section-label">Reviews</p>
    <h2 class="section-title">What Our Customers Say</h2>
  </div>
  <div class="testi-grid">
    <div class="testi-card">
      <p class="testi-quote">Absolutely love the quality and design! Highly recommended.</p>
      <div class="testi-author"><img class="testi-avatar" src="https://randomuser.me/api/portraits/women/68.jpg" alt="Customer"/><div><div class="testi-name">Jane Doe</div><div class="testi-role">Fashion Enthusiast</div></div></div>
    </div>
    <div class="testi-card">
      <p class="testi-quote">Fast shipping and excellent customer service. Will shop again!</p>
      <div class="testi-author"><
