# Bull-Spanners
<!DOCTYPE html>
<html lang="en">
<meta name="google-site-verification" content="5T1j0ZYQdES2-4jim-IJIDImGD_VkE6zBhQwoniwL0k" />
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bull Spanners Garage</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #f9f9f9;
      color: #333;
      overflow-x: hidden;
    }

    /* Floating spanners background */
    .spanner-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      overflow: hidden;
    }

    .spanner {
      position: absolute;
      width: 40px;
      height: 40px;
      background-image: url('https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Wrench_icon.svg/512px-Wrench_icon.svg.png');
      background-size: contain;
      background-repeat: no-repeat;
      opacity: 0.05;
      animation: floatSpanner 30s linear infinite;
    }

    @keyframes floatSpanner {
      0% { transform: translateY(100vh) rotate(0deg); }
      100% { transform: translateY(-100vh) rotate(360deg); }
    }

    header {
      background: linear-gradient(to right, #990000, #333);
      color: white;
      padding: 30px;
      text-align: center;
    }

    nav {
      background: #222;
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
    }

    nav a {
      color: white;
      padding: 15px 20px;
      text-decoration: none;
      font-weight: bold;
      transition: background 0.3s;
    }

    nav a:hover {
      background: #990000;
    }

    section {
      padding: 40px 20px;
      max-width: 1000px;
      margin: auto;
    }

    h2 {
      color: #990000;
      margin-bottom: 10px;
    }

    ul {
      list-style: none;
      padding: 0;
    }

    ul li {
      background: #eee;
      margin: 5px 0;
      padding: 10px;
      border-left: 5px solid #990000;
    }

    .booking-form input, .booking-form textarea {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .booking-form button {
      background: #990000;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }

    .booking-form button:hover {
      background: #cc0000;
    }

    .gallery img {
      width: 100%;
      max-width: 300px;
      margin: 10px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }

    footer {
      background: #222;
      color: white;
      text-align: center;
      padding: 20px;
    }
  </style>
</head>
<body>
  <!-- Floating Spanners -->
  <div class="spanner-bg">
    <div class="spanner" style="left: 10%; animation-delay: 0s;"></div>
    <div class="spanner" style="left: 30%; animation-delay: 5s;"></div>
    <div class="spanner" style="left: 50%; animation-delay: 10s;"></div>
    <div class="spanner" style="left: 70%; animation-delay: 15s;"></div>
    <div class="spanner" style="left: 90%; animation-delay: 20s;"></div>
  </div>

  <header>
    <h1>Bull Spanners Garage</h1>
    <p>Nyeri, Mukurweini — 100m from Wakulima Dairy</p>
    <p>📞 Call/WhatsApp: 0723390348</p>
  </header>

  <nav>
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#booking">Book Now</a>
    <a href="#gallery">Gallery</a>
    <a href="#contact">Contact</a>
  </nav>

  <section id="about">
    <h2>About Us</h2>
    <p>We’re Mukurweini’s trusted garage, offering expert car care with a personal touch. From diagnostics to bodywork, we deliver quality, speed, and honesty.</p>
  </section>

  <section id="services">
    <h2>Our Services</h2>
    <ul>
      <li>Engine Diagnostics & Repair</li>
      <li>Brake & Suspension Work</li>
      <li>Bodywork & Painting</li>
      <li>Tyre Replacement & Balancing</li>
      <li>Routine Maintenance</li>
    </ul>
  </section>

  <section id="booking">
    <h2>Book an Appointment</h2>
    <form class="booking-form" onsubmit="sendToWhatsApp(); return false;">
      <input type="text" id="name" placeholder="Your Name" required />
      <input type="tel" id="phone" placeholder="Phone Number" required />
      <input type="date" id="date" required />
      <textarea id="issue" placeholder="Describe your issue..." rows="4" required></textarea>
      <button type="submit">Submit Booking</button>
    </form>
  </section>

  <section id="gallery" class="gallery">
    <h2>Garage Gallery</h2>
    <p>Upload your own pictures or replace these:</p>
    <img src="https://via.placeholder.com/300x200?text=Garage+1" alt="Garage 1" />
    <img src="https://via.placeholder.com/300x200?text=Garage+2" alt="Garage 2" />
    <img src="https://via.placeholder.com/300x200?text=Garage+3" alt="Garage 3" />
  </section>

  <section id="contact">
    <h2>Contact Us</h2>
    <p>📍 Nyeri, Mukurweini — 100m from Wakulima Dairy</p>
    <p>📞 <a href="tel:+254723390348">0723390348</a></p>
    <p>📧 Email: bullspanners@example.com</p>
  </section>

  <footer>
    <p>&copy; 2025 Bull Spanners Garage. All rights reserved.</p>
  </footer>

  <script>
    function sendToWhatsApp() {
      const name = document.getElementById("name").value.trim();
      const phone = document.getElementById("phone").value.trim();
      const date = document.getElementById("date").value;
      const issue = document.getElementById("issue").value.trim();

      const message = `Hello Bull Spanners Garage,%0A%0A*Booking Request*%0AName: ${name}%0APhone: ${phone}%0ADate: ${date}%0AIssue: ${issue}%0A%0AThanks!`;
      const whatsappURL = `https://wa.me/254723390348?text=${message}`;

      window.open(whatsappURL, "_blank");
    }
  </script>
</body>
</html>
