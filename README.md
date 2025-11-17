<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Helen's Greek Kitchen - Authentic Greek Food</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary: #2e9cab;
            --primary-dark: #1f618d;
            --accent: #e74c3c;
            --text: #2c3e50;
            --text-light: #7f8c8d;
            --background: #f8f9fa;
            --white: #ffffff;
            --shadow: 0 5px 15px rgba(0,0,0,0.08);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--background);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Fejléc */
        .header {
            position: relative;
            overflow: hidden;
        }

        .header-banner {
            width: 100%;
            height: 300px;
            object-fit: cover;
        }

        /* Navigáció */
        .navbar {
            background: var(--primary);
            padding: 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .nav-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }

        .nav-link {
            color: var(--white) !important;
            text-decoration: none;
            padding: 18px 25px;
            font-weight: bold;
            font-size: 1.1em;
            transition: var(--transition);
            position: relative;
            cursor: pointer;
        }

        .nav-link:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 3px;
            background: var(--white);
            transition: var(--transition);
            transform: translateX(-50%);
        }

        .nav-link:hover::after {
            width: 80%;
        }

        /* Fő gombok */
        .main-actions {
            text-align: center;
            padding: 60px 0 40px;
            position: relative;
            z-index: 100;
        }

        .action-button {
            display: inline-flex;
            align-items: center;
            background: var(--primary);
            color: var(--white) !important;
            padding: 20px 40px;
            margin: 15px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.3em;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 2px solid transparent;
            cursor: pointer;
        }

        .action-button:hover {
            background: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        /* Kategória választó */
        .category-selector {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255,255,255,0.98);
            z-index: 2000;
            padding: 80px 20px 50px;
            overflow-y: auto;
        }

        .category-selector.active {
            display: block;
        }

        .category-title {
            text-align: center;
            color: var(--primary);
            font-size: 2.5em;
            margin-bottom: 40px;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .category-card {
            background: var(--white);
            padding: 35px 25px;
            border-radius: 15px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            cursor: pointer;
            border: 2px solid transparent;
        }

        .category-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 30px rgba(0,0,0,0.12);
            border-color: var(--primary);
        }

        .category-card h3 {
            color: var(--primary);
            font-size: 1.4em;
            margin-bottom: 15px;
        }

        .category-card p {
            color: var(--text-light);
            font-size: 1em;
        }

        /* Menü overlay-ek */
        .menu-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(255,255,255,0.98);
            z-index: 2000;
            padding: 80px 20px 50px;
            overflow-y: auto;
        }

        .menu-overlay.active {
            display: block;
        }

        .close-overlay {
            position: fixed;
            top: 25px;
            right: 35px;
            font-size: 2.8em;
            color: var(--primary);
            cursor: pointer;
            transition: var(--transition);
            z-index: 2001;
        }

        .close-overlay:hover {
            color: var(--accent);
            transform: scale(1.2);
        }

        .menu-header {
            text-align: center;
            margin-bottom: 40px;
            padding-bottom: 20px;
            border-bottom: 3px solid var(--primary);
        }

        .menu-header h2 {
            color: var(--primary);
            font-size: 2.2em;
            margin-bottom: 15px;
        }

        .menu-header p {
            color: var(--text-light);
            font-size: 1.1em;
            max-width: 800px;
            margin: 0 auto 30px;
        }

        .menu-items {
            max-width: 900px;
            margin: 0 auto;
        }

        .menu-item {
            background: var(--white);
            margin-bottom: 25px;
            padding: 25px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .menu-item:hover {
            transform: translateX(5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .menu-item h3 {
            color: var(--primary);
            font-size: 1.5em;
            margin-bottom: 12px;
        }

        .menu-item p {
            color: var(--text-light);
            font-size: 1.05em;
            line-height: 1.5;
        }

        /* Lábléc */
        .footer {
            background: var(--primary-dark);
            color: var(--white);
            text-align: center;
            padding: 35px 20px;
            margin-top: 60px;
        }

        /* Reszponzív design */
        @media (max-width: 768px) {
            .nav-link {
                padding: 15px 20px;
                font-size: 1em;
            }

            .action-button {
                padding: 18px 35px;
                font-size: 1.2em;
                position: relative;
                z-index: 100;
            }

            .category-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .category-card {
                padding: 25px 20px;
            }

            .menu-header h2 {
                font-size: 1.8em;
            }
        }

        @media (max-width: 480px) {
            .nav-container {
                flex-direction: column;
            }

            .nav-link {
                width: 100%;
                text-align: center;
            }

            .main-actions {
                padding: 40px 0 30px;
            }

            .action-button {
                display: block;
                margin: 10px auto;
                max-width: 280px;
            }

            .category-title {
                font-size: 2em;
            }

            .container {
                padding: 0 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Fejléc -->
    <header class="header">
        <img src="header2.png" alt="Helen's Greek Kitchen" class="header-banner">
    </header>

    <!-- Navigáció -->
    <nav class="navbar">
        <div class="container">
            <div class="nav-container">
                <a class="nav-link" data-target="about">About</a>
                <a class="nav-link" data-target="allergens">Allergens</a>
                <a class="nav-link" data-target="contact">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Fő gombok -->
    <section class="main-actions">
        <div class="container">
            <a class="action-button" id="showMenu">
                <i class="fas fa-book" style="margin-right:12px;"></i>View Full Menu
            </a>
            <a href="https://goodeats.io/helensgreek" class="action-button" target="_blank">
                <i class="fas fa-shopping-cart" style="margin-right:12px;"></i>Order Now
            </a>
        </div>
    </section>

    <!-- Kategória választó -->
    <div id="categorySelector" class="category-selector">
        <span class="close-overlay" data-close="categorySelector">&times;</span>
        <h2 class="category-title">Our Menu Categories</h2>
        <div class="category-grid">
            <div class="category-card" data-category="starters">
                <h3>Starters for the Gods</h3>
                <p>Divine appetizers to begin your feast</p>
            </div>
            <div class="category-card" data-category="wraps">
                <h3>Wraps for the Gods</h3>
                <p>Heavenly pita wraps filled with flavor</p>
            </div>
            <div class="category-card" data-category="platters">
                <h3>Greek Me Baby One More Time</h3>
                <p>Platters fit for Olympus</p>
            </div>
            <div class="category-card" data-category="quests">
                <h3>The Greek Quests</h3>
                <p>Traditional Greek main courses</p>
            </div>
            <div class="category-card" data-category="sweets">
                <h3>Sweet Treats</h3>
                <p>Desserts worthy of the gods</p>
            </div>
        </div>
    </div>

    <!-- STARTERS MENÜ -->
    <div id="startersMenu" class="menu-overlay">
        <span class="close-overlay" data-close="startersMenu">&times;</span>
        <div class="menu-header">
            <h2>Starters for the Gods</h2>
            <p>Before the main feast, the gods liked to snack too. Sharing is optional. Greed is divine.</p>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Allitis Pitta</h3>
                <p>A homemade Classic from our own Greek Legend Helen. Beef Mince Meat on a pitta bread, served with a little salad and Authentic Greek Yogurt.</p>
            </div>
            <div class="menu-item">
                <h3>Feta Pastry with Honey</h3>
                <p>Crispy, Salty, Sweet and scandalously addictive. Proof the Gods liked a dessert before dinner. PDO Feta cheese wrapped in filo pastry and drizzled with honey and sesame.</p>
            </div>
            <div class="menu-item">
                <h3>Kolokithokeftedes</h3>
                <p>Crispy Courgettes fritters bursting with herb and Feta – Zeus himself declared them "dangerously moreish".</p>
            </div>
            <div class="menu-item">
                <h3>Greek Salad</h3>
                <p>Fresh, Crunchy and very Athenian-approved. Even Plato would pause his philosophy for this. Authentic Greek Salad, fresh tomatoes, cucumber, bell pepper, onions, olives, extra virgin olive-oil and oregano.</p>
            </div>
            <div class="menu-item">
                <h3>Dolmades</h3>
                <p>Tender vine leaves, stuffed with rice and herbs, basically Greek Sushi but with more Salt. Served with a fresh lemon sauce.</p>
            </div>
            <div class="menu-item">
                <h3>Talagani Cheese</h3>
                <p>Grilled to golden perfection, crispy outside heavenly inside. Even Apollo could not resist this melody of flavour.</p>
            </div>
            <div class="menu-item">
                <h3>Tzatziki</h3>
                <p>Cool Authentic Greek Yogurt, cucumber & garlic – Combo of destiny. The shield that protects all gyros.</p>
            </div>
            <div class="menu-item">
                <h3>Aubergine Dip</h3>
                <p>Smokey, silky and deeply mysterious. If the Oracle of Delphi made Sushi, this would be it!</p>
            </div>
            <div class="menu-item">
                <h3>Houmous</h3>
                <p>Smooth, Garlicky and made with love (and Chickpeas.) The dip of diplomacy – unites all tables. Served with Extra Virgin Olive Oil and paprika.</p>
            </div>
            <div class="menu-item">
                <h3>Olives</h3>
                <p>Simple. Classic. Eternal. Athena's proudest invention. Respect the Olive!</p>
            </div>
        </div>
    </div>

    <!-- WRAPS MENÜ -->
    <div id="wrapsMenu" class="menu-overlay">
        <span class="close-overlay" data-close="wrapsMenu">&times;</span>
        <div class="menu-header">
            <h2>Wraps for the Gods</h2>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Pork Gyros</h3>
                <p>Juicy, smoky, and 100% approved by the intellectual Athenians. Yes, Socrates would've ordered two. Served with fries, tomatoes, onions, and Tzatziki.</p>
            </div>
            <div class="menu-item">
                <h3>Chicken Gyros</h3>
                <p>Tastes like a Greek summer, desired by ancient Spartan warriors. Served with fries, tomatoes, onions, and Tzatziki.</p>
            </div>
            <div class="menu-item">
                <h3>Pork Souvlaki</h3>
                <p>Tender pork, kissed by fire and Greek spices, wrapped in fluffy pita glory. Served with fries, salad, and divine sauce.</p>
            </div>
            <div class="menu-item">
                <h3>Chicken Souvlaki</h3>
                <p>Succulent chicken, marinated like a Spartan's secret weapon, grilled to perfection. Wrapped with salad, fries, and legendary sauce.</p>
            </div>
            <div class="menu-item">
                <h3>Kebab Souvlaki</h3>
                <p>All the juicy, grilled goodness of our kebab, wrapped tighter than Athena's helmet. Sweet red peppers and ambrosia-inspired sauce.</p>
            </div>
            <div class="menu-item">
                <h3>Greek Sausage</h3>
                <p>Bold, flavorful, and full of street-smart swagger straight from the Greek agora. Herbs so good, even Dionysus would raise his goblet in approval.</p>
            </div>
            <div class="menu-item">
                <h3>Talagani Wrap</h3>
                <p>Grilled Talagani, peppers, and a drizzle of zesty lemon sauce. Mount Olympus-worthy delight.</p>
            </div>
        </div>
    </div>

    <!-- PLATTERS MENÜ -->
    <div id="plattersMenu" class="menu-overlay">
        <span class="close-overlay" data-close="plattersMenu">&times;</span>
        <div class="menu-header">
            <h2>Greek Me Baby One More Time</h2>
            <p>Because you always come back for more. Don't deny it.</p>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Pork Kalamakia</h3>
                <p>Tender pork skewers, grilled to perfection and kissed by the flames of Mount Olympus. Even Poseidon would put down his trident for these. Includes 3 juicy pork skewers, served with chips and salad.</p>
            </div>
            <div class="menu-item">
                <h3>Chicken Kalamakia</h3>
                <p>Succulent chicken skewers, marinated and flame-grilled until golden. So good, even Poseidon would put down his trident for a bite. Includes 3 chicken skewers, served with chips and salad.</p>
            </div>
            <div class="menu-item">
                <h3>Kebab Portion</h3>
                <p>Succulent, juicy, and grilled with the fire of Hephaestus himself. One bite and you'll be chanting Opa! 3 juicy kebabs served with fries and salad.</p>
            </div>
            <div class="menu-item">
                <h3>Mixed Gyros</h3>
                <p>The ultimate gyro adventure: a little chicken, a little pork, a lot of deliciousness. Like a Greek tragedy, but everyone lives happily ever after. Served with fries, pittas, bread, and salad.</p>
            </div>
            <div class="menu-item">
                <h3>Sausage Platter</h3>
                <p>A heroic lineup of sausages, grilled to perfection. Even Zeus would trade lightning bolts for a bite. Served with fries and salad.</p>
            </div>
            <div class="menu-item">
                <h3>Vegetarian Platter</h3>
                <p>A garden party straight from Mount Olympus. Veggies so good, you'll think Dionysus himself grew them. Talagani, and peppers served with fries and salad.</p>
            </div>
            <div class="menu-item">
                <h3>Mixed Grill Platter</h3>
                <p>A little bit of everything for the indecisive Greek legend. It's like a symposium, but tastier – feeds 2-3 fully grown Greeks.</p>
            </div>
        </div>
    </div>

    <!-- QUESTS MENÜ -->
    <div id="questsMenu" class="menu-overlay">
        <span class="close-overlay" data-close="questsMenu">&times;</span>
        <div class="menu-header">
            <h2>The Greek Quests</h2>
            <p>Not all heroes wear togas. Some just order well.</p>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Bifteki</h3>
                <p>Juicy Greek-style beef patties filled with herbs and maybe a secret or two from Mount Parnassus. A dish worthy of a Spartan warrior after battle. Potatoes accompany.</p>
            </div>
            <div class="menu-item">
                <h3>Briam</h3>
                <p>A vibrant medley of baked vegetables, olive oil, and herbs – the garden of the gods on a plate. Hera herself would claim it as her secret to immortality. Served with fries.</p>
            </div>
            <div class="menu-item">
                <h3>Gemista</h3>
                <p>Peppers and tomatoes stuffed with herby rice and good vibes only. So fresh and wholesome, Aphrodite herself might've packed it for a beach picnic.</p>
            </div>
            <div class="menu-item">
                <h3>Giouvesti</h3>
                <p>Tender chicken baked with orzo, tomato, and a hint of cinnamon. One bite, and you'll feel like you're feasting on Mount Olympus. Comes with fries.</p>
            </div>
            <div class="menu-item">
                <h3>Kleftiko</h3>
                <p>Lamb so tender it practically sings of Greek islands and olive groves. The secret recipes of Cretan rebels live in every mouthful. Served with roast potatoes.</p>
            </div>
            <div class="menu-item">
                <h3>Lemon Chicken</h3>
                <p>Tender chicken baked in zesty lemon sauce that could wake Zeus from a nap. Bright, bold, and just the right amount of cheeky – like a Greek holiday fling.</p>
            </div>
            <div class="menu-item">
                <h3>Mousakas</h3>
                <p>Layers of aubergine, spiced mince, and creamy béchamel baked golden. Like a warm Greek sunset on your plate – Demeter would approve.</p>
            </div>
            <div class="menu-item">
                <h3>Paboutskia</h3>
                <p>Stuffed aubergines overflowing with spiced mince and sunshine. It's basically the Greek version of comfort food... if comfort wore a toga.</p>
            </div>
            <div class="menu-item">
                <h3>Pastitsio</h3>
                <p>Pasta, spiced mince, and luscious béchamel in perfect harmony. Even Dionysus would pause the wine for this masterpiece. Even Hercules wouldn't say no.</p>
            </div>
            <div class="menu-item">
                <h3>Plaki Fish</h3>
                <p>Oven-baked fish with tomatoes, onions, olives, and herbs that sing of the Aegean breeze. Poseidon's favorite – fresh from the sea, fit for a god.</p>
            </div>
            <div class="menu-item">
                <h3>Red Chicken</h3>
                <p>Tender chicken simmered in a rich tomato sauce kissed by the sun. A dish so comforting, Apollo might trade his lyre for a bite. Fries on the side.</p>
            </div>
            <div class="menu-item">
                <h3>Stifado</h3>
                <p>Slow-cooked beef with sweet onions and romantic spices, simmered to perfection. A dish worthy of a Spartan warrior after battle. Fries accompany.</p>
            </div>
        </div>
    </div>

    <!-- SWEETS MENÜ -->
    <div id="sweetsMenu" class="menu-overlay">
        <span class="close-overlay" data-close="sweetsMenu">&times;</span>
        <div class="menu-header">
            <h2>Sweet Treats</h2>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Baklavas</h3>
                <p>Flaky, nutty, sticky perfection. Athena would swap her owl for a piece.</p>
            </div>
            <div class="menu-item">
                <h3>Chocolate Cake</h3>
                <p>Decadent, rich, and dangerously delicious. Even Hades would sneak a slice.</p>
            </div>
            <div class="menu-item">
                <h3>Orange Cake</h3>
                <p>Zesty, sweet and sun-kissed. Helios himself might approve.</p>
            </div>
            <div class="menu-item">
                <h3>Ravani</h3>
                <p>Greek semolina cake drenched in syrup. A sweet hug from the Mediterranean.</p>
            </div>
        </div>
    </div>

    <!-- ABOUT MENÜ -->
    <div id="aboutMenu" class="menu-overlay">
        <span class="close-overlay" data-close="aboutMenu">&times;</span>
        <div class="menu-header">
            <h2>About Helen's Greek Kitchen</h2>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Our Story</h3>
                <p>Helen's Greek Kitchen brings authentic Greek flavors to your table, crafted with love and traditional recipes passed down through generations.</p>
            </div>
        </div>
    </div>

    <!-- ALLERGENS MENÜ -->
    <div id="allergensMenu" class="menu-overlay">
        <span class="close-overlay" data-close="allergensMenu">&times;</span>
        <div class="menu-header">
            <h2>Allergen Information</h2>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Common Allergens</h3>
                <p>Our dishes may contain common allergens including dairy, gluten, nuts, and shellfish. Please inform our staff about any allergies before ordering.</p>
            </div>
        </div>
    </div>

    <!-- CONTACT MENÜ -->
    <div id="contactMenu" class="menu-overlay">
        <span class="close-overlay" data-close="contactMenu">&times;</span>
        <div class="menu-header">
            <h2>Contact Us</h2>
        </div>
        <div class="menu-items">
            <div class="menu-item">
                <h3>Location</h3>
                <p>The Three Cups Pub<br>123 Main Street<br>Your City</p>
            </div>
            <div class="menu-item">
                <h3>Opening Hours</h3>
                <p>Monday-Saturday: 11am-10pm<br>Sunday: 12pm-9pm</p>
            </div>
            <div class="menu-item">
                <h3>Phone</h3>
                <p>+1 234 567 890</p>
            </div>
        </div>
    </div>

    <!-- Lábléc -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2025 Helen's Greek Kitchen | The Three Cups Pub</p>
        </div>
    </footer>

    <script>
        // Kategória választó megjelenítése
        document.getElementById('showMenu').addEventListener('click', function(e) {
            e.preventDefault();
            document.getElementById('categorySelector').classList.add('active');
        });

        // Overlay bezárása
        document.querySelectorAll('.close-overlay').forEach(btn => {
            btn.addEventListener('click', function() {
                const target = this.getAttribute('data-close');
                document.getElementById(target).classList.remove('active');
            });
        });

        // Kategória kiválasztása
        document.querySelectorAll('.category-card').forEach(card => {
            card.addEventListener('click', function() {
                const category = this.getAttribute('data-category');
                document.getElementById('categorySelector').classList.remove('active');
                document.getElementById(category + 'Menu').classList.add('active');
            });
        });

        // Kattintás overlay-en kívülre
        document.querySelectorAll('.category-selector, .menu-overlay').forEach(overlay => {
            overlay.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.remove('active');
                }
            });
        });

        // Navigációs linkek
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const target = this.getAttribute('data-target');
                document.getElementById(target + 'Menu').classList.add('active');
            });
        });

        // ESC billentyű overlay bezárásához
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                document.querySelectorAll('.category-selector.active, .menu-overlay.active').forEach(overlay => {
                    overlay.classList.remove('active');
                });
            }
        });
    </script>
</body>
</html>
