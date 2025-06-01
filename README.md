# index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beige The Pop Up Store</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.6;
            color: #5d4e37;
            background-color: #faf8f5;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #f5f2ed 0%, #e8e2d5 100%);
            padding: 20px 0;
            box-shadow: 0 2px 10px rgba(93, 78, 55, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            width: 120px;
            height: auto;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: #5d4e37;
            font-weight: 500;
            transition: color 0.3s ease;
            cursor: pointer;
        }

        .nav-links a:hover {
            color: #8fac7e;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #f9f6f0 0%, #f0ebe3 50%, #e8dcc6 100%);
            padding: 150px 0 80px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(143, 172, 126, 0.1) 0%, transparent 70%);
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            font-weight: 300;
            letter-spacing: 2px;
            color: #5d4e37;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 30px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            color: #6b6b6b;
        }

        .highlight {
            background: linear-gradient(120deg, #8fac7e 0%, #a8c090 100%);
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1.1rem;
            display: inline-block;
            margin-top: 20px;
            box-shadow: 0 4px 15px rgba(143, 172, 126, 0.3);
        }

        /* Section Styles */
        section {
            padding: 80px 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            color: #5d4e37;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 3px;
            background: linear-gradient(90deg, #8fac7e, #a8c090);
            margin: 20px auto;
            border-radius: 2px;
        }

        /* About Section */
        .about {
            background: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .about-features {
            background: linear-gradient(135deg, #f9f6f0, #f0ebe3);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .feature-item {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            font-size: 1.1rem;
        }

        .feature-icon {
            font-size: 1.5rem;
            margin-right: 15px;
            color: #8fac7e;
        }

        /* Products Section */
        .products {
            background: linear-gradient(135deg, #faf8f5 0%, #f5f2ed 100%);
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
        }

        .product-image {
            height: 200px;
            background: linear-gradient(45deg, #e8dcc6, #d4c5a9);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: #8fac7e;
        }

        .product-info {
            padding: 25px;
        }

        .product-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: #5d4e37;
        }

        .product-price {
            font-size: 1.1rem;
            color: #8fac7e;
            font-weight: 600;
        }

        /* Contact Section */
        .contact {
            background: white;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 50px;
        }

        .contact-card {
            background: linear-gradient(135deg, #f9f6f0, #f0ebe3);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        }

        .contact-icon {
            font-size: 2.5rem;
            color: #8fac7e;
            margin-bottom: 20px;
        }

        .contact-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: #5d4e37;
        }

        .contact-card p {
            line-height: 1.8;
            color: #6b6b6b;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #5d4e37 0%, #4a3f2a 100%);
            color: white;
            text-align: center;
            padding: 50px 0;
        }

        .footer-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: #8fac7e;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 2rem;
            }

            .product-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }

        /* Logo styling to match brand colors */
        .brand-logo {
            filter: sepia(100%) saturate(200%) hue-rotate(45deg) brightness(0.8);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <div class="logo">
                <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTAwIiBoZWlnaHQ9IjMwMCIgdmlld0JveD0iMCAwIDUwMCAzMDAiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxyZWN0IHdpZHRoPSI1MDAiIGhlaWdodD0iMzAwIiBmaWxsPSIjRkFGOEY1Ii8+CjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDcwIDEwMCkiPgo8cGF0aCBkPSJNMCAwSDE3LjU0MjVDMzcuMDc1IDAgNTMuNjI1IDE2LjU1IDUzLjYyNSAzNi45QzUzLjYyNSA0Ny4wNzUgNDkuNSA1Ni4yNSA0Mi45NSA2Mi44QzUwLjE3NSA2OC43IDU0LjY1IDc3LjUyNSA1NC42NSA4Ny4zNUM1NC42NSAxMDYuOTc1IDM4Ljc1IDEyMi44NzUgMTkuMTI1IDEyMi44NzVIMFYwWk0xNi4yIDM5TDE2LjIgNTkuNEwyMS4xNSA1OS40QzI1LjYyNSA1OS40IDI5LjI1IDU1Ljc3NSAyOS4yNSA1MS4zQzI5LjI1IDQ2LjgyNSAyNS42MjUgNDMuMiAyMS4xNSA0My4yTDE2LjIgNDMuMlpNMTYuMiAxNi4yTDE2LjIgMzNIMTkuMTI1QzIzLjI1IDMzIDI2LjMgMjkuOTUgMjYuMyAyNS44MjVDMjYuMyAyMS43IDIzLjI1IDE4LjY1IDE5LjEyNSAxOC42NUwxNi4yIDE4LjY1VjE2LjJaIiBmaWxsPSIjNUQ0RTM3Ii8+CjxwYXRoIGQ9Ik04OSA4MEwxMjcgODBDMTM5LjkgODAgMTUwLjQgNjkuNSAxNTAuNCA1Ni42QzE1MC40IDQ2LjEyNSAxNDMuODUgMzcuMjUgMTM0LjMgMzQuNjVWMzQuMzVDMTQ5LjQgMzAuNTc1IDE1OS43NSAxNi45IDE1OS43NSAwTDEzNi4xMjUgMEMxMzYuMTI1IDExLjE3NSAxMjguNTUgMjAuMjUgMTE4LjQgMjAuMjVMODkgMjAuMjVWMDBMNzIuOCAwVjE0MC44NUg4OVY4MFpNODkgMzkuNkwxMTcuMzkgMzkuNkMxMjIuMTY2IDM5LjYgMTI2LjY5MiA0MS40OTk5IDEzMC4wNzIgNDQuODhDMTMzLjQ1MiA0OC4yNjAxIDEzNS4zNTIgNTIuNzg3IDEzNS4zNTIgNTcuNTYzM0MxMzUuMzUyIDYyLjMzOTUgMTMzLjQ1MiA2Ni44NjY0IDEzMC4wNzIgNzAuMjQ2NUMxMjYuNjkyIDczLjYyNjYgMTIyLjE2NiA3NS41MjY1IDExNy4zOSA3NS41MjY1TDg5IDc1LjUyNjVWMzkuNloiIGZpbGw9IiM1RDRFMzciLz4KPHA+Ci48cGF0aCBkPSJNMTgzLjMgMTAwLjUwMkMxNzUuMzMzIDEwMC41MDIgMTY4IDk3LjkwMTggMTYyIDkzLjMwMTlDMTU2IDE4OC43IDE1My4yIDgxLjcwMTggMTUzLjIgNzIuNjAxOUMxNTMuMiA2My41MDE5IDE1NiA1Ni41MDIgMTYyIDUxLjkwMjFDMTY4IDQ3LjMwMjEgMTc1LjMzMyA0NC43MDIxIDE4My4zIDQ0LjcwMjFDMTkxLjI2NyA0NC43MDIxIDE5OC42IDQ3LjMwMjEgMjA0LjYgNTEuOTAyMUMyMTAuNiA1Ni41MDIxIDIxMy40IDYzLjUwMTkgMjEzLjQgNzIuNjAxOUMyMTMuNCA4MS43MDE4IDIxMC42IDg4LjcwMTggMjA0LjYgOTMuMzAxOUMxOTguNiA5Ny45MDE4IDE5MS4yNjcgMTAwLjUwMiAxODMuMyAxMDAuNTAyWk0xODMuMyA2MS4xMDJDMTc5IDYxLjEwMiAxNzUuNzUgNjIuNTUyMSAxNzMuNTUgNjUuNDUyMUMxNzEuMzUgNjguMzUyIDE3MC4yNSA3Mi42MDE5IDE3MC4yNSA3OC4yMDE5QzE3MC4yNSA4My44MDE5IDE3MS4zNSA4OC4wNTIgMTczLjU1IDkwLjk1MkMxNzUuNzUgOTMuODUyIDE3OSA5NS4zMDIxIDE4My4zIDk1LjMwMjFDMTg3LjYgOTUuMzAyMSAxOTAuODUgOTMuODUyIDE5My4wNSA5MC45NTJDMTU5LjI1IDg4LjA1MiAxOTEuMzUgODMuODAxOSAxOTYuMzUgNzguMjAxOUMxOTYuMzUgNzIuNjAxOSAxOTUuMjUgNjguMzUyIDE5My4wNSA2NS40NTJzMTkwLjggNTEuMTAyIDE4My4zIDYxLjEwMloiIGZpbGw9IiM1RDRFMzciLz4KPHBhdGggZD0iTTI1My40IDQ3VjAuNEwyMzguMyAwLjRWMTAwLjhIMjcyLjdDMjk1LjcgMTAwLjggMzEyLjE1IDg0LjM1IDMxMi4xNSA2MS4zNUMzMTIuMTUgMzguMzUgMjk1LjcgMjEuOSAyNzIuNyAyMS45TDI1My40IDIxLjlWNDdaTTI1My40IDM4LjNMMjcxLjcgMzguM00yODcuNSAzOC4zIDI5MC4yNSA0MS4wNUMyOTMgNDMuOCAyOTQuMzc1IDQ3LjQ3NSAyOTQuMzc1IDUxLjMwMkMyOTQuMzc1IDU1LjEyOSAyOTMgNTguODI1IDI5MC4yNSA2MS41NzVDMjg3LjUgNjQuMzI1IDI4My44IDY1LjcgMjgwIDY1LjdMMjUzLjQgNjUuN1YzOC4zWiIgZmlsbD0iIzVENEUzNyIvPgo8Y2lyY2xlIGNzPSI2Ni44MjUgLTg4IDMiIGN4PSIzNDQiIGN5PSI0OCIgcj0iMTIiIGZpbGw9IiM4RkFDN0UiLz4KPHRleHQgeD0iNDAiIHk9IjE2MCIgZm9udC1mYW1pbHk9Ikdlb3JnaWEsIHNlcmlmIiBmb250LXNpemU9IjI2IiBmaWxsPSIjOEZBQzdFIiBmb250LXN0eWxlPSJpdGFsaWMiPlRoZSBQb3AgVXAgU3RvcmU8L3RleHQ+Cjwvc3ZnPgo=" alt="Beige The Pop Up Store" style="width: 120px; height: auto;">
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Welcome to Beige The Pop Up Store</h1>
                <p>Step into a world of curated fashion and contemporary luxury. We are a multi-designer boutique showcasing India's most promising and established labels — all under one roof. From handcrafted festive edits to everyday statement pieces, we bring you affordable designer wear that redefines accessible luxury.</p>
                <div class="highlight">
                    🛍️ 40+ Designers | New Drops Every Month | Pop-Up Events Across Cities
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">India's Premier Multi-Designer Fashion Destination</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Founded by Harshavi Parikh and Chetan Desai, Beige The Pop Up Store began with a simple idea — to make designer fashion more accessible and experiential. What started as <em>Beige the Gallery</em> in Ahmedabad has now evolved into a multi-city platform hosting fashion pop-ups and designer showcases in Hyderabad, Vadodara, Anand, and beyond.</p>
                    <br>
                    <p>At Beige, we don't just sell clothes — we tell stories. Each piece in our collection is thoughtfully selected, often directly from the studios of India's most innovative and emerging designers. From Indo-Western fusion to occasionwear, every collection celebrates craftsmanship, affordability, and individuality.</p>
                </div>
                <div class="about-features">
                    <div class="feature-item">
                        <span class="feature-icon">🏪</span>
                        <span>Pop-Up Space</span>
                    </div>
                    <div class="feature-item">
                        <span class="feature-icon">✨</span>
                        <span>Designer Curation</span>
                    </div>
                    <div class="feature-item">
                        <span class="feature-icon">👥</span>
                        <span>Community Shopping</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products">
        <div class="container">
            <h2 class="section-title">New Arrivals</h2>
            <div class="product-grid">
                <div class="product-card">
                    <div class="product-image">👗</div>
                    <div class="product-info">
                        <div class="product-name">Sunset Bloom Co-ord Set</div>
                        <div class="product-price">₹4,999</div>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image">🥻</div>
                    <div class="product-info">
                        <div class="product-name">Chanderi Kaftan with Embroidery</div>
                        <div class="product-price">₹6,499</div>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image">👘</div>
                    <div class="product-info">
                        <div class="product-name">Classic Fusion Saree with Belt</div>
                        <div class="product-price">₹7,899</div>
                    </div>
                </div>
                <div class="product-card">
                    <div class="product-image">👑</div>
                    <div class="product-info">
                        <div class="product-name">Hand-Embellished Festive Gown</div>
                        <div class="product-price">₹8,299</div>
                    </div>
                </div>
            </div>
            <div style="text-align: center; margin-top: 40px;">
                <p style="font-style: italic; color: #8fac7e; font-size: 1.1rem;">✨ All designs are limited edition and available at our ongoing pop-ups.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-grid">
                <div class="contact-card">
                    <div class="contact-icon">📍</div>
                    <h3>Our Stores</h3>
                    <p><strong>Hyderabad</strong><br>H.No - 8-26, Plot No 26<br>Anthem Colony, Gundlapochampally<br>Secunderabad, Telangana - 500014</p>
                    <p><strong>Baroda</strong><br>Akota</p>
                    <p><strong>Anand</strong><br>Near Bhaikaka Statue</p>
                </div>
                <div class="contact-card">
                    <div class="contact-icon">📞</div>
                    <h3>Contact Info</h3>
                    <p><strong>Phone:</strong><br>+91-90005-10255</p>
                    <p><strong>Email:</strong><br>beigethepopupstore@gmail.com</p>
                </div>
                <div class="contact-card">
                    <div class="contact-icon">🤝</div>
                    <h3>Collaborate</h3>
                    <p>Want to showcase your brand with us?</p>
                    <p><strong>Instagram:</strong><br>@beigethepopupstore</p>
                    <p style="margin-top: 15px; font-weight: 600;">Drop us a message →</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="social-links">
                    <a href="#" title="Instagram">📷</a>
                    <a href="#" title="Email">📧</a>
                    <a href="#" title="Phone">📞</a>
                </div>
                <p>&copy; 2025 <strong>Beige The Pop Up Store</strong>. All rights reserved.</p>
                <p style="margin-top: 10px; font-style: italic;">Designed with love in India. Powered by storytelling, style, and strong coffee.</p>
                <div style="margin-top: 30px; font-size: 0.9rem; opacity: 0.8;">
                    <p><strong>Terms & Conditions:</strong> All sales are final unless explicitly mentioned. Exchange possible within 3 days on select items with tags intact.</p>
                    <p style="margin-top: 10px;"><strong>Privacy:</strong> We value your privacy and protect your data under applicable Indian data protection laws.</p>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add scroll effect to header
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(245, 242, 237, 0.95)';
                header.style.backdropFilter = 'blur(10px)';
            } else {
                header.style.background = 'linear-gradient(135deg, #f5f2ed 0%, #e8e2d5 100%)';
                header.style.backdropFilter = 'none';
            }
        });
    </script>
</body>
</html>
