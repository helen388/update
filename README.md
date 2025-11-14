<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Helen's Greek Kitchen</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-color: #2e9cab;
            --secondary-color: #1f618d;
            --accent-color: #e74c3c;
            --text-dark: #2c3e50;
            --text-light: #7f8c8d;
            --background: #f8f9fa;
            --background-light: #ffffff;
            --shadow: 0 5px 15px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Trebuchet MS', sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            background-color: var(--background);
            overflow-x: hidden;
        }

        header img {
            width: 100%;
            height: auto;
            max-height: 400px;
            object-fit: cover;
        }

        /* Navigáció */
        nav {
            display: flex;
            justify-content: center;
            background-color: var(--primary-color);
            flex-wrap: wrap;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
        }

        nav a {
            text-decoration: none;
            color: white !important;
            padding: 15px 20px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1em;
            transition: var(--transition);
            position: relative;
        }

        nav a:hover {
            background-color: var(--secondary-color);
            transform: scale(1.05);
            color: white !important;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 3px;
            background: white;
            transition: var(--transition);
            transform: translateX(-50%);
        }

        nav a:hover::after {
            width: 80%;
        }

        section {
            max-width: 1000px;
            margin: 20px auto;
            padding: 0 20px;
        }

        h2 {
            color: var(--primary-color);
            margin-top: 30px;
            border-bottom: 2px solid var(--primary-color);
            padding-bottom: 10px;
            text-align: center;
            font-size: 2rem;
        }

        .menu-item {
            margin-bottom: 20px;
            padding: 20px;
            border-left: 5px solid var(--primary-color);
            background-color: var(--background-light);
            border-radius: 8px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        .menu-item h3 {
            margin: 0 0 10px 0;
            font-size: 1.5em;
            color: var(--primary-color);
        }

        .menu-item p {
            margin: 0;
            color: var(--text-light);
            font-size: 1.1em;
        }

        .order-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background-color: var(--primary-color);
            color: white !important;
            padding: 18px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.4em;
            box-shadow: var(--shadow);
            transition: var(--transition);
            margin: 20px;
            border: 2px solid transparent;
        }

        .order-button:hover {
            background-color: var(--secondary-color);
            transform: scale(1.08);
            box-shadow: 0 8px 20px rgba(0,0,0,0.25);
        }

        footer {
            text-align: center;
            padding: 30px;
            background-color: var(--secondary-color);
            color: white;
            margin-top: 50px;
        }

        /* Hero szekció */
        .hero {
            position: relative;
            overflow: hidden;
            text-align: center;
        }

        .hero-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.7);
            width: 90%;
            max-width: 800px;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
        }

        /* Overlay stílusok */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.98);
            overflow-y: auto;
            display: none;
            z-index: 2000;
            padding: 50px 20px;
            text-align: center;
        }

        .close-btn {
            position: fixed;
            top: 20px;
            right: 30px;
            font-size: 2.5em;
            cursor: pointer;
            color: var(--primary-color);
            transition: var(--transition);
            z-index: 2001;
        }

        .close-btn:hover {
            color: var(--accent-color);
            transform: scale(1.2);
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            max-width: 1000px;
            margin: 50px auto;
        }

        .category-btn {
            background: var(--primary-color);
            color: white;
            padding: 25px 20px;
            border-radius: 15px;
            text-align: center;
            font-size: 1.4em;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

        .category-btn:hover {
            background: var(--secondary-color);
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }

        /* Animációk */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in {
            animation: fadeIn 0.6s ease forwards;
        }

        /* Reszponzív design */
        @media (max-width: 768px) {
            nav a { 
                padding: 12px 15px; 
                font-size: 0.9em; 
            }
            
            header img { 
                max-height: 300px; 
            }
            
            .order-button { 
                font-size: 1.2em; 
                padding: 15px 25px; 
                margin: 10px;
            }
            
            .category-btn { 
                font-size: 1.1em; 
                padding: 20px 15px; 
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            h2 {
                font-size: 1.8rem;
            }
        }

        @media (max-width: 480px) {
            nav {
                flex-direction: column;
                align-items: center;
            }
            
            nav a {
                width: 100%;
                text-align: center;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .category-grid {
                grid-template-columns: 1fr;
            }
            
            section {
                padding: 0 15px;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="hero">
            <img src="header2.png" alt="Helen's Greek Kitchen Banner">
            <div class="hero-content">
                <h1>Helen's Greek Kitchen</h1>
                <p>Authentic Greek Flavors at The Three Cups Pub</p>
            </div>
        </div>
    </header>

    <nav>
        <a data-overlay="aboutOverlay">About</a>
        <a data-overlay="allergensOverlay">Allergens</a>
        <a data-overlay="contactOverlay">Contact</a>
    </nav>

    <section id="home-buttons" style="text-align:center; margin-top:50px;">
        <a id="menuBtnHome" class="order-button" data-overlay="categoryOverlay">
            <i class="fas fa-utensils" style="margin-right:10px;"></i>View Menu
        </a>
        <a href="https://goodeats.io/helensgreek" class="order-button" target="_blank">
            <i class="fas fa-shopping-cart" style="margin-right:10px;"></i>Order Now
        </a>
    </section>

    <!-- CATEGORY SELECTOR OVERLAY -->
    <div id="categoryOverlay" class="overlay">
        <span class="close-btn" data-close="categoryOverlay">&times;</span>
        <h2>Select a Category</h2>
        <div class="category-grid">
            <div class="category-btn" data-overlay="startersOverlay">Starters for the Gods</div>
            <div class="category-btn" data-overlay="wrapsOverlay">Wraps for the Gods</div>
        </div>
    </div>

    <!-- STARTERS OVERLAY -->
    <div id="startersOverlay" class="overlay">
        <span class="close-btn" data-close="startersOverlay">&times;</span>
        <h2>Starters for the Gods</h2>
        <p>Before the main feast, the gods liked to snack too. Sharing is optional. Greed is divine.</p>
        <div class="menu-item fade-in"><h3>Allitis Pitta</h3><p>A homemade Classic from our own Greek Legend Helen. Beef Mince Meat on a pitta bread, served with a little salad and Authentic Greek Yogurt.</p></div>
        <div class="menu-item fade-in"><h3>Feta Pastry with Honey</h3><p>Crispy, Salty, Sweet and scandalously addictive. PDO Feta cheese wrapped in filo pastry and drizzled with honey and sesame.</p></div>
        <div class="menu-item fade-in"><h3>Kolokithokeftedes</h3><p>Crispy Courgettes fritters bursting with herb and Feta – Zeus himself declared them "dangerously moreish".</p></div>
        <div class="menu-item fade-in"><h3>Greek Salad</h3><p>Fresh, Crunchy and very Athenian-approved. Authentic Greek Salad, fresh tomatoes, cucumber, bell pepper, onions, olives, extra virgin olive-oil and oregano.</p></div>
        <div class="menu-item fade-in"><h3>Dolmades</h3><p>Tender vine leaves, stuffed with rice and herbs, basically Greek Sushi but with more Salt. Served with a fresh lemon sauce.</p></div>
        <div class="menu-item fade-in"><h3>Talagani Cheese</h3><p>Grilled to golden perfection, crispy outside heavenly inside. Even Apollo could not resist this melody of flavour.</p></div>
        <div class="menu-item fade-in"><h3>Tzatziki</h3><p>Cool Authentic Greek Yogurt, cucumber & garlic – Combo of destiny. The shield that protects all gyros.</p></div>
        <div class="menu-item fade-in"><h3>Aubergine Dip</h3><p>Smokey, silky and deeply mysterious. If the Oracle of Delphi made Sushi, this would be it!</p></div>
        <div class="menu-item fade-in"><h3>Houmous</h3><p>Smooth, Garlicky and made with love (and Chickpeas.) The dip of diplomacy – unites all tables. Served with Extra Virgin Olive Oil and paprika.</p></div>
        <div class="menu-item fade-in"><h3>Olives</h3><p>Simple. Classic. Eternal. Athena’s proudest invention. Respect the Olive!</p></div>
    </div>

    <!-- WRAPS OVERLAY -->
    <div id="wrapsOverlay" class="overlay">
        <span class="close-btn" data-close="wrapsOverlay">&times;</span>
        <h2>Wraps for the Gods (Pita Gyros)</h2>
        <div class="menu-item fade-in"><h3>Pork Gyros</h3><p>Juicy, smoky, and 100% approved by the intellectual Athenians. Yes, Socrates would've ordered two. Served with fries, tomatoes, onions, and Tzatziki.</p></div>
        <div class="menu-item fade-in"><h3>Chicken Gyros</h3><p>Tastes like a Greek summer, desired by ancient Spartan warriors. Served with fries, tomatoes, onions, and Tzatziki.</p></div>
        <div class="menu-item fade-in"><h3>Pork Souvlaki</h3><p>Tender pork, kissed by fire and Greek spices, wrapped in fluffy pita glory. Served with fries, salad, and divine sauce.</p></div>
        <div class="menu-item fade-in"><h3>Chicken Souvlaki</h3><p>Succulent chicken, marinated like a Spartan's secret weapon, grilled to perfection. Wrapped with salad, fries, and legendary sauce.</p></div>
        <div class="menu-item fade-in"><h3>Kebab Souvlaki</h3><p>All the juicy, grilled goodness of our kebab, wrapped tighter than Athena’s helmet. Sweet red peppers and ambrosia-inspired sauce.</p></div>
        <div class="menu-item fade-in"><h3>Greek Sausage</h3><p>Bold, flavorful, and full of street-smart swagger straight from the Greek agora. Herbs so good, even Dionysus would raise his goblet in approval.</p></div>
        <div class="menu-item fade-in"><h3>Talagani Wrap</h3><p>Grilled Talagani, peppers, and a drizzle of zesty lemon sauce. Mount Olympus-worthy delight.</p></div>
    </div>

    <!-- PLATTERS OVERLAY -->
    <div id="plattersOverlay" class="overlay">
        <span class="close-btn" data-close="plattersOverlay">&times;</span>
        <h2>Greek Me Baby One More Time (Platters)</h2>
        <div class="menu-item fade-in"><h3>Pork Kalamakia</h3><p>Tender pork skewers, grilled to perfection and kissed by the flames of Mount Olympus. Served with chips and salad.</p></div>
        <div class="menu-item fade-in"><h3>Chicken Kalamakia</h3><p>Succulent chicken skewers, marinated and flame-grilled until golden. Served with chips and salad.</p></div>
        <div class="menu-item fade-in"><h3>Kebab Portion</h3><p>Succulent, juicy, grilled with the fire of Hephaestus. One bite and you'll chant Opa! Served with fries and salad.</p></div>
        <div class="menu-item fade-in"><h3>Mixed Gyros</h3><p>A little chicken, a little pork, a lot of deliciousness. Served with fries, pittas, bread, and salad.</p></div>
        <div class="menu-item fade-in"><h3>Sausage Platter</h3><p>Grilled sausages, served with fries and salad.</p></div>
        <div class="menu-item fade-in"><h3>Vegetarian Platter</h3><p>Talagani, and peppers served with fries and salad.</p></div>
        <div class="menu-item fade-in"><h3>Mixed Grill Platter</h3><p>A little bit of everything. Feeds 2-3 people.</p></div>
    </div>

    <!-- QUESTS OVERLAY -->
    <div id="questsOverlay" class="overlay">
        <span class="close-btn" data-close="questsOverlay">&times;</span>
        <h2>The Greek Quests</h2>
        <div class="menu-item fade-in"><h3>Bifteki</h3><p>Juicy Greek-style beef patties filled with herbs. Served with potatoes.</p></div>
        <div class="menu-item fade-in"><h3>Briam</h3><p>Baked vegetables, olive oil, and herbs. Served with fries.</p></div>
        <div class="menu-item fade-in"><h3>Gemista</h3><p>Peppers and tomatoes stuffed with herby rice.</p></div>
        <div class="menu-item fade-in"><h3>Giouvesti</h3><p>Tender chicken baked with orzo, tomato, and a hint of cinnamon. Comes with fries.</p></div>
        <div class="menu-item fade-in"><h3>Kleftiko</h3><p>Lamb so tender it practically sings of Greek islands. Served with roast potatoes.</p></div>
        <div class="menu-item fade-in"><h3>Lemon Chicken</h3><p>Tender chicken baked in zesty lemon sauce.</p></div>
        <div class="menu-item fade-in"><h3>Mousakas</h3><p>Layers of aubergine, spiced mince, and creamy béchamel baked golden.</p></div>
        <div class="menu-item fade-in"><h3>Paboutskia</h3><p>Stuffed aubergines overflowing with spiced mince.</p></div>
        <div class="menu-item fade-in"><h3>Pastitsio</h3><p>Pasta, spiced mince, and luscious béchamel.</p></div>
        <div class="menu-item fade-in"><h3>Plaki Fish</h3><p>Oven-baked fish with tomatoes, onions, olives, and herbs.</p></div>
        <div class="menu-item fade-in"><h3>Red Chicken</h3><p>Tender chicken simmered in a rich tomato sauce. Served with fries.</p></div>
        <div class="menu-item fade-in"><h3>Stifado</h3><p>Slow-cooked beef with sweet onions and spices. Served with fries.</p></div>
    </div>

    <!-- SWEET OVERLAY -->
    <div id="sweetOverlay" class="overlay">
        <span class="close-btn" data-close="sweetOverlay">&times;</span>
        <h2>Sweet Treats</h2>
        <div class="menu-item fade-in"><h3>Baklavas</h3><p>Flaky, nutty, sticky perfection. Athena would swap her owl for a piece.</p></div>
        <div class="menu-item fade-in"><h3>Chocolate Cake</h3><p>Decadent, rich, and dangerously delicious. Even Hades would sneak a slice.</p></div>
        <div class="menu-item fade-in"><h3>Orange Cake</h3><p>Zesty, sweet and sun-kissed. Helios himself might approve.</p></div>
        <div class="menu-item fade-in"><h3>Ravani</h3><p>Greek semolina cake drenched in syrup. A sweet hug from the Mediterranean.</p></div>
    </div>

    <!-- ABOUT OVERLAY -->
    <div id="aboutOverlay" class="overlay">
        <span class="close-btn" data-close="aboutOverlay">&times;</span>
        <h2>About</h2>
        <p>
            Helen's Greek Kitchen – Three Cups Pub<br><br>
            Welcome to Helen's Greek Kitchen at The Three Cups Pub — where the charm of a classic English pub meets the fiery heart of Greek cooking.<br>
            Helen brings her passion straight from the islands — bold flavours, no shortcuts, and a little bit of drama in every dish.<br>
            From moussaka and spanakopita to perfectly grilled souvlaki and creamy tzatziki, every bite tells a story — one that usually ends with "just one more plate."<br><br>
            The Three Cups keeps the drinks flowing — crisp pints, fine wines, and the occasional cheeky ouzo.<br>
            It's the best of both worlds: a British pub with a Greek soul.<br><br>
            <strong>Order from 15:00 to 22:00</strong><br>
            Greek + Mediterranean + Hot food<br>
            Collection + Table orders<br>
            Order from Table QR Code
        </p>
    </div>

    <!-- ALLERGENS OVERLAY -->
    <div id="allergensOverlay" class="overlay">
        <span class="close-btn" data-close="allergensOverlay">&times;</span>
        <h2>Allergens</h2>
        <p>Gluten, Crustaceans, Eggs, Fish, Peanuts, Soybeans, Milk, Nuts, Celery, Mustard, Sesame seeds, Sulphur dioxide and sulphites, Lupin, Molluscs</p>
    </div>

    <!-- CONTACT OVERLAY -->
    <div id="contactOverlay" class="overlay">
        <span class="close-btn" data-close="contactOverlay">&times;</span>
        <h2>Contact</h2>
        <p>Email: helen@helenskitchen.uk</p>
        <p>Three Cups Pub, MK403JR, Bedford 45 Newnham St</p>
    </div>

    <footer>
        <p>© 2025 Helen's Greek Kitchen</p>
    </footer>

    <script>
        const buttons = document.querySelectorAll('[data-overlay]');
        const closeButtons = document.querySelectorAll('.close-btn');

        buttons.forEach(btn => {
            btn.addEventListener('click', () => {
                const overlayId = btn.getAttribute('data-overlay');
                const overlay = document.getElementById(overlayId);
                overlay.style.display = 'block';
                
                // Animáció hozzáadása
                const menuItems = overlay.querySelectorAll('.menu-item');
                menuItems.forEach((item, index) => {
                    item.style.animationDelay = `${index * 0.1}s`;
                });
            });
        });

        closeButtons.forEach(btn => {
            btn.addEventListener('click', () => {
                const overlayId = btn.getAttribute('data-close');
                document.getElementById(overlayId).style.display = 'none';
            });
        });

        // Kattintás overlay-en kívülre
        window.addEventListener('click', (e) => {
            if (e.target.classList.contains('overlay')) {
                e.target.style.display = 'none';
            }
        });

        // Reszponzív navigáció
        window.addEventListener('resize', () => {
            if (window.innerWidth <= 480) {
                document.querySelector('nav').style.flexDirection = 'column';
            } else {
                document.querySelector('nav').style.flexDirection = 'row';
            }
        });

        // Betöltéskor alkalmazza a reszponzív beállításokat
        document.addEventListener('DOMContentLoaded', () => {
            if (window.innerWidth <= 480) {
                document.querySelector('nav').style.flexDirection = 'column';
            }
        });
    </script>

</body>
</html>
