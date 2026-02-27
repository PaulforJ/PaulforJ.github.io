<DOCTYPE html>
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
  .hero-content { position: relative; z-index: 2; max-width: 800px; padding: 0 2rem; animation: heroFadeUp 1.2s cubic-bezier(0.22,1,0.36,1) both; }
  @keyframes heroFadeUp { from { opacity: 0; transform: translateY(40px); } to { opacity: 1; transform: translateY(0); } }
  .hero-eyebrow { font-size: 0.72rem; letter-spacing: 0.25em; text-transform: uppercase; color: var(--gold); margin-bottom: 1.4rem; animation: heroFadeUp 1.2s 0.1s cubic-bezier(0.22,1,0.36,1) both; }
  .hero h1 { font-family: var(--serif); font-size: clamp(3rem,8vw,6.5rem); font-weight: 300; line-height: 1.05; color: var(--white); margin-bottom: 1.4rem; animation: heroFadeUp 1.2s 0.2s cubic-bezier(0.22,1,0.36,1) both; }
  .hero h1 em { font-style: italic; color: var(--gold-light); }
  .hero p { font-size: 1.05rem; line-height: 1.7; color: rgba(250,250,248,0.7); max-width: 500px; margin: 0 auto 2.8rem; animation: heroFadeUp 1.2s 0.35s cubic-bezier(0.22,1,0.36,1) both; }
  .hero-btns { display: flex; gap: 1.2rem; justify-content: center; flex-wrap: wrap; animation: heroFadeUp 1.2s 0.5s cubic-bezier(0.22,1,0.36,1) both; }
  .btn-primary { padding: 1rem 2.4rem; background: var(--gold); color: var(--black); font-size: 0.78rem; letter-spacing: 0.15em; text-transform: uppercase; text-decoration: none; font-weight: 500; transition: background 0.3s, transform 0.3s; }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }
  .btn-outline { padding: 1rem 2.4rem; border: 1px solid rgba(250,250,248,0.5); color: var(--white); font-size: 0.78rem; letter-spacing: 0.15em; text-transform: uppercase; text-decoration: none; transition: border-color 0.3s, color 0.3s, transform 0.3s; }
  .btn-outline:hover { border-color: var(--gold); color: var(--gold); transform: translateY(-2px); }
  .scroll-hint { position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; gap: 0.5rem; color: rgba(250,250,248,0.4); font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase; animation: bounce 2s infinite; }
  .scroll-hint::after { content: ''; display: block; width: 1px; height: 3rem; background: linear-gradient(to bottom, var(--gold), transparent); }
  @keyframes bounce { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(6px); } }

  /* SECTION COMMON */
  section { padding: 7rem 5%; }
  .section-label { font-size: 0.68rem; letter-spacing: 0.3em; text-transform: uppercase; color: var(--gold); margin-bottom: 0.8rem; }
  .section-title { font-family: var(--serif); font-size: clamp(2rem,4vw,3.4rem); font-weight: 300; line-height: 1.15; color: var(--black); }
  .section-subtitle { font-size: 0.95rem; color: var(--text-muted); line-height: 1.7; max-width: 480px; margin-top: 1rem; }
  .section-header { margin-bottom: 4rem; }
  .section-header.centered { text-align: center; }
  .section-header.centered .section-subtitle { margin: 1rem auto 0; }

  /* MARQUEE */
  .marquee-strip { background: var(--black); color: var(--gold); padding: 1rem 0; overflow: hidden; white-space: nowrap; }
  .marquee-inner { display: inline-block; animation: marquee 22s linear infinite; font-family: var(--serif); font-size: 1.1rem; font-style: italic; letter-spacing: 0.05em; }
  .marquee-inner span { margin: 0 2.5rem; }
  .marquee-inner .sep { color: rgba(201,169,110,0.4); }
  @keyframes marquee { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }

  /* CATEGORIES, PRODUCTS, WHY, CTA, NEWSLETTER, FOOTER styles remain as before */
  /* ... (for brevity, reuse your previous CSS for categories, products, why, testimonials, footer) ... */

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
  .testi-stars { color: var(--gold); font-size: 0.7rem; margin-bottom: 1rem; }

  /* MOBILE */
  @media (max-width: 900px) { .footer-top { grid-template-columns: 1fr 1fr; } .nav-links { display: none; } }
  @media (max-width: 580px) { section { padding: 5rem 5%; } .footer-top { grid-template-columns: 1fr; } }

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
    <a href="#" id="cart-link">Cart (0)</a>
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
  <div class="scroll-hint">Scroll</div>
</section>

<!-- MARQUEE -->
<div class="marquee-strip">
  <div class="marquee-inner">
    <span>New Arrivals</span><span class="sep">✦</span>
    <span>Premium Quality</span><span class="sep">✦</span>
    <span>Trend-Driven Designs</span><span class="sep">✦</span>
    <span>Affordable Luxury</span><span class="sep">✦</span>
    <span>Free Shipping Over $150</span><span class="sep">✦</span>
    <span>New Arrivals</span><span class="sep">✦</span>
    <span>Premium Quality</span><span class="sep">✦</span>
  </div>
</div>

<!-- CATEGORIES, PRODUCTS, WHY sections go here -->

<!-- TESTIMONIALS -->
<section class="testimonials" id="testimonials">
  <div class="section-header centered">
    <p class="section-label">Loved by Customers</p>
    <h2 class="section-title">What People Are Saying</h2>
  </div>
  <div class="testi-grid">
    <div class="testi-card">
      <p class="testi-quote">I absolutely love the quality and style of Essy Haven products. They elevate every outfit!</p>
      <div class="testi-author">
        <img src="https://randomuser.me/api/portraits/women/45.jpg" alt="Customer" class="testi-avatar">
        <div>
          <div class="testi-name">Sophia M.</div>
          <div class="testi-role">Fashion Enthusiast</div>
          <div class="testi-stars">★★★★★</div>
        </div>
      </div>
    </div>
    <div class="testi-card">
      <p class="testi-quote">The attention to detail is unmatched. Shipping was fast and the products feel premium.</p>
      <div class="testi-author">
        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Customer" class="testi-avatar">
        <div>
          <div class="testi-name">Liam R.</div>
          <div class="testi-role">Style Blogger</div>
          <div class="testi-stars">★★★★★</div>
        </div>
      </div>
    </div>
    <div class="testi-card">
      <p class="testi-quote">Essy Haven has become my go-to for accessories. Each piece feels like it was made just for me.</p>
      <div class="testi-author">
        <img src="https://randomuser.me/api/portraits/women/65.jpg" alt="Customer" class="testi-avatar">
        <div>
          <div class="testi-name">Amara K.</div>
          <div class="testi-role">Entrepreneur</div>
          <div class="testi-stars">★★★★★</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Remaining sections: CTA, Newsletter, Footer go here -->

</body>
</html>
