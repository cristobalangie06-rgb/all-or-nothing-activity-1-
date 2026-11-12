# all-or-nothing-activity-1-
``html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Savoria Restaurant</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: Georgia, "Times New Roman", serif;
            background: #f8f3ec;
            color: #33261f;
            line-height: 1.6;
        }

        /* =========================
           NAVIGATION
        ========================= */

        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(255, 250, 244, 0.97);
            box-shadow: 0 3px 15px rgba(70, 40, 20, 0.12);
        }

        nav {
            max-width: 1200px;
            margin: auto;
            padding: 18px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            color: #8b3f2f;
            font-size: 28px;
            font-weight: bold;
            letter-spacing: 1px;
        }

        .logo span {
            color: #c89552;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 28px;
        }

        nav a {
            text-decoration: none;
            color: #49362b;
            font-family: Arial, sans-serif;
            font-weight: bold;
            font-size: 14px;
            transition: 0.3s;
        }

        nav a:hover {
            color: #b2643d;
        }

        /* =========================
           HERO
        ========================= */

        .hero {
            min-height: 88vh;
            display: flex;
            align-items: center;
            padding: 60px 8%;

            background:
                linear-gradient(
                    rgba(35, 18, 12, 0.60),
                    rgba(35, 18, 12, 0.48)
                ),
                url("https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1600&q=80")
                center/cover;
        }

        .hero-content {
            max-width: 760px;
            color: white;
        }

        .small-title {
            color: #f1c27d;
            letter-spacing: 4px;
            font-family: Arial, sans-serif;
            font-size: 13px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .hero h1 {
            font-size: clamp(48px, 8vw, 85px);
            line-height: 0.95;
            margin-bottom: 25px;
        }

        .hero h1 span {
            color: #e7b36e;
        }

        .hero p {
            font-family: Arial, sans-serif;
            font-size: 17px;
            max-width: 650px;
            color: #f8eee4;
        }

        .btn {
            display: inline-block;
            margin-top: 30px;
            padding: 14px 28px;
            background: #a94f34;
            color: white;
            text-decoration: none;
            font-family: Arial, sans-serif;
            font-weight: bold;
            border-radius: 4px;
            transition: 0.3s;
        }

        .btn:hover {
            background: #d0924e;
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }

        /* =========================
           GENERAL SECTIONS
        ========================= */

        section {
            padding: 90px 7%;
        }

        .section-heading {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 50px;
        }

        .section-heading .label {
            color: #b2643d;
            font-family: Arial, sans-serif;
            font-size: 12px;
            font-weight: bold;
            letter-spacing: 3px;
        }

        .section-heading h2 {
            color: #7d382a;
            font-size: 43px;
            margin: 10px 0;
        }

        .section-heading p {
            color: #78675d;
            font-family: Arial, sans-serif;
        }

        /* =========================
           ABOUT
        ========================= */

        .about {
            background: #fffaf5;
        }

        .about-container {
            max-width: 1100px;
            margin: auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-image {
            min-height: 450px;
            border-radius: 4px;

            background:
                url("https://images.unsplash.com/photo-1552566626-52f8b828add9?auto=format&fit=crop&w=1000&q=80")
                center/cover;

            box-shadow: 20px 20px 0 #ead7c2;
        }

        .about-text h3 {
            font-size: 32px;
            color: #3d2b22;
            margin-bottom: 20px;
        }

        .about-text p {
            color: #706158;
            font-family: Arial, sans-serif;
            margin-bottom: 18px;
        }

        /* =========================
           MENU
        ========================= */

        .menu {
            background: #f2e8dc;
        }

        .menu-grid {
            max-width: 1100px;
            margin: auto;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 22px;
        }

        .menu-item {
            background: #fffaf5;
            padding: 25px;
            display: flex;
            justify-content: space-between;
            gap: 20px;
            border-bottom: 2px solid #e3cdb7;
            transition: 0.3s;
        }

        .menu-item:hover {
            transform: translateX(7px);
            border-bottom-color: #a94f34;
            box-shadow: 0 8px 20px rgba(80, 45, 25, 0.10);
        }

        .food-info h3 {
            color: #7d382a;
            font-size: 20px;
            margin-bottom: 6px;
        }

        .food-info p {
            color: #75665d;
            font-family: Arial, sans-serif;
            font-size: 14px;
        }

        .price {
            color: #b2643d;
            font-size: 19px;
            font-weight: bold;
            white-space: nowrap;
        }

        /* =========================
           SPECIALS
        ========================= */

        .specials {
            background: #7d382a;
            color: white;
        }

        .specials .section-heading h2 {
            color: #f4c983;
        }

        .specials .section-heading p {
            color: #ead9cc;
        }

        .special-grid {
            max-width: 1050px;
            margin: auto;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .special-card {
            padding: 35px 25px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.25);
            background: rgba(255,255,255,0.07);
            transition: 0.3s;
        }

        .special-card:hover {
            transform: translateY(-8px);
            background: rgba(255,255,255,0.13);
        }

        .special-card .icon {
            font-size: 42px;
            margin-bottom: 15px;
        }

        .special-card h3 {
            color: #f4c983;
            font-size: 23px;
            margin-bottom: 10px;
        }

        .special-card p {
            color: #f2e6dc;
            font-family: Arial, sans-serif;
            font-size: 14px;
        }

        /* =========================
           EXPERIENCE
        ========================= */

        .experience {
            background: #fffaf5;
        }

        .experience-grid {
            max-width: 1100px;
            margin: auto;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .experience-card {
            text-align: center;
            padding: 35px 25px;
            border: 1px solid #ead9c6;
        }

        .experience-card .number {
            font-size: 42px;
            color: #b2643d;
            font-weight: bold;
        }

        .experience-card h3 {
            color: #49362b;
            margin: 8px 0;
        }

        .experience-card p {
            color: #78675d;
            font-family: Arial, sans-serif;
            font-size: 14px;
        }

        /* =========================
           RESERVATION
        ========================= */

        .reservation {
            background:
                linear-gradient(rgba(42, 22, 14, 0.85), rgba(42, 22, 14, 0.85)),
                url("https://images.unsplash.com/photo-1414235077428-338989a2e8c0?auto=format&fit=crop&w=1600&q=80")
                center/cover;
            color: white;
            text-align: center;
        }

        .reservation h2 {
            font-size: 45px;
            color: #f4c983;
            margin-bottom: 15px;
        }

        .reservation p {
            max-width: 650px;
            margin: auto;
            color: #eee0d6;
            font-family: Arial, sans-serif;
        }

        .reservation-box {
            max-width: 800px;
            margin: 35px auto 0;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }

        .reservation-box div {
            padding: 18px;
            border: 1px solid rgba(255,255,255,0.3);
        }

        .reservation-box strong {
            display: block;
            color: #f4c983;
            margin-bottom: 5px;
        }

        /* =========================
           CONTACT
        ========================= */

        .contact {
            background: #f2e8dc;
        }

        .contact-container {
            max-width: 1000px;
            margin: auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .contact-info h3 {
            color: #7d382a;
            font-size: 28px;
            margin-bottom: 20px;
        }

        .contact-info p {
            font-family: Arial, sans-serif;
            color: #6f6159;
            margin-bottom: 12px;
        }

        .contact-info strong {
            color: #49362b;
        }

        .hours {
            background: #fffaf5;
            padding: 30px;
            border-left: 5px solid #a94f34;
        }

        .hours h3 {
            color: #7d382a;
            margin-bottom: 15px;
        }

        .hours p {
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #e4d5c5;
            padding: 8px 0;
            font-family: Arial, sans-serif;
            color: #6f6159;
        }

        /* =========================
           FOOTER
        ========================= */

        footer {
            background: #2b1913;
            color: #bbaaa0;
            text-align: center;
            padding: 28px 20px;
            font-family: Arial, sans-serif;
        }

        footer strong {
            color: #e7b36e;
        }

        /* =========================
           RESPONSIVE
        ========================= */

        @media (max-width: 850px) {

            nav {
                flex-direction: column;
                gap: 15px;
            }

            nav ul {
                flex-wrap: wrap;
                justify-content: center;
                gap: 15px;
            }

            .about-container,
            .contact-container {
                grid-template-columns: 1fr;
            }

            .menu-grid {
                grid-template-columns: 1fr;
            }

            .special-grid,
            .experience-grid {
                grid-template-columns: 1fr 1fr;
            }

            .about-image {
                min-height: 350px;
            }
        }

        @media (max-width: 600px) {

            .hero {
                min-height: 75vh;
                padding: 40px 6%;
            }

            .hero h1 {
                font-size: 50px;
            }

            section {
                padding: 65px 5%;
            }

            .section-heading h2 {
                font-size: 34px;
            }

            .special-grid,
            .experience-grid,
            .reservation-box {
                grid-template-columns: 1fr;
            }

            nav {
                padding: 15px;
            }

            nav ul {
                gap: 10px;
            }

            nav a {
                font-size: 12px;
            }
        }
    </style>
</head>

<body>

<!-- =========================
     NAVIGATION
========================= -->

<header>
    <nav>

        <div class="logo">
            Savor<span>ia</span>
        </div>

        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#menu">Menu</a></li>
            <li><a href="#specials">Specials</a></li>
            <li><a href="#reservation">Reservation</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>

    </nav>
</header>


<!-- =========================
     HOME
========================= -->

<section id="home" class="hero">

    <div class="hero-content">

        <div class="small-title">
            WELCOME TO SAVORIA
        </div>

        <h1>
            Taste the Art<br>
            of <span>Good Food.</span>
        </h1>

        <p>
            A warm dining experience where delicious food,
            beautiful moments, and unforgettable flavors come together.
        </p>

        <a href="#menu" class="btn">
            Explore Our Menu
        </a>

    </div>

</section>


<!-- =========================
     ABOUT
========================= -->

<section id="about" class="about">

    <div class="section-heading">

        <div class="label">
            OUR STORY
        </div>

        <h2>Made With Passion</h2>

        <p>
            More than a restaurant — Savoria is a place to gather,
            celebrate, and enjoy good food.
        </p>

    </div>


    <div class="about-container">

        <div class="about-image"></div>

        <div class="about-text">

            <h3>Where Every Meal Becomes a Memory</h3>

            <p>
                At Savoria, we believe great food is best enjoyed
                with great company. Our restaurant combines carefully
                prepared dishes with a warm and welcoming atmosphere.
            </p>

            <p>
                We use fresh ingredients and thoughtful preparation
                to create meals that are comforting, flavorful,
                and memorable.
            </p>

            <p>
                Whether you're having dinner with family, meeting
                friends, or celebrating a special occasion,
                there's always a place for you at Savoria.
            </p>

            <a href="#contact" class="btn">
                Visit Us
            </a>

        </div>

    </div>

</section>


<!-- =========================
     MENU
========================= -->

<section id="menu" class="menu">

    <div class="section-heading">

        <div class="label">
            OUR MENU
        </div>

        <h2>Favorites From Our Kitchen</h2>

        <p>
            A selection of dishes made to satisfy every craving.
        </p>

    </div>


    <div class="menu-grid">

        <div class="menu-item">

            <div class="food-info">

                <h3>Truffle Cream Pasta</h3>

                <p>
                    Creamy pasta with parmesan, mushrooms,
                    herbs, and truffle flavor.
                </p>

            </div>

            <div class="price">
                ₱395
            </div>

        </div>


        <div class="menu-item">

            <div class="food-info">

                <h3>Grilled Chicken</h3>

                <p>
                    Tender grilled chicken served with
                    seasonal vegetables and house sauce.
                </p>

            </div>

            <div class="price">
                ₱420
            </div>

        </div>


        <div class="menu-item">

            <div class="food-info">

                <h3>Beef Steak</h3>

                <p>
                    Juicy grilled beef with roasted vegetables
                    and signature steak sauce.
                </p>

            </div>

            <div class="price">
                ₱650
            </div>

        </div>


        <div class="menu-item">

            <div class="food-info">

                <h3>Crispy Calamari</h3>

                <p>
                    Golden calamari served with lemon
                    and creamy dipping sauce.
                </p>

            </div>

            <div class="price">
                ₱350
            </div>

        </div>


        <div class="menu-item">

            <div class="food-info">

                <h3>Garden Salad</h3>

                <p>
                    Fresh greens, tomatoes, cucumber,
                    cheese, and house dressing.
                </p>

            </div>

            <div class="price">
                ₱280
            </div>

        </div>


        <div class="menu-item">

            <div class="food-info">

                <h3>Chocolate Lava Cake</h3>

                <p>
                    Warm chocolate cake with a rich molten
                    center and vanilla cream.
                </p>

            </div>

            <div class="price">
                ₱250
            </div>

        </div>

    </div>

</section>


<!-- =========================
     SPECIALS
========================= -->

<section id="specials" class="specials">

    <div class="section-heading">

        <div class="label">
            WHY SAVORIA
        </div>

        <h2>A Dining Experience to Remember</h2>

        <p>
            Discover what makes every visit special.
        </p>

    </div>


    <div class="special-grid">

        <div class="special-card">

            <div class="icon">🍽️</div>

            <h3>Fresh Ingredients</h3>

            <p>
                Carefully selected ingredients are used
                to create fresh and flavorful dishes.
            </p>

        </div>


        <div class="special-card">

            <div class="icon">👨‍🍳</div>

            <h3>Passionate Chefs</h3>

            <p>
                Our chefs put creativity and care into
                every plate that leaves the kitchen.
            </p>

        </div>


        <div class="special-card">

            <div class="icon">✨</div>

            <h3>Warm Atmosphere</h3>

            <p>
                Enjoy your meal in a cozy environment
                designed for meaningful moments.
            </p>

        </div>

    </div>

</section>


<!-- =========================
     EXPERIENCE
========================= -->

<section class="experience">

    <div class="section-heading">

        <div class="label">
            SAVORIA EXPERIENCE
        </div>

        <h2>Good Food. Good People.</h2>

        <p>
            We create memorable experiences beyond the plate.
        </p>

    </div>


    <div class="experience-grid">

        <div class="experience-card">

            <div class="number">
                01
            </div>

            <h3>Gather</h3>

            <p>
                Bring your favorite people together around
                a table filled with delicious food.
            </p>

        </div>


        <div class="experience-card">

            <div class="number">
                02
            </div>

            <h3>Enjoy</h3>

            <p>
                Take your time, enjoy every bite,
                and appreciate the moment.
            </p>

        </div>


        <div class="experience-card">

            <div class="number">
                03
            </div>

            <h3>Remember</h3>

            <p>
                Leave with great memories and
                a reason to come back again.
            </p>

        </div>

    </div>

</section>


<!-- =========================
     RESERVATION
========================= -->

<section id="reservation" class="reservation">

    <h2>Reserve Your Table</h2>

    <p>
        Planning a dinner, celebration, or simple night out?
        Make Savoria part of your next special moment.
    </p>

    <a href="#contact" class="btn">
        Contact Us
    </a>


    <div class="reservation-box">

        <div>
            <strong>MONDAY - FRIDAY</strong>
            11:00 AM - 10:00 PM
        </div>

        <div>
            <strong>SATURDAY</strong>
            11:00 AM - 11:00 PM
        </div>

        <div>
            <strong>SUNDAY</strong>
            10:00 AM - 9:00 PM
        </div>

    </div>

</section>


<!-- =========================
     CONTACT
========================= -->

<section id="contact" class="contact">

    <div class="section-heading">

        <div class="label">
            FIND US
        </div>

        <h2>Visit Savoria</h2>

        <p>
            We'd love to welcome you to our table.
        </p>

    </div>


    <div class="contact-container">

        <div class="contact-info">

            <h3>Contact Information</h3>

            <p>
                <strong>📍 Address:</strong><br>
                123 Main Street, Your City, Philippines
            </p>

            <p>
                <strong>📞 Phone:</strong><br>
                +63 900 123 4567
            </p>

            <p>
                <strong>📧 Email:</strong><br>
                hello@savoria.com
            </p>

        </div>


        <div class="hours">

            <h3>Opening Hours</h3>

            <p>
                <span>Monday - Friday</span>
                <span>11 AM - 10 PM</span>
            </p>

            <p>
                <span>Saturday</span>
                <span>11 AM - 11 PM</span>
            </p>

            <p>
                <span>Sunday</span>
                <span>10 AM - 9 PM</span>
            </p>

        </div>

    </div>

</section>


<!-- =========================
     FOOTER
========================= -->

<footer>

    <p>
        © 2026 <strong>Savoria Restaurant</strong>
        | Crafted with HTML5 & CSS3
    </p>

</footer>

</body>
</html>
```
