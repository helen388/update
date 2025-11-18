<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Epiros Greek Grill Menu</title>

    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, Helvetica, sans-serif;
            background-color: #ffffff;
            color: #333333;
        }

        header {
            width: 100%;
            background-color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            padding-top: 20px;
            padding-bottom: 20px;
        }

        header img {
            width: 420px;
            height: auto;
            display: block;
            margin: 0 auto;
        }

        .menu-section {
            width: 100%;
            box-sizing: border-box;
            padding-top: 15px;
            padding-bottom: 15px;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .menu-section h2 {
            margin: 0;
            font-size: 32px;
            font-weight: 900;
            text-align: center;
        }

        .category-divider {
            width: 100%;
            height: 6px;
            background-color: #000000;
            margin-top: 15px;
        }

        .menu-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.92);
            display: none;
            flex-direction: column;
            align-items: center;
            overflow-y: auto;
            padding-bottom: 100px;
        }

        .menu-overlay.active {
            display: flex;
        }

        .menu-overlay h2 {
            color: #ffffff;
            font-size: 40px;
            margin-top: 30px;
            margin-bottom: 20px;
            text-align: center;
            font-weight: 900;
        }

        .menu-item {
            width: 90%;
            max-width: 1000px;
            background-color: #ffffff;
            color: #000000;
            margin-top: 10px;
            margin-bottom: 10px;
            padding: 20px;
            border-radius: 6px;
            cursor: pointer;
            border: 2px solid #000000;
            box-sizing: border-box;
        }

        .menu-item:hover {
            background-color: #f2f2f2;
        }

        .menu-item p {
            margin: 0;
            font-size: 22px;
            line-height: 30px;
            font-weight: 700;
        }

        .close-button {
            margin-top: 20px;
            margin-bottom: 25px;
            padding: 10px 25px;
            background-color: #ffffff;
            color: #000000;
            border: 3px solid #000000;
            border-radius: 8px;
            cursor: pointer;
            font-size: 22px;
            font-weight: 900;
        }

        .close-button:hover {
            background-color: #e6e6e6;
        }

        .gallery-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.94);
            display: none;
            flex-direction: column;
            align-items: center;
            overflow-y: auto;
            padding-bottom: 80px;
        }

        .gallery-overlay.active {
            display: flex;
        }

        .gallery-title {
            color: #ffffff;
            font-size: 40px;
            font-weight: 900;
            margin-top: 30px;
            margin-bottom: 20px;
            text-align: center;
        }

        .gallery-description {
            color: #ffffff;
            font-size: 22px;
            font-weight: 400;
            width: 80%;
            max-width: 900px;
            text-align: center;
            line-height: 30px;
            margin-bottom: 15px;
        }

        .gallery-image {
            width: 90%;
            max-width: 800px;
            border-radius: 12px;
            border: 4px solid #ffffff;
            margin-bottom: 40px;
        }

        .nav-buttons {
            display: flex;
            flex-direction: row;
            justify-content: center;
            width: 100%;
            margin-bottom: 40px;
        }

        .nav-button {
            background-color: #ffffff;
            color: #000000;
            padding: 10px 30px;
            margin-left: 15px;
            margin-right: 15px;
            border-radius: 8px;
            border: 3px solid #000000;
            cursor: pointer;
            font-size: 22px;
            font-weight: 900;
        }

        .nav-button:disabled {
            opacity: 0.45;
            cursor: default;
        }

        .nav-button:hover:not(:disabled) {
            background-color: #e6e6e6;
        }

        .gallery-close {
            padding: 10px 25px;
            margin-bottom: 50px;
            background-color: #ffffff;
            color: #000000;
            border: 3px solid #000000;
            border-radius: 8px;
            cursor: pointer;
            font-size: 22px;
            font-weight: 900;
        }

        .gallery-close:hover {
            background-color: #e6e6e6;
        }
    </style>
</head>
<body>
  <!-- MAIN PAGE CONTENT (folytatás a body-ban) -->

    <!-- Intro / Welcome (About) -->
    <section id="about" class="menu-section" style="padding-top:10px; padding-bottom:10px;">
        <div class="container" style="max-width:1000px; margin:0 auto; text-align:center;">
            <h2 style="font-size:28px; font-weight:900; margin-bottom:12px;">Helen's Greek Kitchen – Three Cups Pub</h2>
            <p style="font-size:18px; line-height:26px; max-width:900px; margin:0 auto 18px;">
                Welcome to Helen’s Greek Kitchen at The Three Cups Pub — where the charm of a classic English pub meets the fiery heart of Greek cooking. It’s the kind of place where a hearty “OPA!” might echo over the bar, and the smell of sizzling souvlaki competes with the sound of laughter and clinking pint glasses.
            </p>
            <p style="font-size:18px; line-height:26px; max-width:900px; margin:0 auto 18px;">
                Helen brings her passion straight from the islands — she cooks like a true Greek mama: bold flavours, no shortcuts, and a little bit of drama in every dish. From her famous moussaka and golden spanakopita to perfectly grilled souvlaki and creamy tzatziki, every bite tells a story — one that usually ends with “just one more plate.”
            </p>
            <p style="font-size:18px; line-height:26px; max-width:900px; margin:0 auto 18px;">
                Meanwhile, The Three Cups keeps the drinks flowing — crisp pints, fine wines, and the occasional cheeky ouzo if you’re feeling brave. It’s the best of both worlds: a British pub with a Greek soul. Whether you’re here for a quiet pint, a lively dinner, or to argue over who makes the best baklava, you’ll always find good food, good company, and a warm welcome.
            </p>
            <p style="font-size:16px; color:#666; margin-top:8px;">Order from 15:00 to 22:00 | Greek + Mediterranean + Hot food | Collection + Table orders | Order from Table QR Code</p>
        </div>
    </section>

    <!-- Category quick links divider -->
    <div class="category-divider" style="margin-bottom:30px;"></div>

    <!-- Category cards (small static representation on the page for quick access as well) -->
    <div class="container" style="max-width:1100px; margin:0 auto 30px;">
        <div style="display:flex; gap:12px; flex-wrap:wrap; justify-content:center;">
            <button class="action-button" id="openStartersBtn" style="padding:12px 20px; font-size:16px;">Starters for the Gods</button>
            <button class="action-button" id="openWrapsBtn" style="padding:12px 20px; font-size:16px;">Wraps for the Gods</button>
            <button class="action-button" id="openPlattersBtn" style="padding:12px 20px; font-size:16px;">Greek Me Baby One More Time</button>
            <button class="action-button" id="openQuestsBtn" style="padding:12px 20px; font-size:16px;">The Greek Quests</button>
            <button class="action-button" id="openSweetsBtn" style="padding:12px 20px; font-size:16px;">Sweet Treats</button>
        </div>
    </div>

    <!-- STARTERS MENU OVERLAY -->
    <div id="startersMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="startersMenu">CLOSE</button>
        <h2>STARTERS FOR THE GODS</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">Before the main feast, the gods liked to snack too. Sharing is optional. Greed is divine.</p>

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
            <p style="font-weight:700; color:#222;">£3.00</p>
        </div>

        <div class="menu-item" data-item="Aubergine Dip">
            <h3>Aubergine Dip</h3>
            <p>Smokey, silky and deeply mysterious. If the Oracle of Delphi made Sushi, this would be it!</p>
            <p style="font-weight:700; color:#222;">£3.00</p>
        </div>

        <div class="menu-item" data-item="Houmous">
            <h3>Houmous</h3>
            <p>Smooth, Garlicky and made with love (and Chickpeas.) The dip of diplomacy – unites all tables. Served with Extra Virgin Olive Oil and paprika.</p>
        </div>

        <div class="menu-item" data-item="Olives">
            <h3>Olives</h3>
            <p>Simple. Classic. Eternal. Athena’s proudest invention. Respect the Olive!</p>
        </div>
    </div>

    <!-- WRAPS MENU OVERLAY -->
    <div id="wrapsMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="wrapsMenu">CLOSE</button>
        <h2>WRAPS FOR THE GODS (PITA GYROS)</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">All served in fluffy Greek pita with salad, fries & sauce. Don't ask for ketchup – we're not a chip shop.</p>

        <div class="menu-item" data-item="Pork Gyros">
            <h3>Pork Gyros</h3>
            <p>Juicy, smoky, and 100% approved by the intellectual Athenians. Yes, Socrates would've ordered two. Pork Gyros, served with fries, tomatoes, onions, and Tzatziki.</p>
        </div>

        <div class="menu-item" data-item="Chicken Gyros">
            <h3>Chicken Gyros</h3>
            <p>Tastes like a Greek summer, desired by ancient Spartan warriors. Will not give you abs, sorry. Chicken Gyros, served with fries, tomatoes, onions, and Tzatziki.</p>
        </div>

        <div class="menu-item" data-item="Pork Souvlaki">
            <h3>Pork Souvlaki</h3>
            <p>Tender pork, kissed by fire and Greek spices, wrapped in fluffy pita glory. Served with fries, salad, and our divine sauce – so good even Hera might sneak a bite.</p>
        </div>

        <div class="menu-item" data-item="Chicken Souvlaki">
            <h3>Chicken Souvlaki</h3>
            <p>Succulent chicken, marinated like a Spartan's secret weapon, grilled to perfection. Wrapped with salad, fries, and our legendary sauce – a true hero's handheld feast.</p>
        </div>

        <div class="menu-item" data-item="Kebab Souvlaki">
            <h3>Kebab Souvlaki</h3>
            <p>All the juicy, grilled goodness of our kebab, wrapped tighter than Athena's helmet. Sweet red peppers and our secret “ambrosia-inspired” sauce create a Greek miracle in every mouthful.</p>
            <p style="font-weight:700; color:#222;">From £8.00</p>
        </div>

        <div class="menu-item" data-item="Greek Sausage">
            <h3>Greek Sausage</h3>
            <p>Bold, flavorful, and full of street-smart swagger straight from the Greek agora. Not spicy – passionate. Herbs so good, even Dionysus would raise his goblet in approval.</p>
        </div>

        <div class="menu-item" data-item="Talagani Wrap">
            <h3>Talagani Wrap</h3>
            <p>Grilled Talagani (our very own halloumi), peppers, and a drizzle of zesty lemon sauce make this a Mount Olympus-worthy delight.</p>
            <p style="font-weight:700; color:#222;">From £8.00</p>
        </div>
    </div>

    <!-- PLATTERS MENU OVERLAY -->
    <div id="plattersMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="plattersMenu">CLOSE</button>
        <h2>GREEK ME BABY ONE MORE TIME</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">Platters fit for Olympus - share with your fellow gods or keep it all for yourself</p>

        <div class="menu-item" data-item="Pork Kalamakia">
            <h3>Pork Kalamakia</h3>
            <p>Tender pork skewers, grilled to perfection and kissed by the flames of Mount Olympus. Includes 3 juicy pork skewers, served with chips and salad.</p>
        </div>

        <div class="menu-item" data-item="Chicken Kalamakia">
            <h3>Chicken Kalamakia</h3>
            <p>Succulent chicken skewers, marinated and flame-grilled until golden. Includes 3 chicken skewers, served with chips and salad.</p>
        </div>

        <div class="menu-item" data-item="Kebab Portion">
            <h3>Kebab Portion</h3>
            <p>Succulent, juicy, and grilled with the fire of Hephaestus himself. One bite and you’ll be chanting Opa! 3 juicy kebabs served with fries and salad.</p>
        </div>

        <div class="menu-item" data-item="Mixed Gyros">
            <h3>Mixed Gyros</h3>
            <p>The ultimate gyro adventure: a little chicken, a little pork, a lot of deliciousness. Served with fries, pittas, bread, and salad.</p>
        </div>

        <div class="menu-item" data-item="Sausage Platter">
            <h3>Sausage Platter</h3>
            <p>A heroic lineup of sausages, grilled to perfection. Served with fries and salad.</p>
        </div>

        <div class="menu-item" data-item="Vegetarian Platter">
            <h3>Vegetarian Platter</h3>
            <p>A garden party straight from Mount Olympus. Talagani, and peppers served with fries and salad.</p>
            <p style="font-weight:700; color:#222;">£14.00</p>
        </div>

        <div class="menu-item" data-item="Mixed Grill Platter">
            <h3>Mixed Grill Platter</h3>
            <p>A little bit of everything for the indecisive Greek legend. It’s like a symposium, but tastier – feeds 2-3 fully grown Greeks.</p>
        </div>
    </div>

    <!-- QUESTS MENU OVERLAY -->
    <div id="questsMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="questsMenu">CLOSE</button>
        <h2>THE GREEK QUESTS</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">Traditional Greek main courses that will take you on a culinary journey</p>

        <div class="menu-item" data-item="Bifteki">
            <h3>Bifteki</h3>
            <p>Juicy Greek-style beef patties filled with herbs and maybe a secret or two from Mount Parnassus. Potatoes accompany – because every epic meal needs a side.</p>
        </div>

        <div class="menu-item" data-item="Briam">
            <h3>Briam</h3>
            <p>A vibrant medley of baked vegetables, olive oil, and herbs – the garden of the gods on a plate. Served with fries.</p>
        </div>

        <div class="menu-item" data-item="Gemista">
            <h3>Gemista</h3>
            <p>Peppers and tomatoes stuffed with herby rice and good vibes only. So fresh and wholesome, Aphrodite herself might’ve packed it for a beach picnic.</p>
        </div>

        <div class="menu-item" data-item="Giouvesti">
            <h3>Giouvesti</h3>
            <p>Tender chicken baked with orzo, tomato, and a hint of cinnamon. Comes with fries.</p>
        </div>

        <div class="menu-item" data-item="Kleftiko">
            <h3>Kleftiko</h3>
            <p>Lamb so tender it practically sings of Greek islands and olive groves. Served with roast potatoes.</p>
        </div>

        <div class="menu-item" data-item="Lemon Chicken">
            <h3>Lemon Chicken</h3>
            <p>Tender chicken baked in zesty lemon sauce that could wake Zeus from a nap. Fries on the side.</p>
        </div>

        <div class="menu-item" data-item="Mousakas">
            <h3>Mousakas</h3>
            <p>Layers of aubergine, spiced mince, and creamy béchamel baked golden. Like a warm Greek sunset on your plate.</p>
        </div>

        <div class="menu-item" data-item="Paboutskia">
            <h3>Paboutskia</h3>
            <p>Stuffed aubergines overflowing with spiced mince and sunshine. It’s basically the Greek version of comfort food.</p>
        </div>

        <div class="menu-item" data-item="Pastitsio">
            <h3>Pastitsio</h3>
            <p>Pasta, spiced mince, and luscious béchamel in perfect harmony. Even Hercules wouldn’t say no.</p>
        </div>

        <div class="menu-item" data-item="Plaki Fish">
            <h3>Plaki Fish</h3>
            <p>Oven-baked fish with tomatoes, onions, olives, and herbs that sing of the Aegean breeze. Poseidon’s favorite.</p>
        </div>

        <div class="menu-item" data-item="Red Chicken">
            <h3>Red Chicken</h3>
            <p>Tender chicken simmered in a rich tomato sauce kissed by the sun. Fries on the side.</p>
        </div>

        <div class="menu-item" data-item="Stifado">
            <h3>Stifado</h3>
            <p>Slow-cooked beef with sweet onions and romantic spices, simmered to perfection. Fries accompany.</p>
        </div>
    </div>

    <!-- SWEETS MENU OVERLAY -->
    <div id="sweetsMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="sweetsMenu">CLOSE</button>
        <h2>SWEET TREATS</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">Desserts worthy of the gods - because even Olympus needs something sweet!</p>

        <div class="menu-item" data-item="Baklava">
            <h3>Baklava</h3>
            <p>Flaky, nutty, sticky perfection. Athena would swap her owl for a piece.</p>
        </div>

        <div class="menu-item" data-item="Chocolate Cake">
            <h3>Chocolate Cake</h3>
            <p>Decadent, rich, and dangerously delicious. Even Hades would sneak a slice.</p>
        </div>

        <div class="menu-item" data-item="Orange Cake">
            <h3>Orange Cake</h3>
            <p>Zesty, sweet and sun-kissed. Helios himself might approve.</p>
        </div>

        <div class="menu-item" data-item="Ravani">
            <h3>Ravani</h3>
            <p>Greek semolina cake drenched in syrup. A sweet hug from the Mediterranean.</p>
        </div>
    </div>

    <!-- About / Allergens / Contact overlays for nav-links -->
    <div id="aboutMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="aboutMenu">CLOSE</button>
        <h2>About</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">
            Helen's Greek Kitchen – Three Cups Pub. Welcome to Helen’s kitchen. We bring authentic Greek home cooking to a friendly pub environment. Fresh ingredients, bold flavours, and warm hospitality.
        </p>
    </div>

    <div id="allergensMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="allergensMenu">CLOSE</button>
        <h2>Allergens</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">
            Please inform our staff of any allergies. Dishes may contain allergens including: gluten, dairy (milk, cheese), nuts, sesame, eggs, soy, fish, and shellfish. Cross-contamination may occur.
        </p>
    </div>

    <div id="contactMenu" class="menu-overlay" aria-hidden="true">
        <button class="close-button close-overlay" data-close="contactMenu">CLOSE</button>
        <h2>Contact</h2>
        <p style="color:#ffffff; max-width:900px; text-align:center; margin-bottom:20px;">
            Helen's Greek Kitchen at The Three Cups Pub<br>
            Phone: +44 20 0000 0000 (replace with real number)<br>
            Email: hello@helensgreek.example (replace with real email)
        </p>
    </div>

    <!-- GALLERY OVERLAY (used for all menu-item clicks) -->
    <div id="galleryOverlay" class="gallery-overlay" aria-hidden="true">
        <div style="width:100%; display:flex; justify-content:flex-end; padding:20px;">
            <button class="close-button close-overlay" data-close="galleryOverlay">CLOSE</button>
        </div>
        <h2 class="gallery-title" id="galleryTitle">Food Name</h2>
        <img id="galleryImage" class="gallery-image" src="" alt="Food photo">
        <p class="gallery-description" id="galleryDescription">Food description</p>

        <div class="nav-buttons" style="margin-top:20px;">
            <button id="prevBtn" class="nav-button">Previous</button>
            <button id="nextBtn" class="nav-button">Next</button>
        </div>

        <button id="galleryCloseBtn" class="gallery-close" style="margin-top:30px;">CLOSE GALLERY</button>
    </div>

    <!-- Footer already provided in part 1; repeat small spacer here -->
    <div style="height:40px;"></div>

    <!-- END OF HTML CONTENT - JAVASCRIPT FOLYIK ITT TOVABB -->
    <script>
        // FULL JAVASCRIPT: event handling, gallery image resolution, overlay control, keyboard handling
        // No short forms, no omissions. Everything explicit.

        // Helper: find first existing image from base path + extensions.
        // Uses Image() onload/onerror to detect existence asynchronously.
        function findImageUrl(basePath, baseName, callback) {
            // basePath should end with '/' or be empty string; baseName is without extension
            var exts = ['.jpg', '.png', '.jpeg', '.jpg.png', '.JPG', '.PNG', '.JPEG'];
            var tried = 0;
            var found = false;
            var result = '';
            // Try each extension in order; call callback(resultOrNull) when first found or null if none.
            function tryNext() {
                if (tried >= exts.length) {
                    // none found
                    callback(null);
                    return;
                }
                var ext = exts[tried];
                tried++;
                var url = basePath + baseName + ext;
                var img = new Image();
                img.onload = function() {
                    if (!found) {
                        found = true;
                        result = url;
                        callback(result);
                    }
                };
                img.onerror = function() {
                    // try next
                    tryNext();
                };
                // trigger load
                img.src = url;
            }
            tryNext();
        }

        // Variables for gallery data
        var currentFoodItems = []; // array of { name: string, description: string }
        var currentIndex = 0;

        // Open category overlays from top quick buttons
        document.getElementById('openStartersBtn').addEventListener('click', function() {
            document.getElementById('startersMenu').classList.add('active');
            document.getElementById('startersMenu').setAttribute('aria-hidden', 'false');
            scrollToTopOfOverlay('startersMenu');
        });
        document.getElementById('openWrapsBtn').addEventListener('click', function() {
            document.getElementById('wrapsMenu').classList.add('active');
            document.getElementById('wrapsMenu').setAttribute('aria-hidden', 'false');
            scrollToTopOfOverlay('wrapsMenu');
        });
        document.getElementById('openPlattersBtn').addEventListener('click', function() {
            document.getElementById('plattersMenu').classList.add('active');
            document.getElementById('plattersMenu').setAttribute('aria-hidden', 'false');
            scrollToTopOfOverlay('plattersMenu');
        });
        document.getElementById('openQuestsBtn').addEventListener('click', function() {
            document.getElementById('questsMenu').classList.add('active');
            document.getElementById('questsMenu').setAttribute('aria-hidden', 'false');
            scrollToTopOfOverlay('questsMenu');
        });
        document.getElementById('openSweetsBtn').addEventListener('click', function() {
            document.getElementById('sweetsMenu').classList.add('active');
            document.getElementById('sweetsMenu').setAttribute('aria-hidden', 'false');
            scrollToTopOfOverlay('sweetsMenu');
        });

        // Utility to scroll overlay to top for consistent UX
        function scrollToTopOfOverlay(id) {
            try {
                var el = document.getElementById(id);
                if (el) el.scrollTop = 0;
            } catch(e) { /* ignore */ }
        }

        // show/hide categorySelector from header main button (from part 1)
        var showMenuBtn = document.getElementById('showMenu');
        if (showMenuBtn) {
            showMenuBtn.addEventListener('click', function(e) {
                e.preventDefault();
                var cs = document.getElementById('categorySelector');
                if (cs) {
                    cs.classList.add('active');
                    cs.setAttribute('aria-hidden','false');
                }
            });
        }

        // nav-link elements (About / Allergens / Contact)
        var navLinks = document.querySelectorAll('.nav-link');
        navLinks.forEach(function(link){
            link.addEventListener('click', function(e){
                e.preventDefault();
                var target = link.getAttribute('data-target');
                if (target === 'about') {
                    document.getElementById('aboutMenu').classList.add('active');
                    document.getElementById('aboutMenu').setAttribute('aria-hidden','false');
                } else if (target === 'allergens') {
                    document.getElementById('allergensMenu').classList.add('active');
                    document.getElementById('allergensMenu').setAttribute('aria-hidden','false');
                } else if (target === 'contact') {
                    document.getElementById('contactMenu').classList.add('active');
                    document.getElementById('contactMenu').setAttribute('aria-hidden','false');
                }
            });
        });

        // Close overlay buttons (all elements with class 'close-overlay' and data-close attr)
        var closeButtons = document.querySelectorAll('.close-overlay');
        closeButtons.forEach(function(btn){
            btn.addEventListener('click', function(){
                var targetId = btn.getAttribute('data-close');
                if (targetId) {
                    var targetEl = document.getElementById(targetId);
                    if (targetEl) {
                        targetEl.classList.remove('active');
                        targetEl.setAttribute('aria-hidden','true');
                    }
                }
            });
        });

        // Click outside overlay content to close (for elements with class menu-overlay or gallery-overlay)
        var overlays = document.querySelectorAll('.menu-overlay, .gallery-overlay, .category-selector');
        overlays.forEach(function(overlay){
            overlay.addEventListener('click', function(e){
                if (e.target === overlay) {
                    overlay.classList.remove('active');
                    overlay.setAttribute('aria-hidden','true');
                }
            });
        });

        // ESC to close any active overlay
        document.addEventListener('keydown', function(e){
            if (e.key === 'Escape' || e.key === 'Esc') {
                overlays.forEach(function(overlay){
                    if (overlay.classList.contains('active')) {
                        overlay.classList.remove('active');
                        overlay.setAttribute('aria-hidden','true');
                    }
                });
            }
        });

        // Build a NodeList of all current menu items (from all overlays)
        var menuItems = document.querySelectorAll('.menu-item');

        // Add click handler to each menu-item to open gallery
        menuItems.forEach(function(item){
            item.addEventListener('click', function(){
                // Build currentFoodItems array from the parent overlay's menu-items only (so Prev/Next is category-scoped)
                var parentOverlay = item.closest('.menu-overlay');
                var itemsInCategory = parentOverlay.querySelectorAll('.menu-item');
                currentFoodItems = []; // reset
                var clickedIndex = 0;
                itemsInCategory.forEach(function(mi, idx){
                    var name = mi.getAttribute('data-item') || mi.querySelector('h3').textContent || ('item_' + idx);
                    var desc = '';
                    var p = mi.querySelector('p');
                    if (p) desc = p.textContent;
                    currentFoodItems.push({ name: name, description: desc });
                    if (mi === item) clickedIndex = idx;
                });
                currentIndex = clickedIndex;
                openGalleryForCurrentIndex();
            });
        });

        // Gallery elements
        var galleryOverlay = document.getElementById('galleryOverlay');
        var galleryImage = document.getElementById('galleryImage');
        var galleryTitle = document.getElementById('galleryTitle');
        var galleryDescription = document.getElementById('galleryDescription');
        var prevBtn = document.getElementById('prevBtn');
        var nextBtn = document.getElementById('nextBtn');
        var galleryCloseBtn = document.getElementById('galleryCloseBtn');

        // When gallery close button clicked
        if (galleryCloseBtn) {
            galleryCloseBtn.addEventListener('click', function(){
                if (galleryOverlay) {
                    galleryOverlay.classList.remove('active');
                    galleryOverlay.setAttribute('aria-hidden','true');
                }
            });
        }

        // Prev / Next buttons
        if (prevBtn) {
            prevBtn.addEventListener('click', function(){
                if (currentIndex > 0) {
                    currentIndex = currentIndex - 1;
                    openGalleryForCurrentIndex();
                }
            });
        }
        if (nextBtn) {
            nextBtn.addEventListener('click', function(){
                if (currentIndex < currentFoodItems.length - 1) {
                    currentIndex = currentIndex + 1;
                    openGalleryForCurrentIndex();
                }
            });
        }

        // Core: open gallery for currentIndex and load first available image
        function openGalleryForCurrentIndex() {
            var item = currentFoodItems[currentIndex];
            if (!item) return;
            galleryTitle.textContent = item.name;
            galleryDescription.textContent = item.description;
            galleryImage.src = ''; // reset while we try to find
            galleryOverlay.classList.add('active');
            galleryOverlay.setAttribute('aria-hidden','false');

            // Build base name from item.name
            var baseName = item.name.toLowerCase().replace(/\s+/g, '_').replace(/[^a-z0-9_\-]/g, '');
            var basePath = 'food_images/'; // images folder - ensure you have this folder
            findImageUrl(basePath, baseName, function(foundUrl){
                if (foundUrl) {
                    galleryImage.src = foundUrl;
                } else {
                    // fallback placeholder - ensure placeholder exists in food_images
                    galleryImage.src = basePath + 'placeholder.png';
                }
            });

            // Update nav button states
            updateGalleryNavButtons();
        }

        function updateGalleryNavButtons() {
            if (!prevBtn || !nextBtn) return;
            if (currentIndex <= 0) {
                prevBtn.disabled = true;
                prevBtn.style.opacity = '0.45';
            } else {
                prevBtn.disabled = false;
                prevBtn.style.opacity = '1';
            }
            if (currentIndex >= currentFoodItems.length - 1) {
                nextBtn.disabled = true;
                nextBtn.style.opacity = '0.45';
            } else {
                nextBtn.disabled = false;
                nextBtn.style.opacity = '1';
            }
        }

        // Also handle keyboard left/right for gallery navigation when gallery is open
        document.addEventListener('keydown', function(e){
            if (galleryOverlay && galleryOverlay.classList.contains('active')) {
                if (e.key === 'ArrowLeft') {
                    if (currentIndex > 0) {
                        currentIndex = currentIndex - 1;
                        openGalleryForCurrentIndex();
                    }
                } else if (e.key === 'ArrowRight') {
                    if (currentIndex < currentFoodItems.length - 1) {
                        currentIndex = currentIndex + 1;
                        openGalleryForCurrentIndex();
                    }
                }
            }
        });

        // Close any open menu overlays when user navigates away using the category selector cards
        var categoryCards = document.querySelectorAll('.category-card');
        categoryCards.forEach(function(card){
            card.addEventListener('click', function(){
                var category = card.getAttribute('data-category');
                // close category selector
                var cs = document.getElementById('categorySelector');
                if (cs) cs.classList.remove('active');
                // open respective overlay
                var overlayId = category + 'Menu';
                var ov = document.getElementById(overlayId);
                if (ov) {
                    ov.classList.add('active');
                    ov.setAttribute('aria-hidden','false');
                    scrollToTopOfOverlay(overlayId);
                }
            });
        });

        // Ensure that if user resizes or loads the page, focus/aria states remain consistent
        window.addEventListener('load', function(){
            // make sure overlays are hidden
            overlays.forEach(function(o){ o.classList.remove('active'); o.setAttribute('aria-hidden','true'); });
        });
    </script>
</body>
</html>
