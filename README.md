<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Helen's Greek Kitchen</title>
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">

<style>
  body {
    font-family: 'Trebuchet MS', sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f8ff;
    color: #2e9cab;
    line-height: 1.6;
    scroll-behavior: smooth;
    text-align: center;
  }

  header img {
    width: 100%;
    height: auto;
    max-height: 400px;
    object-fit: cover;
  }

  nav {
    display: flex;
    justify-content: center;
    background-color: #2e9cab;
    flex-wrap: wrap;
    position: sticky;
    top: 0;
    z-index: 1000;
  }

  nav a {
    text-decoration: none;
    color: white;
    padding: 15px 20px;
    cursor: pointer;
    font-weight: bold;
    font-size: 1em;
    transition: background 0.3s, transform 0.2s;
  }

  nav a:hover {
    background-color: #2874a6;
    transform: scale(1.05);
  }

  section {
    max-width: 1000px;
    margin: 20px auto;
    padding: 0 20px;
  }

  h2 {
    color: #2e9cab;
    margin-top: 30px;
    border-bottom: 2px solid #2e9cab;
    padding-bottom: 5px;
    text-align: center;
  }

  .menu-item {
    margin: 20px auto;
    padding: 15px;
    border-left: 5px solid #2e9cab;
    background-color: #e6f2ff;
    border-radius: 8px;
    text-align: center;
  }

  .menu-item h3 {
    margin: 0 0 5px 0;
    font-size: 1.3em;
    color: #2e9cab;
  }

  .menu-item p {
    margin: 0;
    color: #2e9cab;
  }

  .order-button {
    display:inline-flex;
    align-items:center;
    justify-content:center;
    background-color:#2e9cab;
    color:white !important;
    padding:18px 35px;
    border-radius:50px;
    text-decoration:none;
    font-weight:bold;
    font-size:1.4em;
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    transition: background 0.3s, transform 0.2s, box-shadow 0.3s;
    margin:20px auto;
    text-align: center;
  }

  .order-button:hover {
    background-color: #1f618d;
    transform: scale(1.08);
    box-shadow: 0 8px 20px rgba(0,0,0,0.35);
  }

  footer {
    text-align: center;
    padding: 20px;
    background-color: #1f618d;
    color: white;
    margin-top: 30px;
  }

  /* Overlay */
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(240, 248, 255, 0.98);
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
    font-size: 2em;
    cursor: pointer;
    color: #2e9cab;
  }

  /* Category selector */
  .category-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
    max-width: 800px;
    margin: 50px auto;
  }

  .category-btn {
    background: #2e9cab;
    color: white;
    padding: 20px;
    border-radius: 15px;
    text-align: center;
    font-size: 1.3em;
    cursor: pointer;
    transition: 0.3s;
  }

  .category-btn:hover {
    background:#1f618d;
    transform: scale(1.05);
  }

  /* Hamburger menu */
  .hamburger {
    display: none;
    font-size: 2em;
    cursor: pointer;
    color: white;
    position: absolute;
    right: 20px;
    top: 10px;
  }

  .nav-links {
    display: flex;
    justify-content: center;
    width: 100%;
    flex-wrap: wrap;
  }

  @media (max-width: 800px) {
    .nav-links {
      display: none;
      flex-direction: column;
      background-color: #2e9cab;
      width: 100%;
    }

    .nav-links.show {
      display: flex;
    }

    .hamburger {
      display: block;
    }

    nav a {
      width: 100%;
      padding: 15px;
      box-sizing: border-box;
    }
  }

</style>
</head>
<body>

<header>
  <img src="header2.png" alt="Helen's Greek Kitchen Banner">
</header>

<nav>
  <div class="hamburger" id="hamburger"><i class="fas fa-bars"></i></div>
  <div class="nav-links" id="navLinks">
    <a data-overlay="aboutOverlay">About</a>
    <a data-overlay="allergensOverlay">Allergens</a>
    <a data-overlay="contactOverlay">Contact</a>
  </div>
</nav>

<section id="home-buttons" style="margin-top:50px;">
  <a id="menuBtnHome" class="order-button" data-overlay="categoryOverlay">Menu</a>
  <a href="https://goodeats.io/helensgreek" class="order-button" target="_blank">Order Now</a>
</section>

<!-- CATEGORY OVERLAY -->
<div id="categoryOverlay" class="overlay">
  <span class="close-btn" data-close="categoryOverlay">&times;</span>
  <h2>Select a Category</h2>
  <div class="category-grid">
    <div class="category-btn" data-overlay="startersOverlay">Starters</div>
    <div class="category-btn" data-overlay="wrapsOverlay">Wraps</div>
    <div class="category-btn" data-overlay="plattersOverlay">Platters</div>
    <div class="category-btn" data-overlay="questsOverlay">Greek Quests</div>
    <div class="category-btn" data-overlay="sweetOverlay">Sweet Treats</div>
  </div>
</div>

<!-- STARTERS OVERLAY -->
<div id="startersOverlay" class="overlay">
  <span class="close-btn" data-close="startersOverlay">&times;</span>
  <h2>Starters for the Gods</h2>
  <div class="menu-item">
    <h3>Tzatziki</h3>
    <p>Cucumber, Greek yogurt & garlic dip. The cool breeze of Mount Olympus captured in a bowl.</p>
  </div>
  <div class="menu-item">
    <h3>Hummus</h3>
    <p>Chickpeas, tahini, garlic & lemon. A silky dip so good even the gods double-dip.</p>
  </div>
  <div class="menu-item">
    <h3>Melitzanosalata</h3>
    <p>Smoked aubergine with olive oil, garlic & lemon. For those who like their meze with a little mystery.</p>
  </div>
  <div class="menu-item">
    <h3>Taramasalata</h3>
    <p>Cod roe dip. Pink, punchy & unapologetically Greek.</p>
  </div>
  <div class="menu-item">
    <h3>Dolmades</h3>
    <p>Vine leaves stuffed with rice & herbs. Like little scrolls of delicious Greek poetry.</p>
  </div>
  <div class="menu-item">
    <h3>Olives & Feta</h3>
    <p>The salty essence of the Aegean. Simplicity perfected.</p>
  </div>
  <div class="menu-item">
    <h3>Spanakopita</h3>
    <p>Spinach and feta wrapped in golden filo pastry. Zeus himself would approve.</p>
  </div>
  <div class="menu-item">
    <h3>Gigantes</h3>
    <p>Butter beans baked in tomato and herbs — hearty, humble, heavenly.</p>
  </div>
  <div class="menu-item">
    <h3>Halloumi</h3>
    <p>Grilled Cypriot cheese with honey drizzle. Sweet, salty, sizzling perfection.</p>
  </div>
  <div class="menu-item">
    <h3>Keftedakia</h3>
    <p>Greek meatballs seasoned with mint and oregano. Small bites, big flavour.</p>
  </div>
</div>

<!-- WRAPS OVERLAY -->
<div id="wrapsOverlay" class="overlay">
  <span class="close-btn" data-close="wrapsOverlay">&times;</span>
  <h2>Wraps for the Gods (Pita Gyros)</h2>
  <div class="menu-item">
    <h3>Pork Pita Gyros</h3>
    <p>Tender slices of marinated pork wrapped with tomato, onion, fries & tzatziki in warm Greek pita. Simple, divine, authentic.</p>
  </div>
  <div class="menu-item">
    <h3>Chicken Pita Gyros</h3>
    <p>Juicy grilled chicken with tomato, onion, fries & tzatziki. A wrap worthy of Apollo himself.</p>
  </div>
  <div class="menu-item">
    <h3>Halloumi Pita</h3>
    <p>Grilled halloumi with salad, fries & a drizzle of honey — the vegetarian hero of the Olympus.</p>
  </div>
  <div class="menu-item">
    <h3>Falafel Pita</h3>
    <p>Chickpea patties with salad, fries & hummus — flavourful, filling, fully legendary.</p>
  </div>
  <div class="menu-item">
    <h3>Mixed Gyros Pita</h3>
    <p>Half pork, half chicken, all Greek power. Balanced, bold, unbeatable.</p>
  </div>
  <div class="menu-item">
    <h3>Extra Pita</h3>
    <p>Because one is never enough.</p>
  </div>
</div>

<!-- PLATTERS OVERLAY -->
<div id="plattersOverlay" class="overlay">
  <span class="close-btn" data-close="plattersOverlay">&times;</span>
  <h2>Greek Me Baby One More Time (Platters)</h2>
  <div class="menu-item">
    <h3>Pork Gyros Plate</h3>
    <p>Tender pork gyros served with fries, pita, salad & tzatziki. As classic as a Santorini sunset.</p>
  </div>
  <div class="menu-item">
    <h3>Chicken Gyros Plate</h3>
    <p>Juicy marinated chicken gyros with fries, pita, salad & tzatziki. For when you want the full Greek treatment.</p>
  </div>
  <div class="menu-item">
    <h3>Mixed Gyros Plate</h3>
    <p>A perfect harmony of pork & chicken gyros. Served with fries, salad, pita & tzatziki. Because why choose?</p>
  </div>
  <div class="menu-item">
    <h3>Souvlaki Plate (Pork or Chicken)</h3>
    <p>Two skewers of your choice, flame-grilled & fabulous. Served with fries, salad, pita & tzatziki. Spartan strength guaranteed.</p>
  </div>
  <div class="menu-item">
    <h3>Halloumi Plate</h3>
    <p>Grilled halloumi cheese with salad, fries, pita & tzatziki. Proof that the gods love vegetarians too.</p>
  </div>
  <div class="menu-item">
    <h3>Falafel Plate</h3>
    <p>Golden falafel with salad, fries, pita & hummus. 100% plant-based, 1000% delicious.</p>
  </div>
  <div class="menu-item">
    <h3>Greek Salad Plate</h3>
    <p>Fresh tomato, cucumber, feta, olives, onion, oregano & olive oil. The legend that started it all.</p>
  </div>
</div>

<!-- QUESTS OVERLAY -->
<div id="questsOverlay" class="overlay">
  <span class="close-btn" data-close="questsOverlay">&times;</span>
  <h2>The Greek Quests</h2>
  <div class="menu-item">
    <h3>Moussaka</h3>
    <p>Layers of aubergine, spiced mince, and creamy béchamel baked golden. Comfort food, Greek-style.</p>
  </div>
  <div class="menu-item">
    <h3>Pastitsio</h3>
    <p>Greek pasta bake with mince and béchamel — the Mediterranean’s answer to lasagna.</p>
  </div>
  <div class="menu-item">
    <h3>Stifado</h3>
    <p>Beef stew slow-cooked with sweet onions and spices. Deep, rich, and made with love (and red wine).</p>
  </div>
  <div class="menu-item">
    <h3>Kleftiko</h3>
    <p>Lamb baked slowly until tender, with lemon, garlic, and herbs. A dish fit for heroes and rebels alike.</p>
  </div>
  <div class="menu-item">
    <h3>Briam</h3>
    <p>Oven-roasted vegetables in olive oil and herbs — sunshine in a tray.</p>
  </div>
</div>

<!-- SWEET TREATS OVERLAY -->
<div id="sweetOverlay" class="overlay">
  <span class="close-btn" data-close="sweetOverlay">&times;</span>
  <h2>Sweet Treats</h2>
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

<!-- ABOUT OVERLAY -->
<div id="aboutOverlay" class="overlay">
  <span class="close-btn" data-close="aboutOverlay">&times;</span>
  <h2>About</h2>
  <p>
    Helen's Greek Kitchen – Three Cups Pub<br><br>
    Welcome to Helen’s Greek Kitchen at The Three Cups Pub — where the charm of a classic English pub meets the fiery heart of Greek cooking.  
    Helen brings her passion straight from the islands — bold flavours, no shortcuts, and a little bit of drama in every dish.  
    From moussaka and spanakopita to perfectly grilled souvlaki and creamy tzatziki, every bite tells a story — one that usually ends with “just one more plate.”<br><br>
    The Three Cups keeps the drinks flowing — crisp pints, fine wines, and the occasional cheeky ouzo.  
    It’s the best of both worlds: a British pub with a Greek soul.<br><br>
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
  <ul class="allergen-list">
    <li>Gluten</li>
    <li>Crustaceans</li>
    <li>Eggs</li>
    <li>Fish</li>
    <li>Peanuts</li>
    <li>Soybeans</li>
    <li>Milk</li>
    <li>Nuts</li>
    <li>Celery</li>
    <li>Mustard</li>
    <li>Sesame seeds</li>
    <li>Sulphur dioxide and sulphites</li>
    <li>Lupin</li>
    <li>Molluscs</li>
  </ul>
</div>

<!-- CONTACT OVERLAY -->
<div id="contactOverlay" class="overlay">
  <span class="close-btn" data-close="contactOverlay">&times;</span>
  <h2>Contact</h2>
  <p>Email: <a href="mailto:hello@helenskitchen.uk">hello@helenskitchen.uk</a></p>
  <p>Phone: +44 123 456 789</p>
  <p>Address: The Three Cups Pub, London</p>
</div>

<footer>
  &copy; 2025 Helen's Greek Kitchen. All rights reserved.
</footer>

<script>
  // Overlay functionality
  document.querySelectorAll('[data-overlay]').forEach(btn => {
    btn.addEventListener('click', () => {
      const overlay = document.getElementById(btn.getAttribute('data-overlay'));
      overlay.style.display = 'block';
    });
  });

  document.querySelectorAll('.close-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      const overlay = document.getElementById(btn.getAttribute('data-close'));
      overlay.style.display = 'none';
    });
  });

  // Hamburger menu toggle
  const hamburger = document.getElementById('hamburger');
  const navLinks = document.getElementById('navLinks');
  hamburger.addEventListener('click', () => {
    navLinks.classList.toggle('show');
  });
</script>

</body>
</html>
