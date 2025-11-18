<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Helen's Greek Kitchen - Photo Gallery</title>
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

        /* Header */
        .header {
            position: relative;
            overflow: hidden;
        }

        .header-banner {
            width: 100%;
            height: 300px;
            object-fit: cover;
        }

        /* Navigation */
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

        /* Main buttons */
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

        /* Category selector */
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

        /* Menu overlays */
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
            cursor: pointer;
            position: relative;
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

        /* Photo gallery overlay */
        .gallery-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 3000;
            padding: 80px 20px 50px;
            overflow-y: auto;
        }

        .gallery-overlay.active {
            display: block;
        }

        .gallery-container {
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
        }

        .gallery-image {
            max-width: 100%;
            max-height: 70vh;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            margin-bottom: 20px;
        }

        .gallery-title {
            color: var(--white);
            font-size: 2.2em;
            margin-bottom: 15px;
        }

        .gallery-description {
            color: var(--text-light);
            font-size: 1.1em;
            max-width: 800px;
            margin: 0 auto 30px;
        }

        .gallery-nav {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .gallery-nav-btn {
            background: var(--primary);
            color: var(--white);
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
        }

        .gallery-nav-btn:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
        }

        /* Footer */
        .footer {
            background: var(--primary-dark);
            color: var(--white);
            text-align: center;
            padding: 35px 20px;
            margin-top: 60px;
        }

        /* Responsive design */
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
    <!-- Header -->
    <header class="header">
        <img src="header2.png" alt="Helen's Greek Kitchen" class="header-banner">
    </header>

    <!-- Navigation -->
    <nav class="navbar">
        <div class="container">
            <div class="nav-container">
                <a class="nav-link" data-target="about">About</a>
                <a class="nav-link" data-target="allergens">Allergens</a>
                <a class="nav-link" data-target="contact">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Main buttons -->
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

    <!-- Category selector -->
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

    <!-- STARTERS MENU -->
    <div id="startersMenu" class="menu-overlay">
        <span class="close-overlay" data-close="startersMenu">&times;</span>
        <div class="menu-header">
            <h2>Starters for the Gods</h2>
            <p>Before the main feast, the gods liked to snack too. Sharing is optional. Greed is divine.</p>
        </div>
        <div class="menu-items">
            <div class="menu-item" data-item="Allitis Pitta">
                <h3>Allitis Pitta</h3>
                <p>A homemade Classic from our own Greek Legend Helen. Beef Mince Meat on a pitta bread, served with a little salad and Authentic Greek Yogurt.</p>
            </div>
            <div class="menu-item" data-item="Feta Pastry with Honey">
                <h3>Feta Pastry with Honey</h3>
                <p>Crispy, Salty, Sweet and scandalously addictive. Proof the Gods liked a dessert before dinner. PDO Feta cheese wrapped in filo pastry and drizzled with honey and sesame.</p>
            </div>
            <div class="menu-item" data-item="Kolokithokeftedes">
                <h3>Kolokithokeftedes</h3>
                <p>Crispy Courgettes fritters bursting with herb and Feta – Zeus himself declared them "dangerously moreish".</p>
            </div>
            <div class="menu-item" data-item="Greek Salad">
                <h3>Greek Salad</h3>
                <p>Fresh, Crunchy and very Athenian-approved. Even Plato would pause his philosophy for this. Authentic Greek Salad, fresh tomatoes, cucumber, bell pepper, onions, olives, extra virgin olive-oil and oregano.</p>
            </div>
            <div class="menu-item" data-item="Dolmades">
                <h3>Dolmades</h3>
                <p>Tender vine leaves, stuffed with rice and herbs, basically Greek Sushi but with more Salt. Served with a fresh lemon sauce.</p>
            </div>
            <div class="menu-item" data-item="Talagani Cheese">
                <h3>Talagani Cheese</h3>
                <p>Grilled to golden perfection, crispy outside heavenly inside. Even Apollo could not resist this melody of flavour.</p>
            </div>
            <div class="menu-item" data-item="Tzatziki">
                <h3>Tzatziki</h3>
                <p>Cool Authentic Greek Yogurt, cucumber & garlic – Combo of destiny. The shield that protects all gyros.</p>
            </div>
            <div class="menu-item" data-item="Aubergine Dip">
                <h3>Aubergine Dip</h3>
                <p>Smokey, silky and deeply mysterious. If the Oracle of Delphi made Sushi, this would be it!</p>
            </div>
            <div class="menu-item" data-item="Houmous">
                <h3>Houmous</h3>
                <p>Smooth, Garlicky and made with love (and Chickpeas.) The dip of diplomacy – unites all tables. Served with Extra Virgin Olive Oil and paprika.</p>
            </div>
            <div class="menu-item" data-item="Olives">
                <h3>Olives</h3>
                <p>Simple. Classic. Eternal. Athena's proudest invention. Respect the Olive!</p>
            </div>
        </div>
    </div>

    <!-- WRAPS MENU -->
    <div id="wrapsMenu" class="menu-overlay">
        <span class="close-overlay" data-close="wrapsMenu">&times;</span>
        <div class="menu-header">
            <h2>Wraps for the Gods</h2>
        </div>
        <div class="menu-items">
            <div class="menu-item" data-item="Pork Gyros">
                <h3>Pork Gyros</h3>
                <p>Juicy, smoky, and 100% approved by the intellectual Athenians. Yes, Socrates would've ordered two. Served with fries, tomatoes, onions, and Tzatziki.</p>
            </div>
            <div class="menu-item" data-item="Chicken Gyros">
                <h3>Chicken Gyros</h3>
                <p>Tastes like a Greek summer, desired by ancient Spartan warriors. Served with fries, tomatoes, onions, and Tzatziki.</p>
            </div>
            <div class="menu-item" data-item="Pork Souvlaki">
                <h3>Pork Souvlaki</h3>
                <p>Tender pork, kissed by fire and Greek spices, wrapped in fluffy pita glory. Served with fries, salad, and divine sauce.</p>
            </div>
            <div class="menu-item" data-item="Chicken Souvlaki">
                <h3>Chicken Souvlaki</h3>
                <p>Succulent chicken, marinated like a Spartan's secret weapon, grilled to perfection. Wrapped with salad, fries, and legendary sauce.</p>
            </div>
            <div class="menu-item" data-item="Kebab Souvlaki">
                <h3>Kebab Souvlaki</h3>
                <p>All the juicy, grilled goodness of our kebab, wrapped tighter than Athena's helmet. Sweet red peppers and ambrosia-inspired sauce.</p>
            </div>
            <div class="menu-item" data-item="Greek Sausage">
                <h3>Greek Sausage</h3>
                <p>Bold, flavorful, and full of street-smart swagger straight from the Greek agora. Herbs so good, even Dionysus would raise his goblet in approval.</p>
            </div>
            <div class="menu-item" data-item="Talagani Wrap">
                <h3>Talagani Wrap</h3>
                <p>Grilled Talagani, peppers, and a drizzle of zesty lemon sauce. Mount Olympus-worthy delight.</p>
            </div>
        </div>
    </div>

    <!-- GREEK ME BABY ONE MORE TIME MENU -->
    <div id="plattersMenu" class="menu-overlay">
        <span class="close-overlay" data-close="plattersMenu">&times;</span>
        <div class="menu-header">
            <h2>Greek Me Baby One More Time</h2>
            <p>Platters fit for Olympus - share with your fellow gods or keep it all for yourself</p>
        </div>
        <div class="menu-items">
            <div class="menu-item" data-item="Pork Gyros Platter">
                <h3>Pork Gyros Platter</h3>
                <p>Feast like a true Olympian with our legendary pork gyros served with fries, salad, pita bread, and Tzatziki.</p>
            </div>
            <div class="menu-item" data-item="Chicken Gyros Platter">
                <h3>Chicken Gyros Platter</h3>
                <p>A heroic portion of our famous chicken gyros, accompanied by fries, fresh salad, warm pita, and authentic Tzatziki.</p>
            </div>
            <div class="menu-item" data-item="Mixed Gyros Platter">
                <h3>Mixed Gyros Platter</h3>
                <p>Can't decide? Have it all! Both pork and chicken gyros with all the trimmings.</p>
            </div>
        </div>
    </div>

    <!-- THE GREEK QUESTS MENU -->
    <div id="questsMenu" class="menu-overlay">
        <span class="close-overlay" data-close="questsMenu">&times;</span>
        <div class="menu-header">
            <h2>The Greek Quests</h2>
            <p>Traditional Greek main courses that will take you on a culinary journey</p>
        </div>
        <div class="menu-items">
            <div class="menu-item" data-item="Moussaka">
                <h3>Moussaka</h3>
                <p>Layers of eggplant, minced meat, and creamy béchamel sauce - a Greek classic!</p>
            </div>
            <div class="menu-item" data-item="Pastitsio">
                <h3>Pastitsio</h3>
                <p>Greek baked pasta with minced meat and béchamel sauce.</p>
            </div>
            <div class="menu-item" data-item="Stifado">
                <h3>Stifado</h3>
                <p>Traditional Greek beef stew with pearl onions in rich tomato sauce.</p>
            </div>
        </div>
    </div>

    <!-- SWEET TREATS MENU -->
    <div id="sweetsMenu" class="menu-overlay">
        <span class="close-overlay" data-close="sweetsMenu">&times;</span>
        <div class="menu-header">
            <h2>Sweet Treats</h2>
            <p>Desserts worthy of the gods - because even Olympus needs something sweet!</p>
        </div>
        <div class="menu-items">
            <div class="menu-item" data-item="Baklava">
                <h3>Baklava</h3>
                <p>Layers of crispy filo pastry, nuts and honey syrup.</p>
            </div>
            <div class="menu-item" data-item="Galaktoboureko">
                <h3>Galaktoboureko</h3>
                <p>Creamy custard baked in filo pastry with sweet syrup.</p>
            </div>
            <div class="menu-item" data-item="Loukoumades">
                <h3>Loukoumades</h3>
                <p>Golden honey puffs drizzled with cinnamon and walnuts.</p>
            </div>
        </div>
    </div>

    <!-- Photo gallery overlay -->
    <div id="galleryOverlay" class="gallery-overlay">
        <span class="close-overlay" data-close="galleryOverlay">&times;</span>
        <div class="gallery-container">
            <h2 class="gallery-title" id="galleryTitle">Food Name</h2>
            <img id="galleryImage" class="gallery-image" src="" alt="Food photo">
            <p class="gallery-description" id="galleryDescription">Food description</p>
            <div class="gallery-nav">
                <button class="gallery-nav-btn" id="prevBtn"><i class="fas fa-chevron-left"></i> Previous</button>
                <button class="gallery-nav-btn" id="nextBtn">Next <i class="fas fa-chevron-right"></i></button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2025 Helen's Greek Kitchen | The Three Cups Pub</p>
        </div>
    </footer>

    <script>
        // Global variables for gallery navigation
        let currentFoodItems = [];
        let currentIndex = 0;

        // Category selector display
        document.getElementById('showMenu').addEventListener('click', function(e) {
            e.preventDefault();
            document.getElementById('categorySelector').classList.add('active');
        });

        // Close overlay
        document.querySelectorAll('.close-overlay').forEach(btn => {
            btn.addEventListener('click', function() {
                const target = this.getAttribute('data-close');
                document.getElementById(target).classList.remove('active');
            });
        });

        // Category selection
        document.querySelectorAll('.category-card').forEach(card => {
            card.addEventListener('click', function() {
                const category = this.getAttribute('data-category');
                document.getElementById('categorySelector').classList.remove('active');
                document.getElementById(category + 'Menu').classList.add('active');
            });
        });

        // Click outside overlay to close
        document.querySelectorAll('.category-selector, .menu-overlay').forEach(overlay => {
                overlay.addEventListener('click', function(e) {
                    if (e.target === this) {
                        this.classList.remove('active');
                    }
                });
            });

        // Navigation links
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const target = this.getAttribute('data-target');
                document.getElementById(target + 'Menu').classList.add('active');
            });
        });

        // ESC key to close overlay
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                document.querySelectorAll('.category-selector.active, .menu-overlay.active').forEach(overlay => {
                    overlay.classList.remove('active');
                });
            }
        });

        // Food item click - display photo gallery
        document.querySelectorAll('.menu-item').forEach(item => {
            item.addEventListener('click', function() {
                const foodName = this.getAttribute('data-item');
                const category = this.closest('.menu-overlay').id.replace('Menu', '');

                // Collect all food items from current category
                currentFoodItems = [];
                const menuItems = this.closest('.menu-items').querySelectorAll('.menu-item');
                menuItems.forEach((menuItem, index) => {
                    if (menuItem === this) {
                        currentIndex = index;
                    }
                    currentFoodItems.push({
                        name: menuItem.getAttribute('data-item'),
                        description: menuItem.querySelector('p').textContent
                    });
                });

                // Load current food data
               function loadFoodImage(foodName, index) {
    const baseName = foodName.toLowerCase().replace(/ /g, '_');
    const extensions = ['.jpg', '.png', '.jpeg', '.jpg.png'];

    let imageFound = false;
    let imageUrl = '';

    for (let ext of extensions) {
        const testUrl = baseName + ext;
        // Ellenőrizzük, hogy a kép létezik-e
        const xhr = new XMLHttpRequest();
        xhr.open('HEAD', testUrl, false);  // szinkron kérés
        xhr.send();
        if (xhr.status !== 404) {
            imageUrl = testUrl;
            imageFound = true;
            break;
        }
    }

    // Ha egyáltalán nincs kép, legyen egy helyettesítő
    if (!imageFound) {
        imageUrl = 'placeholder.png'; // ide tehetsz egy "not found" képet
    }

    // Betöltés a galériába
    document.getElementById('galleryTitle').textContent = foodName;
    document.getElementById('galleryDescription').textContent = currentFoodItems[index].description;
    document.getElementById('galleryImage').src = imageUrl;
    document.getElementById('galleryOverlay').classList.add('active');

    // Navigáció gombok frissítése
    updateNavButtons();
}
        }

        // Previous food
        document.getElementById('prevBtn').addEventListener('click', function() {
            if (currentIndex > 0) {
                currentIndex--;
                loadFoodImage(currentFoodItems[currentIndex].name, currentIndex);
            }
        });

        // Next food
        document.getElementById('nextBtn').addEventListener('click', function() {
                if (currentIndex < currentFoodItems.length - 1) {
                    currentIndex++;
                    loadFoodImage(currentFoodItems[currentIndex].name, currentIndex);
                }
            });

        // Update navigation buttons
        function updateNavButtons() {
            const prevBtn = document.getElementById('prevBtn');
            const nextBtn = document.getElementById('nextBtn');

            if (currentIndex === 0) {
                prevBtn.disabled = true;
                prevBtn.style.opacity = '0.5';
            } else {
                prevBtn.disabled = false;
                prevBtn.style.opacity = '1';
            }

            if (currentIndex === currentFoodItems.length - 1) {
                nextBtn.disabled = true;
                nextBtn.style.opacity = '0.5';
            } else {
                nextBtn.disabled = false;
                nextBtn.style.opacity = '1';
            }
        }
    </script>
</body>
</html>
