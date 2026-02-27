<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Essy Haven</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f8f8f8;
            color: #333;
        }

        header {
            background: black;
            color: white;
            padding: 20px;
            text-align: center;
        }

        nav {
            text-align: center;
            background: #222;
            padding: 10px;
        }

        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }

        .hero {
            background: url('https://images.unsplash.com/photo-1520975916090-3105956dac38') no-repeat center center/cover;
            color: white;
            text-align: center;
            padding: 100px 20px;
        }

        .hero h1 {
            font-size: 40px;
            margin-bottom: 10px;
        }

        .hero p {
            font-size: 18px;
        }

        .section {
            padding: 60px 20px;
            text-align: center;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            padding: 20px;
        }

        .product {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        .product img {
            width: 100%;
            border-radius: 5px;
        }

        footer {
            background: black;
            color: white;
            text-align: center;
            padding: 20px;
        }

        button {
            padding: 10px 20px;
            background: black;
            color: white;
            border: none;
            cursor: pointer;
            margin-top: 10px;
        }

        button:hover {
            background: #444;
        }
    </style>
</head>

<body>

<header>
    <h1>Essy Haven</h1>
    <p>Your Home of Premium Fashion Accessories</p>
</header>

<nav>
    <a href="#">Home</a>
    <a href="#products">Products</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
</nav>

<section class="hero">
    <h1>Elevate Your Style</h1>
    <p>Shirts • Trousers • Shoes • Bracelets • Necklaces</p>
    <button>Shop Now</button>
</section>

<section class="section" id="products">
    <h2>Our Products</h2>

    <div class="products">

        <div class="product">
            <img src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab" alt="Shirt">
            <h3>Premium Shirts</h3>
            <p>Modern, stylish and comfortable.</p>
        </div>

        <div class="product">
            <img src="https://images.unsplash.com/photo-1541099649105-f69ad21f3246" alt="Trousers">
            <h3>Classic Trousers</h3>
            <p>Tailored for elegance and class.</p>
        </div>

        <div class="product">
            <img src="https://images.unsplash.com/photo-1528701800489-20be3cddc6c9" alt="Shoes">
            <h3>Luxury Shoes</h3>
            <p>Walk with confidence and style.</p>
        </div>

        <div class="product">
            <img src="https://images.unsplash.com/photo-1519741497674-611481863552" alt="Accessories">
            <h3>Accessories</h3>
            <p>Bracelets and necklaces that shine.</p>
        </div>

    </div>
</section>

<section class="section" id="about">
    <h2>About Essy Haven</h2>
    <p>Essy Haven is a fashion brand focused on premium accessories and clothing designed to enhance confidence and elegance.</p>
</section>

<section class="section" id="contact">
    <h2>Contact Us</h2>
    <p>Email: info@essyhaven.com</p>
    <p>Phone: +234 000 000 0000</p>
</section>

<footer>
    <p>© 2026 Essy Haven. All Rights Reserved.</p>
</footer>

</body>
</html>https://images.unsplash.com/photo-1521572163474-6864f9cf17ab
