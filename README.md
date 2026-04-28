
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">


<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;500;700&display=swap" rel="stylesheet">

<style>
body {
  font-family: 'Inter', sans-serif;
  margin: 0;
  background: #f7f7f7;
  color: #333; 
}

/* HEADER */
header {
  background: #111;
  color: white;
  padding: 20px;
  text-align: center;
}

/* HERO */
.hero {
  padding: 60px 20px;
  text-align: center;
  background: white;
}

.hero h1 {
  font-size: 2.5rem;
  margin-bottom: 10px;
}

.hero p {
  color: #666;
}

/* SERVICES GRID */
.services {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 25px;
  padding: 40px;
  max-width: 1100px;
  margin: auto;
}

/* CARD */
.card {
  background: white;
  border-radius: 14px;
  overflow: hidden;
  box-shadow: 0 6px 20px rgba(0,0,0,0.08);
  display: flex;
  flex-direction: column;
  transition: transform 0.2s ease;
}

.card:hover {
  transform: translateY(-5px);
}

.card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

/* CARD CONTENT */
.card-content {
  padding: 15px 18px;
  flex-grow: 1;
}

.card h3 {
  margin: 0 0 10px;
}

.card p {
  margin: 0;
  line-height: 1.6;
  color: #555;
}

/* BUTTON */
.card button {
  margin: 15px;
  padding: 12px;
  border: none;
  background: #111;
  color: white;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 500;
  transition: background 0.2s ease;
}

.card button:hover {
  background: #333;
}

/* SECTION */
.section {
  padding: 50px 20px;
  text-align: center;
  background: white;
}

.section h2 {
  margin-bottom: 20px;
}

/* FOOTER */
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
    <img src="https://images.unsplash.com/photo-1690068023694-053da714f95f?w=1000&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8Z3Jhc3MlMjBjdXR0aW5nfGVufDB8fDB8fHww">
    <div class="card-content">
      <h3>Yard Work</h3>
      <p>
        Small yard: $40–$60<br>
        Medium yard: $75–$125<br>
        Large yard: $150+
      </p>
    </div>
    <button onclick="book()">Book Appointment</button>
  </div>

  <div class="card">
    <img src="https://images.unsplash.com/photo-1581578731548-c64695cc6952">
    <div class="card-content">
      <h3>House Cleaning</h3>
      <p>
        Small home: $60–$100<br>
        Medium: $100–$150<br>
        Large: $150+
      </p>
    </div>
    <button onclick="book()">Book Appointment</button>
  </div>

  <div class="card">
    <img src="https://media.istockphoto.com/id/1490490821/photo/male-janitor-in-uniform-cleans-a-trash-can-in-the-street.jpg?s=612x612&w=0&k=20&c=B-FDD1DgM7eGff9XAF1rjBOFKtAZsrtGx3M5oTVnP8Y=">
    <div class="card-content">
      <h3>Junk Removal</h3>
      <p>
        Small load: $80–$150<br>
        Medium: $150–$300<br>
        Large: $300+
      </p>
    </div>
    <button onclick="book()">Book Appointment</button>
  </div>

  <div class="card">
    <img src="https://imgs.search.brave.com/qE4y-o01hk3Ln8WCLrDHGB1KZoDDREKTMu6OQ8mNOHA/rs:fit:500:0:1:0/g:ce/aHR0cHM6Ly9zdC5k/ZXBvc2l0cGhvdG9z/LmNvbS8xMDM3OTg3/LzQ4MzAvaS80NTAv/ZGVwb3NpdHBob3Rv/c180ODMwNTA1My1z/dG9jay1waG90by1t/YW4tY2Fycnlpbmct/c29mYS5qcGc">
    <div class="card-content">
      <h3>Moving Help</h3>
      <p>
        Small home: $150–$200<br>
        Medium: $200–$250<br>
        Large: $300+
      </p>
    </div>
    <button onclick="book()">Book Appointment</button>
  </div>

</section>

<section class="section">
  <h2>Schedule an Appointment</h2>

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
