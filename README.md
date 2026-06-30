# Demo-website-


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Neighborhood Bakery | Fresh Local Bakes & Custom Cakes</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Playfair+Display:ital,wght@0,600;0,700;1,400&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-light: #FAF8F5;
            --primary-dark: #2C2523;
            --accent-pink: #F3D9DC;
            --text-dark: #3D3432;
            --text-light: #70625F;
            --white: #FFFFFF;
            --gray-light: #F0ECE7;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
            color: var(--primary-dark);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 38px;
            margin-bottom: 15px;
        }

        .section-subtitle {
            text-align: center;
            color: var(--text-light);
            max-width: 600px;
            margin: 0 auto 50px auto;
            font-size: 16px;
        }

        /* Navigation */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.02);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            text-decoration: none;
            color: var(--primary-dark);
        }

        nav a {
            text-decoration: none;
            color: var(--text-light);
            margin-left: 25px;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--primary-dark);
        }

        .cta-btn {
            background-color: var(--primary-dark);
            color: white;
            padding: 10px 22px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 500;
            font-size: 14px;
            transition: opacity 0.3s;
        }

        .cta-btn:hover {
            opacity: 0.9;
        }

        /* Hero Section */
        .hero {
            padding: 100px 0;
            display: flex;
            align-items: center;
            min-height: 70vh;
            background: linear-gradient(rgba(250, 248, 245, 0.85), rgba(250, 248, 245, 0.75)), url('https://images.unsplash.com/photo-1509440159596-0249088772ff?auto=format&fit=crop&w=1200&q=80') center/cover no-repeat;
        }

        .hero-content {
            max-width: 600px;
        }

        .hero h1 {
            font-size: 52px;
            margin-bottom: 20px;
            line-height: 1.15;
        }

        .hero p {
            font-size: 18px;
            color: var(--text-light);
            margin-bottom: 35px;
        }

        .btn-primary {
            background-color: var(--primary-dark);
            color: var(--white);
            padding: 15px 32px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            display: inline-block;
        }

        /* NEW LAYOUT 1: Visual Product Category Grid */
        .categories-section {
            padding: 90px 0;
            background-color: var(--white);
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .category-item {
            position: relative;
            border-radius: 12px;
            overflow: hidden;
            height: 350px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.03);
        }

        .category-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .category-item:hover .category-image {
            transform: scale(1.05);
        }

        .category-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(44, 37, 35, 0.9));
            padding: 30px 20px;
            color: var(--white);
        }

        .category-overlay h3 {
            color: var(--white);
            font-size: 20px;
            margin-bottom: 5px;
        }

        .category-overlay p {
            font-size: 13px;
            opacity: 0.8;
        }

        /* NEW LAYOUT 2: Multi-Column Features Banner */
        .features-section {
            padding: 80px 0;
            background-color: var(--bg-light);
            border-top: 1px solid var(--gray-light);
            border-bottom: 1px solid var(--gray-light);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 40px;
            text-align: center;
        }

        .feature-box h4 {
            font-size: 20px;
            margin-bottom: 10px;
        }

        .feature-box p {
            font-size: 14px;
            color: var(--text-light);
        }

        /* NEW LAYOUT 3: Asymmetric Gallery Showcase */
        .gallery-section {
            padding: 90px 0;
            background-color: var(--white);
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-auto-rows: 200px;
            gap: 20px;
        }

        .gallery-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 8px;
        }

        .gallery-item-1 { grid-column: span 2; grid-row: span 2; }
        .gallery-item-2 { grid-column: span 2; grid-row: span 1; }
        .gallery-item-3 { grid-column: span 1; grid-row: span 1; }
        .gallery-item-4 { grid-column: span 1; grid-row: span 1; }

        /* Menu Specialties Section */
        .specialties {
            padding: 90px 0;
            background-color: var(--bg-light);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .card {
            background-color: var(--white);
            padding: 45px 35px;
            border-radius: 16px;
            text-align: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.01);
        }

        /* About Block */
        .about {
            padding: 90px 0;
            background-color: var(--white);
        }

        .about-block {
            background-color: var(--accent-pink);
            padding: 60px;
            border-radius: 24px;
            color: var(--primary-dark);
            text-align: center;
            max-width: 900px;
            margin: 0 auto;
        }

        .about-block blockquote {
            font-family: 'Playfair Display', serif;
            font-size: 26px;
            font-style: italic;
            line-height: 1.5;
        }

        /* Footer */
        footer {
            background-color: var(--primary-dark);
            color: var(--white);
            padding: 60px 0 30px 0;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        footer h3, footer h4 {
            color: var(--bg-light);
            margin-bottom: 20px;
        }

        footer p {
            color: #A39693;
            margin-bottom: 10px;
            font-size: 15px;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.08);
            padding-top: 20px;
            text-align: center;
            font-size: 14px;
            color: #8A7D7A;
        }

        @media (max-width: 768px) {
            nav { display: none; }
            .hero h1 { font-size: 38px; }
            .gallery-grid { grid-template-columns: 1fr; grid-auto-rows: 250px; }
            .gallery-item-1, .gallery-item-2, .gallery-item-3, .gallery-item-4 { grid-column: span 1; grid-row: span 1; }
            .about-block { padding: 40px 20px; }
            .about-block blockquote { font-size: 20px; }
        }
    </style>
</head>
<body>

    <header>
        <div class="container nav-container">
            <a href="#" class="logo">The Bakery</a>
            <nav>
                <a href="#categories">Categories</a>
                <a href="#menu">Specialties</a>
                <a href="#gallery">Gallery</a>
                <a href="#contact">Find Us</a>
            </nav>
            <a href="#contact" class="cta-btn">Contact Shop</a>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Your Daily Dose of Freshly Baked Happiness.</h1>
                <p>Savor handcrafted artisan breads, custom celebration cakes, and delicious local pastries baked fresh daily right in your neighborhood.</p>
                <a href="#menu" class="btn-primary">View Our Specialties</a>
            </div>
        </div>
    </section>

    <section id="categories" class="categories-section">
        <div class="container">
            <h2 class="section-title">Explore Our Categories</h2>
            <p class="section-subtitle">From sunrise cravings to midnight celebrations, find exactly what your kitchen needs.</p>
            <div class="category-grid">
                <div class="category-item">
                    <img src="https://images.unsplash.com/photo-1509440159596-0249088772ff?auto=format&fit=crop&w=400&q=80" alt="Breads" class="category-image">
                    <div class="category-overlay">
                        <h3>Artisan Crusts</h3>
                        <p>Sourdough, whole-grain loaves, and country baguettes.</p>
                    </div>
                </div>
                <div class="category-item">
                    <img src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?auto=format&fit=crop&w=400&q=80" alt="Cakes" class="category-image">
                    <div class="category-overlay">
                        <h3>Celebration Cakes</h3>
                        <p>Creamy layers tailored for birthday milestones.</p>
                    </div>
                </div>
                <div class="category-item">
                    <img src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=400&q=80" alt="Pastries" class="category-image">
                    <div class="category-overlay">
                        <h3>Morning Pastries</h3>
                        <p>Flaky, golden croissants and filled sweet puffs.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="features-section">
        <div class="container">
            <div class="features-grid">
                <div class="feature-box">
                    <h4>🌾 100% Organic Flour</h4>
                    <p>Sourced ethically from premium local milling facilities.</p>
                </div>
                <div class="feature-box">
                    <h4>🔥 Oven-Fresh Daily</h4>
                    <p>Baked fresh every single morning before the sun comes up.</p>
                </div>
                <div class="feature-box">
                    <h4>🧁 Custom Requests</h4>
                    <p>Tailor flavors, frostings, and designs to your exact theme.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="menu" class="specialties">
        <div class="container">
            <h2 class="section-title">Fresh Daily Selections</h2>
            <p class="section-subtitle">Our signature treats prepared with classic standards and unique recipe balances.</p>
            <div class="grid">
                <div class="card">
                    <h3>🥐 Handcrafted Pastries</h3>
                    <p>Flaky croissants, sweet tarts, and savory morning puffs prepared daily by our baking team using premium local ingredients.</p>
                </div>
                <div class="card">
                    <h3>🎂 Custom Celebration Cakes</h3>
                    <p>Beautiful layered customized cakes made perfectly for birthdays, weddings, or any milestone event worth celebrating.</p>
                </div>
                <div class="card">
                    <h3>☕ Cozy Cafe Bites</h3>
                    <p>Take a break out of your morning and pair our warm oven bakes with exceptionally brewed hot coffee or afternoon teas.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="gallery" class="gallery-section">
        <div class="container">
            <h2 class="section-title">Behind the Counter</h2>
            <p class="section-subtitle">Take a visual stroll through our kitchen workshop and daily creations.</p>
            <div class="gallery-grid">
                <div class="gallery-item-1">
                    <img src="https://images.unsplash.com/photo-1549931319-a545dcf3bc73?auto=format&fit=crop&w=600&q=80" alt="Kitchen Prep" class="gallery-img">
                </div>
                <div class="gallery-item-2">
                    <img src="https://images.unsplash.com/photo-1517433456452-f9633a875f6f?auto=format&fit=crop&w=600&q=80" alt="Fresh Cookies" class="gallery-img">
                </div>
                <div class="gallery-item-3">
                    <img src="https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=300&q=80" alt="Donuts" class="gallery-img">
                </div>
                <div class="gallery-item-4">
                    <img src="https://images.unsplash.com/photo-1608686207856-001b95cf60ca?auto=format&fit=crop&w=300&q=80" alt="Buns" class="gallery-img">
                </div>
            </div>
        </div>
    </section>

    <section class="about">
        <div class="container">
            <div class="about-block">
                <blockquote>
                    "We blend traditional neighborhood baking values with sophisticated flavor profiles. Every morning, our ovens warm up to handcraft pure goodness so you start your day with something truly comforting."
                </blockquote>
            </div>
        </div>
    </section>

    <footer id="contact">
        <div class="container">
            <div class="footer-grid">
                <div>
                    <h3>Our Neighborhood Bakery</h3>
                    <p>Bringing warmth and premium confectionery bakes directly to your neighborhood kitchens every single day.</p>
                </div>
                <div>
                    <h4>Stop By Today</h4>
                    <p>📍 Available in your local community hub</p>
                    <p>Check your navigation map link to view exact location pins, directions, and instant neighborhood hours.</p>
                </div>
                <div>
                    <h4>Open Hours</h4>
                    <p>🕒 Mon - Sun: Fresh bakes ready from morning to evening.</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2026 Your Local Neighborhood Bakery. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

</body>
</html>