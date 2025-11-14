<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Helen's Greek Kitchen</title>
<style>
  body {
    font-family: 'Trebuchet MS', sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f8ff;
    color: #2e2b2b;
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
    background-color: #1f618d;
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
    color: #1f618d;
    margin-top: 30px;
    border-bottom: 2px solid #1f618d;
    padding-bottom: 5px;
  }

  .menu-item {
    margin-bottom: 20px;
    padding: 15px;
    border-left: 5px solid #1f618d;
    background-color: #e6f2ff;
    border-radius: 8px;
  }

  .menu-item h3 {
    margin: 0 0 5px 0;
    font-size: 1.3em;
    color: #2874a6;
  }

  .menu-item p {
    margin: 0;
  }

  .menu-item .price {
    font-weight: bold;
    margin-top: 5px;
    color: #1f618d;
  }

  .allergen-list {
    list-style-type: disc;
    padding-left: 20px;
    margin: 10px 0;
  }

  .order-button {
    display:inline-flex;
    align-items:center;
    justify-content:center;
    background-color:#2874a6;
    color:white;
    padding:18px 35px;
    border-radius:50px;
    text-decoration:none;
    font-weight:bold;
    font-size:1.4em;
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    transition: background 0.3s, transform 0.2s, box-shadow 0.3s;
    margin:20px 0;
  }

  .order-button i {
    margin-right:10px;
    font-size:1.2em;
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

  @media (max-width: 600px) {
    nav a {
      padding: 10px;
      font-size: 0.9em;
    }
    header img {
      max-height: 250px;
    }
    .order-button {
      font-size:1.2em;
      padding: 15px 25px;
    }
  }
</style>
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
</head>
<body>

<header>
  <img src="header2.png" alt="Helen's Greek Kitchen Banner">
</header>

<nav>
  <a href="#about">About</a>
  <a href="#menu">Menu</a>
  <a href="#contact">Contact</a>
  <a href="#allergens">Allergens</a>
</nav>

<section id="about">
  <h2>About</h2>
  <p>
    Helen's Greek Kitchen – Three Cups Pub<br>
    Welcome to Helen’s Greek Kitchen at The Three Cups Pub — where the charm of a classic English pub meets the fiery heart of Greek cooking. Helen brings her passion straight from the islands — bold flavours, no shortcuts, and a little bit of drama in every dish. From moussaka and spanakopita to perfectly grilled souvlaki and creamy tzatziki, every bite tells a story — one that usually ends with “just one more plate.”<br><br>
    The Three Cups keeps the drinks flowing — crisp pints, fine wines, and the occasional cheeky ouzo. It’s the best of both worlds: a British pub with a Greek soul.<br><br>
    Whether you’re here for a quiet pint, a lively dinner, or to argue over who makes the best baklava, you’ll always find good food, good company, and a warm welcome.<br><br>
    <strong>Order from 15:00 to 22:00</strong><br>
    Greek + Mediterranean + Hot food<br>
    Collection + Table orders<br>
    Order from Table QR Code
  </p>
  <a href="https://goodeats.io/helensgreek" class="order-button" target="_blank">
    <i class="fas fa-utensils"></i> Order Now
  </a>
</section>

<section id="menu">
  <h2>STARTERS FOR THE GODS</h2>
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
    <p>Fresh, Crunchy and very Athenian-approved. Authentic Greek Salad with fresh tomatoes, cucumber, bell pepper, onions, olives, extra virgin olive-oil and oregano.</p>
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
    <p>Simple. Classic. Eternal. Athena’s proudest invention. Respect the Olive!</p>
  </div>

  <!-- WRAPS FOR THE GODS -->
  <h2>WRAPS FOR THE GODS (PITA GYROS)</h2>
  <p>All served in fluffy Greek pita with salad, fries & sauce. Don't ask for ketchup – we're not a chip shop.</p>

  <div class="menu-item">
    <h3>Pork Gyros</h3>
    <p>Juicy, smoky, and 100% approved by the intellectual Athenians. Served with fries, tomatoes, onions, and Tzatziki.</p>
  </div>

  <div class="menu-item">
    <h3>Chicken Gyros</h3>
    <p>Tastes like a Greek summer, desired by ancient Spartan warriors. Served with fries, tomatoes, onions, and Tzatziki.</p>
  </div>

  <div class="menu-item">
    <h3>Pork Souvlaki</h3>
    <p>Tender pork, kissed by fire and Greek spices, wrapped in fluffy pita glory. Served with fries, salad, and our divine sauce.</p>
  </div>

  <div class="menu-item">
    <h3>Chicken Souvlaki</h3>
    <p>Succulent chicken, marinated like a Spartan's secret weapon, grilled to perfection. Wrapped with salad, fries, and our legendary sauce.</p>
  </div>

  <div class="menu-item">
    <h3>Kebab Souvlaki</h3>
    <p>All the juicy, grilled goodness of our kebab, wrapped tighter than Athena’s helmet. Sweet red peppers and our secret “ambrosia-inspired” sauce create a Greek miracle in every mouthful.</p>
  </div>

  <div class="menu-item">
    <h3>Greek Sausage</h3>
    <p>Bold, flavorful, and full of street-smart swagger straight from the Greek agora. Herbs so good, even Dionysus would raise his goblet in approval.</p>
  </div>

  <div class="menu-item">
    <h3>Talagani Wrap</h3>
    <p>Grilled Talagani (our very own halloumi), peppers, and a drizzle of zesty lemon sauce make this a Mount Olympus-worthy delight.</p>
  </div>

  <!-- GREEK ME BABY ONE MORE TIME -->
  <h2>GREEK ME BABY ONE MORE TIME</h2>
  <p>Because you always come back for more. Don’t deny it.</p>

  <div class="menu-item">
    <h3>Pork Kalamakia</h3>
    <p>Tender pork skewers, grilled to perfection. Includes 3 juicy pork skewers, served with chips and salad.</p>
  </div>

  <div class="menu-item">
    <h3>Chicken Kalamakia</h3>
    <p>Succulent chicken skewers, marinated and flame-grilled until golden. Includes 3 chicken skewers, served with chips and salad.</p>
  </div>

  <div class="menu-item">
    <h3>Kebab Portion</h3>
    <p>Succulent, juicy, and grilled with the fire of Hephaestus himself. 3 juicy kebabs served with fries and salad.</p>
  </div>

  <div class="menu-item">
    <h3>Mixed Gyros</h3>
    <p>The ultimate gyro adventure: a little chicken, a little pork, a lot of deliciousness. Served with fries, pittas, bread, and salad.</p>
  </div>

  <div class="menu-item">
    <h3>Sausage Platter</h3>
    <p>A heroic lineup of sausages, grilled to perfection. Served with fries and salad.</p>
  </div>

  <div class="menu-item">
    <h3>Vegetarian Platter</h3>
    <p>Talagani, peppers served with fries and salad – a garden party straight from Mount Olympus.</p>
  </div>

  <div class="menu-item">
    <h3>Mixed Grill Platter</h3>
    <p>A little bit of everything for the indecisive Greek legend. Feeds 2-3 fully grown Greeks.</p>
  </div>

  <!-- THE GREEK QUESTS -->
  <h2>THE GREEK QUESTS</h2>
  <div class="menu-item">
    <h3>Bifteki</h3>
    <p>Juicy Greek-style beef patties filled with herbs and maybe a secret or two from Mount Parnassus. Potatoes accompany.</p>
  </div>

  <div class="menu-item">
    <h3>Briam</h3>
    <p>Vibrant medley of baked vegetables, olive oil, and herbs. Served with fries.</p>
  </div>

  <div class="menu-item">
    <h3>Gemista</h3>
    <p>Peppers and tomatoes stuffed with herby rice and good vibes only. Served with fries.</p>
  </div>

  <div class="menu-item">
    <h3>Giouvesti</h3>
    <p>Tender chicken baked with orzo, tomato, and a hint of cinnamon. Comes with fries.</p>
  </div>

  <div class="menu-item">
    <h3>Kleftiko</h3>
    <p>Lamb so tender it practically sings of Greek islands and olive groves. Served with roast potatoes.</p>
  </div>

  <div class="menu-item">
    <h3>Lemon Chicken</h3>
    <p>Tender chicken baked in zesty lemon sauce. Fries on the side.</p>
  </div>

  <div class="menu-item">
    <h3>Mousakas</h3>
    <p>Layers of aubergine, spiced mince, and creamy béchamel baked golden.</p>
  </div>

  <div class="menu-item">
    <h3>Paboutskia</h3>
    <p>Stuffed aubergines overflowing with spiced mince and sunshine.</p>
  </div>

  <div class="menu-item">
  <h3>Pastitsio</h3>
 <p>Pasta, spiced mince, and luscious béchamel in perfect harmony.</p>
  </div>

  <div class="menu-item">
    <h3>Plaki Fish</h3>
    <p>Oven-baked fish with tomatoes, onions, olives, and herbs. Fries on the side.</p>
  </div>

  <div class="menu-item">
    <h3>Red Chicken</h3>
    <p>Tender chicken simmered in rich tomato sauce kissed by the sun. Fries on the side.</p>
  </div>

  <div class="menu-item">
    <h3>Stifado</h3>
    <p>Slow-cooked beef with sweet onions and romantic spices. Fries accompany.</p>
  </div>

  <!-- SWEET TREATS -->
  <h2>SWEET TREATS</h2>

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

</section>

<section id="contact">
  <h2>Contact</h2>
  <p>Email: info@helenskitchen.uk</p>
  <p>Address: 45 Newnham St, Bedford MK40 3JR</p>
</section>

<section id="allergens">
  <h2>Allergens</h2>
  <p>At Helen's Greek Kitchen, we use traditional Greek ingredients and family recipes. Please let us know if you have any food allergies or dietary requirements.</p>
  <ul class="allergen-list">
    <li>Dairy (milk, cheese, yoghurt)</li>
    <li>Gluten (wheat, barley, bread, pita, pastry)</li>
    <li>Nuts (almonds, walnuts, pistachios)</li>
    <li>Shellfish (prawns, mussels, calamari)</li>
    <li>Eggs</li>
    <li>Sesame (tahini, seeds, bread toppings)</li>
    <li>Soy</li>
    <li>Mustard</li>
    <li>Sulphites (in dressings and wines)</li>
  </ul>
  <p>We take care to avoid cross-contamination but cannot guarantee any dish is completely allergen-free. Please ask our team for advice. Efharisto!</p>
</section>

<footer>
  <p>© Helen's Greek Kitchen. All rights reserved. Designed by Miska.</p> 
</footer>

</body>
</html>
