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
  .hero-bg { position: absolute; inset: 0; background: linear-gradient(to bottom, rgba(10,10,10,0.55) 0%, rgba(10,10,10,0.3) 50%, rgba(10,10,10,0.7) 100%), url('https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=1800&q=80') center/cover no-repeat; transform: scale(1.05); transition: transform 8s ease; }
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
  @keyframes bounce { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transformX(-50%) translateY(6px); } }

  /* MARQUEE */
  .marquee-strip { background: var(--black); color: var(--gold); padding: 1rem 0; overflow: hidden; white-space: nowrap; }
  .marquee-inner { display: inline-block; animation: marquee 22s linear infinite; font-family: var(--serif); font-size: 1.1rem; font-style: italic; letter-spacing: 0.05em; }
  .marquee-inner span { margin: 0 2.5rem; }
  .marquee-inner .sep { color: rgba(201,169,110,0.4); }
  @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }

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
  .cat-card-cta { font-size: 0.68rem; letter-spacing: 0.18em; text-transform: uppercase; color: var(--gold); margin-top: 0.6rem; display: flex; align-items: center; gap: 0.5rem; transition: gap 0.3s; }
  .cat-card:hover .cat-card-cta { gap: 0.9rem; }
  .cat-card-cta::after { content: '→'; }

  /* PRODUCTS GRID */
  .products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px,1fr)); gap: 2rem; }
  .product-card { background: var(--white); position: relative; transition: transform 0.4s cubic-bezier(0.22,1,0.36,1); }
  .product-card:hover { transform: translateY(-6px); }
  .product-img-wrap { position: relative; overflow: hidden; aspect-ratio: 3/4; background: var(--beige); }
  .product-img-wrap img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s cubic-bezier(0.22,1,0.36,1); }
  .product-card:hover .product-img-wrap img { transform: scale(1.06); }
  .product-badge { position: absolute; top: 1rem; left: 1rem; background: var(--black); color: var(--gold); font-size: 0.62rem; letter-spacing: 0.15em; text-transform: uppercase; padding: 0.3rem 0.7rem; }
  .product-actions { position: absolute; bottom: 0; left: 0; right: 0; background: rgba(10,10,10,0.9); display: flex; justify-content: center; padding: 0.9rem; transform: translateY(100%); transition: transform 0.35s cubic-bezier(0.22,1,0.36,1); }
  .product-card:hover .product-actions { transform: translateY(0); }
  .btn-cart { background: transparent; border: 1px solid var(--gold); color: var(--gold); font-size: 0.72rem; letter-spacing: 0.15em; text-transform: uppercase; padding: 0.6rem 1.8rem; cursor: pointer; transition: background 0.3s, color 0.3s; width: 100%; }
  .btn-cart:hover { background: var(--gold); color: var(--black); }
  .product-info { padding: 1.2rem 0.2rem 0.5rem; }
  .product-name { font-family: var(--serif); font-size: 1.15rem; font-weight: 400; margin-bottom: 0.4rem; }
  .product-meta { display: flex; justify-content: space-between; align-items: center; }
  .product-price { font-size: 0.9rem; font-weight: 500; color: var(--black); }
  .product-price .old { color: var(--text-muted); text-decoration: line-through; margin-right: 0.5rem; font-weight: 300; }
  .product-stars { color: var(--gold); font-size: 0.72rem; letter-spacing: 0.1em; }

  /* WHY SHOP */
  .why { background: var(--black); }
  .why .section-title { color: var(--white); }
  .why .section-label { color: var(--gold); }
  .why-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px,1fr)); gap: 2.5rem; margin-top: 4rem; }
  .why-card { border-top: 1px solid rgba(201,169,110,0.25); padding-top: 2rem; transition: border-color 0.3s; }
  .why-card:hover { border-color: var(--gold); }
  .why-icon { font-size: 2rem; margin-bottom: 1.2rem; filter: sepia(1) saturate(3) hue-rotate(5deg); }
  .why-title { font-family: var(--serif); font-size: 1.3rem; color: var(--white); margin-bottom: 0.7rem; font-weight: 400; }
  .why-desc { font-size: 0.88rem; color: rgba(250,250,248,0.5); line-height: 1.7; }

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

  /* CTA BAND */
  .cta-band { position: relative; overflow: hidden; min-height: 420px; display: flex; align-items: center; justify-content: center; text-align: center; padding: 7rem 5%; }
  .cta-band-bg { position: absolute; inset: 0; background: linear-gradient(135deg, rgba(10,10,10,0.92) 0%, rgba(10,10,10,0.7) 100%), url('https://images.unsplash.com/photo-1490481651871-ab68de25d43d?w=1400&q=80') center/cover; }
  .cta-band-content { position: relative; z-index: 2; max-width: 680px; }
  .cta-band h2 { font-family: var(--serif); font-size: clamp(2.4rem,5vw,4.5rem); font-weight: 300; color: var(--white); line-height: 1.1; margin-bottom: 0.8rem; }
  .cta-band h2 em { font-style: italic; color: var(--gold-light); }
  .cta-band p { color: rgba(250
