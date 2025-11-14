<!DOCTYPE html>
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
    color: white !important;
    padding: 15px 20px;
    cursor: pointer;
    font-weight: bold;
    font-size: 1em;
    transition: background 0.3s, transform 0.2s;
  }

  nav a:hover {
    background-color: #1f618d;
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
  }

  .menu-item {
    margin-bottom: 20px;
    padding: 15px;
    border-left: 5px solid #2e9cab;
    background-color: #e6f2ff;
    border-radius: 8px;
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
    margin:20px;
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

  .overlay h2 {
    text-align: center;
    color: #2e9cab;
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
    color: white !important;
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

  @media (max-width: 600px) {
    nav a { padding: 10px; font-size: 0.9em; }
    header img { max-height: 250px; }
    .order-button { font-size:1.2em; padding:15px 25px; }
    .category-btn { font-size:1.1em; padding:15px; }
  }
</style>
</head>
<body>

<header>
  <img src="header2.png" alt="Helen's Greek Kitchen Banner">
</header>

<nav>
  <a data-overlay="aboutOverlay">About</a>
  <a data-overlay="allergensOverlay">Allergens</a>
  <a data-overlay="contactOverlay">Contact</a>
</nav>

<section id="home-buttons" style="text-align:center; margin-top:50px;">
  <a id="menuBtnHome" class="order-button" data-overlay="categoryOverlay">Menu</a>
  <a href="https://goodeats.io/helensgreek" class="order-button" target="_blank">Order Now</a>
</section>

<!-- CATEGORY SELECTOR OVERLAY -->
<div id="categoryOverlay" class="overlay">
  <span class="close-btn" data-close="categoryOverlay">&times;</span>
  <h2>Select a Category</h2>
  <div class="category-grid">
    <div class="category-btn" data-overlay="startersOverlay">Starters for the Gods</div>
    <div class="category-btn" data-overlay="wrapsOverlay">Wraps for the Gods (Pita Gyros)</div>
    <div class="category-btn" data-overlay="plattersOverlay">Greek Me Baby One More Time</div>
    <div class="category-btn" data-overlay="questsOverlay">The Greek Quests</div>
    <div class="category-btn" data-overlay="sweetOverlay">Sweet Treats</div>
  </div>
</div>

<!-- STARTERS OVERLAY -->
<div id="startersOverlay" class="overlay">
  <span class="close-btn" data-close="startersOverlay">&times;</span>
  <h2>Starters for the Gods</h2>
  <p>Before the main feast, the gods liked to snack too. Sharing is optional. Greed is divine.</p>

  <div class="menu-item">
    <h3>Allitis Pitta</h3>
    <p>A homemade Classic from our own Greek Legend Helen. Beef Mince Meat on a pitta bread, served with a little salad and Authentic Greek Yogurt.</p>
  </div>
  <div class="menu-item">
    <h3>Feta Pastry with Honey</h3>
    <p>Crispy, Salty, Sweet and scandalously addictive. PDO Feta cheese wrapped in filo pastry and drizzled with honey & sesame.</p>
  </div>
  <div class="menu-item">
    <h3>Kolokithokeftedes</h3>
    <p>Crispy Courgettes fritters bursting with herb and Feta – Zeus himself declared them "dangerously moreish".</p>
  </div>
  <div class="menu-item">
    <h3>Greek Salad</h3>
    <p>Fresh, Crunchy and very Athenian-approved. Authentic Greek Salad with tomatoes, cucumber, bell pepper, onions, olives, extra virgin olive-oil and oregano.</p>
  </div>
  <div class="menu-item">
    <h3>Dolmades</h3>
    <p>Tender vine leaves, stuffed with rice and herbs. Served with a fresh lemon sauce.</p>
  </div>
  <div class="menu-item">
    <h3>Talagani Cheese</h3>
    <p>Grilled to golden perfection, crispy outside heavenly inside. Even Apollo could not resist.</p>
  </div>
  <div class="menu-item">
    <h3>Tzatziki</h3>
    <p>Cool Authentic Greek Yogurt, cucumber & garlic – combo of destiny. The shield that protects all gyros.</p>
  </div>
  <div class="menu-item">
    <h3>Aubergine Dip</h3>
    <p>Smokey, silky and deeply mysterious. If the Oracle of Delphi made Sushi, this would be it!</p>
  </div>
  <div class="menu-item">
    <h3>Houmous</h3>
    <p>Smooth, Garlicky and made with love (and Chickpeas). Served with Extra Virgin Olive Oil and paprika.</p>
  </div>
  <div class="menu-item">
    <h3>Olives</h3>
    <p>Simple. Classic. Eternal. Athena’s proudest invention.</p>
  </div>
</div>

<!-- WRAPS OVERLAY -->
<div id="wrapsOverlay" class="overlay">
  <span class="close-btn" data-close="wrapsOverlay">&times;</span>
  <h2>Wraps for the Gods (Pita Gyros)</h2>
  <p>All served in fluffy Greek pita with salad, fries & sauce. Don't ask for ketchup – we're not a chip shop.</p>

  <div class="menu-item">
    <h3>Pork Gyros</h3>
    <p>Juicy, smoky, and 100% approved by the intellectual Athenians. Served with fries, tomatoes, onions, and Tzatziki.</p>
  </div>
  <div class="menu-item">
    <h3>Chicken Gyros</h3>
    <p>Tastes like a Greek summer. Served with fries, tomatoes, onions, and Tzatziki.</p>
  </div>
  <div class="menu-item">
    <h3>Pork Souvlaki</h3>
    <p>Tender pork, kissed by fire and Greek spices. Served with fries, salad, and divine sauce.</p>
  </div>
  <div class="menu-item">
    <h3>Chicken Souvlaki</h3>
    <p>Succulent chicken, marinated, grilled to perfection. Served with salad, fries, and legendary sauce.</p>
  </div>
  <div class="menu-item">
    <h3>Kebab Souvlaki</h3>
    <p>Juicy, grilled goodness with sweet red peppers and ambrosia-inspired sauce. From £8.00</p>
  </div>
  <div class="menu-item">
    <h3>Greek Sausage</h3>
    <p>Bold, flavorful, and full of street-smart swagger. Herbs so good, even Dionysus would approve.</p>
  </div>
  <div class="menu-item">
    <h3>Talagani Wrap</h3>
    <p>Grilled Talagani, peppers, and a drizzle of lemon sauce. From £8.00</p>
  </div>
</div>

<!-- PLATTERS OVERLAY -->
<div id="plattersOverlay" class="overlay">
  <span class="close-btn" data-close="plattersOverlay">&times;</span>
  <h2>Greek Me Baby One More Time (Platters)</h2>
  <p>Because you always come back for more. Don’t deny it.</p>

  <div class="menu-item">
    <h3>Pork Kalamakia</h3>
    <p>Tender pork skewers, grilled to perfection. Includes 3 pork skewers, served with chips and salad.</p>
  </div>
  <div class="menu-item">
    <h3>Chicken Kalamakia</h3>
    <p>Succulent chicken skewers, marinated and flame-grilled. Served with chips and salad.</p>
  </div>
  <div class="menu-item">
    <h3>Kebab Portion</h3>
    <p>Succulent, juicy, grilled with fire. 3 juicy kebabs served with fries and salad.</p>
  </div>
  <div class="menu-item">
    <h3>Mixed Gyros</h3>
    <p>A little chicken, a little pork. Served with fries, pittas, bread, and salad.</p>
  </div>
  <div class="menu-item">
    <h3>Sausage Platter</h3>
    <p>Grilled sausages with fries and salad.</p>
  </div>
  <div class="menu-item">
    <h3>Vegetarian Platter</h3>
    <p>Talagani, peppers served with fries and salad. £14.00</p>
  </div>
  <div class="menu-item">
    <h3>Mixed Grill Platter</h3>
    <p>A little bit of everything for 2-3 people.</p>
  </div>
</div>

<!-- THE GREEK QUESTS OVERLAY -->
<div id="questsOverlay" class="overlay">
  <span class="close-btn" data-close="questsOverlay">&times;</span>
  <h2>The Greek Quests</h2>

  <div class="menu-item">
    <h3>Bifteki</h3>
    <p>Juicy Greek-style beef patties with herbs. Served with potatoes.</p>
  </div>
  <div class="menu-item">
    <h3>Briam</h3>
    <p>Baked vegetables with olive oil and herbs. Served with fries.</p>
  </div>
  <div class="menu-item">
    <h3>Gemista</h3>
    <p>Peppers and tomatoes stuffed with herby rice.</p>
  </div>
  <div class="menu-item">
    <h3>Giouvesti</h3>
    <p>Tender chicken baked with orzo, tomato, and cinnamon. Comes with fries.</p>
  </div>
  <div class="menu-item">
    <h3>Kleftiko</h3>
    <p>Lamb baked until tender. Served with roast potatoes.</p>
  </div>
  <div class="menu-item">
    <h3>Lemon Chicken</h3>
    <p>Tender chicken baked in zesty lemon sauce.</p>
  </div>
  <div class="menu-item">
    <h3>Mousakas</h3>
    <p>Layers of aubergine, spiced mince, and béchamel baked golden.</p>
  </div>
  <div class="menu-item">
    <h3>Paboutskia</h3>
    <p>Stuffed aubergines with spiced mince.</p>
  </div>
  <div class="menu-item">
    <h3>Pastitsio</h3>
    <p>Pasta with spiced mince and béchamel.</p>
  </div>
  <div class="menu-item">
    <h3>Plaki Fish</h3>
    <p>Oven-baked fish with tomatoes, onions, olives, and herbs.</p>
  </div>
  <div class="menu-item">
    <h3>Red Chicken</h3>
    <p>Tender chicken simmered in rich tomato sauce. Fries on the side.</p>
  </div>
  <div class="menu-item">
    <h3>Stifado</h3>
    <p>Slow-cooked beef with sweet onions. Fries accompany.</p>
  </div>
</div>

<!-- SWEET TREATS OVERLAY -->
<div id="sweetOverlay" class="overlay">
  <span class="close-btn" data-close="sweetOverlay">&times;</span>
  <h2>Sweet Treats</h2>
  <div class="menu-item">
    <h3>Baklavas</h3>
    <p>Flaky, nutty, sticky perfection.</p>
  </div>
  <div class="menu-item">
    <h3>Chocolate Cake</h3>
    <p>Decadent, rich, and dangerously delicious.</p>
  </div>
  <div class="menu-item">
    <h3>Orange Cake</h3>
    <p>Zesty, sweet and sun-kissed.</p>
  </div>
  <div class="menu-item">
    <h3>Ravani</h3>
    <p>Greek semolina cake drenched in syrup.</p>
  </div>
</div>

<!-- ABOUT OVERLAY -->
<div id="aboutOverlay" class="overlay">
  <span class="close-btn" data-close="aboutOverlay">&times;</span>
  <h2>About</h2>
  <p>
    Helen's Greek Kitchen – Three Cups Pub<br><br>
    Welcome to Helen’s Greek Kitchen at The Three Cups Pub — where the charm of a classic English pub meets the fiery heart of Greek cooking.<br>
    Helen brings her passion straight from the islands — bold flavours, no shortcuts, and a little bit of drama in every dish.<br>
    From moussaka and spanakopita to perfectly grilled souvlaki and creamy tzatziki, every bite tells a story.<br><br>
    The Three Cups keeps the drinks flowing — crisp pints, fine wines, and the occasional cheeky ouzo.<br>
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
  <p>Gluten, Crustaceans, Eggs, Fish, Peanuts, Soybeans, Milk, Nuts, Celery, Mustard, Sesame seeds, Sulph
