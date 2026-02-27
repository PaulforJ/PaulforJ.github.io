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

  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.4rem 5%;
    background: rgba(10,10,10,0.55);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(201,169,110,0.15);
  }
  .nav-logo { font-family: var(--serif); font-size: 1.7rem; font-weight: 500; color: var(--gold); letter-spacing: 0.08em; text-decoration: none; }
  .nav-links { display: flex; gap: 2.4rem; list-style: none; }
  .nav-links a { font-size: 0.78rem; letter-spacing: 0.12em; text-transform: uppercase; color: rgba(250,250,248,0.75); text-decoration: none; }
  .nav-links a:hover { color: var(--gold); }
  .nav-actions { display: flex; gap: 1.2rem; align-items: center; }
  .nav-actions a { color: rgba(250,250,248,0.75); text-decoration: none; font-size: 0.78rem; letter-spacing: 0.1em; text-transform: uppercase; }

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
  .btn-primary { padding: 1rem 2.4rem; background: var(--gold); color: var(--black); font-size: 0.78rem; letter-spacing: 0.15em; text-transform: uppercase; font-weight: 500; text-decoration: none; }
  .btn-outline { padding: 1rem 2.4rem; border: 1px solid rgba(250,250,248,0.5); color: var(--white); font-size: 0.78rem; letter-spacing: 0.15em; text-transform: uppercase; text-decoration: none; }
  .scroll-hint { position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: 0.5rem; color: rgba(250,250,248,0.4); font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase; }

  section { padding: 7rem 5%; }
  .section-label { font-size: 0.68rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.8rem; }
  .section-title { font-family: var(--serif); font-size: clamp(2rem,4vw,3.4rem); font-weight: 300; line-height: 1.15; color: var(--black); }
  .section-subtitle { font-size: 0.95rem; color: var(--text-muted); line-height: 1.7; max-width: 480px; margin-top: 1rem; }
  .section-header { margin-bottom: 4rem; }
  .section-header.centered { text-align: center; }

  .categories { background: var(--beige); }
  .categories-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1.5rem; }
  .cat-card { position: relative; overflow: hidden; cursor: pointer; aspect-ratio: 3/4; background: var(--black); }
  .cat-card img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s, opacity 0.6s; opacity: 0.82; }
  .cat-card:hover img { transform: scale(1.08); opacity: 0.65; }
  .cat-card-overlay { position: absolute; inset: 0; background: linear-gradient(to top, rgba(10,10,10,0.8) 0%, transparent 60%); display: flex; flex-direction: column; justify-content: flex-end; padding: 1.8rem; }
  .cat-card-name { font-family: var(--serif); font-size: 1.4rem; font-weight: 400; color: var(--white); line-height: 1.2; }
  .cat-card-cta { font-size: 0.68rem; letter-spacing: 0.18em; text-transform: uppercase; color: var(--gold); margin-top: 0.6rem; display: flex; align-items: center; gap: 0.5rem; }
  .cat-card-cta::after { content: '→'; }

  footer { background: var(--black); color: rgba(250,250,248,0.5); padding: 5rem 5% 3rem; }
  .footer-brand-logo { font-family: var(--serif); font-size: 2rem; color: var(--gold); font-weight: 400; letter-spacing: 0.08em; display: block; margin-bottom: 1rem; }
</style>
</head>
<body>

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
    <a href="#" id="cart-link">Cart (0)</a>
  </div>
</nav>

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
  <div class="scroll-hint">Scroll</div>
</section>

<section class="categories" id="categories">
  <div class="section-header centered">
    <p class="section-label">Curated for You</p>
    <h2 class="section-title">Shop by Category</h2>
    <p class="section-subtitle">Explore our carefully curated collections across every style dimension.</p>
  </div>
  <div class="categories-grid">
    <div class="cat-card">
      <img src="https://images.unsplash.com/photo-1596755094514-f87e34085b2c?w=600&q=80" alt="Shirts"/>
      <div class="cat-card-overlay">
        <div class="cat-card-name">Shirts</div>
        <div class="cat-card-cta">Shop Now</div>
      </div>
    </div>
    <div class="cat-card">
      <img src="https://images.unsplash.com/photo-1624378439575-d8705ad7ae80?w=600&q=80" alt="Trousers"/>
      <div class="cat-card-overlay">
        <div class="cat-card-name">Trousers</div>
        <div class="cat-card-cta">Shop Now</div>
      </div>
    </div>
    <div class="cat-card">
      <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=600&q=80" alt="Shoes"/>
      <div class="cat-card-overlay">
        <div class="cat-card-name">Shoes</div>
        <div class="cat-card-cta">Shop Now</div>
      </div>
    </div>
  </div>
</section>

<footer>
  <span class="footer-brand-logo">Essy Haven</span>
  <p>Premium fashion accessories for everyday style and elegance.</p>
</footer>

</body>
</html>
