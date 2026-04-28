
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Banks General Labor</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;500;700&display=swap" rel="stylesheet">

<style>
body {
  font-family: 'Inter', sans-serif;
  margin: 0;
  background: #f7f7f7;
  color: #333;
}

header {
  background: #111;
  color: white;
  padding: 20px;
  text-align: center;
}

.hero {
  padding: 60px 20px;
  text-align: center;
  background: white;
}

.hero h1 {
  font-size: 2.5rem;
}

.services {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  padding: 40px;
}

.card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
}

.card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.card h3 {
  padding: 10px;
}

.card p {
  padding: 10px;
}

.card button {
  margin: 10px;
  padding: 10px;
  border: none;
  background: black;
  color: white;
  border-radius: 6px;
  cursor: pointer;
}

.section {
  padding: 50px 20px;
  text-align: center;
}

footer {
  text-align: center;
  padding: 20px;
  background: #111;
  color: white;
}
</style>
</head>

<body>

<header>
  <h2>Banks General Labor Services</h2>
</header>

<section class="hero">
  <h1>Reliable Help When You Need It</h1>
  <p>Yard Work • Cleaning • Moving • Junk Removal</p>
</section>

<section class="services">

  <div class="card">
    <img src="https://images.unsplash.com/photo-1598514983318-2f64f8f4796c">
    <h3>Yard Work</h3>
    <p>
     Small yard: $40–$60<br>
     Medium yard: $75–$125<br>
     Large yard: $150+
   </p>
    <button onclick="book()">Book</button>
    
  </div>

  <div class="card">
    <img src="https://images.unsplash.com/photo-1581578731548-c64695cc6952">
    <h3>House Cleaning</h3>
    <p>
      Small home: $60–$100<br>
      Medium: $100–$150<br>
      Large: $150+
   </p>
    <button onclick="book()">Book</button>
    
  </div>

  <div class="card">
    <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c">
    <h3>Junk Removal</h3>
    Small load: $80–$150<br>
    Medium: $150–$300<br>
    Large: $300+
    <button onclick="book()">Book</button>
    
  </div>

  <div class="card">
    <img src="https://images.unsplash.com/photo-1604147706283-d7119b5b822c">
    <h3>Moving Help</h3>
    Small home: $150–$200<br>
      Medium: $200–$250<br>
      Large: $300+
    <button onclick="book()">Book</button>
    
  </div>

</section>

<section class="section">
  <h2>Schedule an Appointment</h2>

  <!-- Calendly Embed -->
  <div class="calendly-inline-widget"
    data-url="https://calendly.com/salreeves00/new-meeting"
    style="min-width:320px;height:700px;">
  </div>

  <script src="https://assets.calendly.com/assets/external/widget.js"></script>
</section>

<footer>
  <p>© 2026 Banks General Labor</p>
</footer>

<script>
function book() {
  document.querySelector('.section').scrollIntoView({ behavior: 'smooth' });
}

async function pay(amount) {
  const res = await fetch("https://Banks-labor-backend.onrender.com/create-checkout-session", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ amount })
  });

  const data = await res.json();
  window.location = data.url;
}
</script>

</body>
</html>
