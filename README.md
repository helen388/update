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

  .hamburger {
    display: none;
    font-size: 2em;
    color: white;
    position: absolute;
    right: 20px;
    top: 10px;
    cursor: pointer;
    z-index: 1100;
  }

  .mobile-nav {
    display: none;
    flex-direction: column;
    background-color: #2e9cab;
    position: fixed;
    top: 60px;
    width: 100%;
    left: 0;
    z-index: 1050;
  }

  .mobile-nav a {
    padding: 15px;
    border-top: 1px solid rgba(255,255,255,0.2);
    text-align: center;
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

  @media (max-width: 768px) {
    nav a { display: none; }
    .hamburger { display: block; }
    .mobile-nav { display: none; }
    header img { max-height: 250px; }
    .order-button { font-size:1.2em; padding:15px 25px; }
    .category-btn { font-size:1.1em; padding:15px; }
  }
</style>
</head>
<body>

<header>
  <img src="header2.png" alt="Helen's Greek Kitchen Banner">
  <div class="hamburger"><i class="fas fa-bars"></i></div>
</header>

<nav>
  <a data-overlay="aboutOverlay">About</a>
  <a data-overlay="allergensOverlay">Allergens</a>
  <a data-overlay="contactOverlay">Contact</a>
</nav>

<div class="mobile-nav">
  <a data-overlay="aboutOverlay">About</a>
  <a data-overlay="allergensOverlay">Allergens</a>
  <a data-overlay="contactOverlay">Contact</a>
  <a data-overlay="categoryOverlay">Menu</a>
  <a href="https://goodeats.io/helensgreek" target="_blank">Order Now</a>
</div>

<section id="home-buttons" style="text-align:center; margin-top:50px;">
  <a id="menuBtnHome" class="order-button" data-overlay="categoryOverlay">Menu</a>
  <a href="https://goodeats.io/helensgreek" class="order-button" target="_blank">Order Now</a>
</section>

<!-- CATEGORY SELECTOR OVERLAY -->
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

<!-- MENU OVERLAYS -->
<div id="startersOverlay" class="overlay">
  <span class="close-btn" data-close="startersOverlay">&times;</span>
  <h2>Starters for the Gods</h2>
  <!-- Add your starter items here -->
</div>

<div id="wrapsOverlay" class="overlay">
  <span class="close-btn" data-close="wrapsOverlay">&times;</span>
  <h2>Wraps for the Gods (Pita Gyros)</h2>
  <!-- Add your wrap items here -->
</div>

<div id="plattersOverlay" class="overlay">
  <span class="close-btn" data-close="plattersOverlay">&times;</span>
  <h2>Greek Me Baby One More Time (Platters)</h2>
  <!-- Add your platter items here -->
</div>

<div id="questsOverlay" class="overlay">
  <span class="close-btn" data-close="questsOverlay">&times;</span>
  <h2>The Greek Quests</h2>
  <!-- Add your quest items here -->
</div>

<div id="sweetOverlay" class="overlay">
  <span class="close-btn" data-close="sweetOverlay">&times;</span>
  <h2>Sweet Treats</h2>
  <!-- Add your sweet items here -->
</div>

<div id="aboutOverlay" class="overlay">
  <span class="close-btn" data-close="aboutOverlay">&times;</span>
  <h2>About</h2>
  <p>Helen's Greek Kitchen – Three Cups Pub ...</p>
</div>

<div id="allergensOverlay" class="overlay">
  <span class="close-btn" data-close="allergensOverlay">&times;</span>
  <h2>Allergens</h2>
  <ul>
    <li>Gluten</li><li>Crustaceans</li><li>Eggs</li><li>Fish</li><li>Peanuts</li>
    <li>Soybeans</li><li>Milk</li><li>Nuts</li><li>Celery</li><li>Mustard</li>
    <li>Sesame seeds</li><li>Sulphur dioxide and sulphites</li><li>Lupin</li><li>Molluscs</li>
  </ul>
</div>

<div id="contactOverlay" class="overlay">
  <span class="close-btn" data-close="contactOverlay">&times;</span>
  <h2>Contact</h2>
  <p>Email: helen@helenskitchen.uk</p>
  <p>Three Cups Pub, MK403JR, Bedford 45 Newnham St</p>
</div>

<footer>
  &copy; 2025 Helen's Greek Kitchen. All rights reserved. Designed by Miska.
</footer>

<script>
  // Hamburger toggle
  const hamburger = document.querySelector('.hamburger');
  const mobileNav = document.querySelector('.mobile-nav');
  hamburger.addEventListener('click', () => {
    mobileNav.style.display = mobileNav.style.display === 'flex' ? 'none' : 'flex';
  });

  // Open overlay buttons
  document.querySelectorAll('[data-overlay]').forEach(btn => {
    btn.addEventListener('click', () => {
      const target = btn.getAttribute('data-overlay');
      document.getElementById(target).style.display = 'block';
      if(mobileNav) mobileNav.style.display = 'none';
    });
  });

  // Close buttons
  document.querySelectorAll('.close-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      const target = btn.getAttribute('data-close');
      document.getElementById(target).style.display = 'none';
    });
  });

  // Close when clicking outside overlay content
  window.addEventListener('click', (e) => {
    if (e.target.classList.contains('overlay')) {
      e.target.style.display = 'none';
    }
  });
</script>
</body>
</html>
