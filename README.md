<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dwarkesh Cafe</title>
  <meta name="description" content="Dwarkesh Cafe in Vapi — premium hot beverages, bakery, cakes, fast food, dine-in, takeaway, and reservations." />
  <style>
    :root{
      --bg:#f8f1ec;
      --panel:#fffdfb;
      --primary:#3d2b24;
      --primary-2:#5a3d34;
      --accent:#d49b68;
      --accent-2:#f0d3a9;
      --text:#2b211e;
      --muted:#665d5a;
      --line: rgba(61,43,36,0.12);
      --shadow:0 18px 45px rgba(40,28,22,0.12);
      --radius:20px;
    }

    *{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      font-family: Arial, Helvetica, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height:1.6;
    }
    img{max-width:100%; display:block}
    a{text-decoration:none; color:inherit}
    .container{
      width:min(100% - 20px, 1100px);
      margin:0 auto;
    }

    header{
      position:sticky;
      top:0;
      z-index:1000;
      background: rgba(248,241,236,0.9);
      backdrop-filter: blur(8px);
      border-bottom:1px solid var(--line);
    }
    .nav{
      display:flex;
      justify-content:space-between;
      align-items:center;
      min-height:72px;
      gap:12px;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:8px;
      font-weight:800;
      font-size:0.8rem;
      letter-spacing:0.08em;
      text-transform:uppercase;
      color:var(--primary);
    }
    .brand-mark{
      width:36px;height:36px;border-radius:50%;
      display:grid;place-items:center;
      background:linear-gradient(135deg, var(--accent), var(--accent-2));
      color:#fff;
      font-weight:800;
      box-shadow:var(--shadow);
    }
    .menu-btn{
      background: var(--primary);
      color:#fff;
      border:none;
      border-radius:999px;
      padding:11px 16px;
      font-weight:700;
      font-size:0.8rem;
    }

    .hero{
      background:
        linear-gradient(90deg, rgba(22,16,13,0.72), rgba(22,16,13,0.42)),
        url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=1200&q=80') center/cover no-repeat;
      min-height:560px;
      display:flex;
      align-items:flex-end;
      padding:24px 0 36px;
      color:#fff;
    }
    .hero-box{
      background: rgba(0,0,0,0.1);
      border-radius:20px;
      padding:14px 14px 18px;
    }
    .eyebrow{
      display:inline-block;
      font-size:0.68rem;
      letter-spacing:0.14em;
      text-transform:uppercase;
      background: rgba(255,255,255,0.14);
      border:1px solid rgba(255,255,255,0.15);
      border-radius:999px;
      padding:7px 12px;
      margin-bottom:12px;
      font-weight:700;
    }
    h1{
      font-size: clamp(2.2rem, 8vw, 4rem);
      line-height:0.95;
      margin-bottom:12px;
      color:#fff;
    }
    .hero p{
      color: rgba(255,255,255,0.84);
      font-size:0.96rem;
      margin-bottom:18px;
    }
    .cta-row{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-bottom:18px;
    }
    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      border:none;
      border-radius:999px;
      padding:14px 18px;
      font-weight:800;
      font-size:0.88rem;
      cursor:pointer;
    }
    .btn.primary{
      background: var(--primary);
      color:#fff;
    }
    .btn.secondary{
      background: transparent;
      border:1px solid rgba(255,255,255,0.24);
      color:#fff;
    }

    .stats{
      display:grid;
      grid-template-columns:repeat(2, minmax(0, 1fr));
      gap:12px;
      margin-top:8px;
    }
    .stat{
      background: rgba(255,255,255,0.08);
      border:1px solid rgba(255,255,255,0.14);
      border-radius:16px;
      padding:12px 12px 10px;
      text-align:center;
    }
    .stat strong{
      display:block;
      font-size:1.3rem;
      margin-bottom:4px;
      color:#fff;
    }
    .stat span{
      display:block;
      font-size:0.68rem;
      letter-spacing:0.08em;
      text-transform:uppercase;
      color: rgba(255,255,255,0.72);
    }

    section{
      padding:68px 0;
    }
    h2{
      font-size: clamp(1.8rem, 7vw, 2.6rem);
      color: var(--primary);
      margin-bottom:12px;
      line-height:1.1;
    }
    .section-tag{
      display:inline-block;
      font-size:0.68rem;
      letter-spacing:0.12em;
      text-transform:uppercase;
      color: var(--primary-2);
      background: rgba(212,155,104,0.12);
      border:1px solid rgba(61,43,36,0.1);
      border-radius:999px;
      padding:7px 12px;
      margin-bottom:12px;
      font-weight:700;
    }
    p.lead{
      color: var(--muted);
      margin-bottom:20px;
      font-size:0.98rem;
    }

    .feature-card, .service-card, .menu-card, .reservation-card{
      background: var(--panel);
      border:1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }

    .feature-card{
      padding:22px 18px;
      margin-bottom:16px;
    }
    .icon{
      width:52px;height:52px;border-radius:16px;
      display:grid;place-items:center;
      background: linear-gradient(135deg, rgba(212,155,104,0.18), rgba(240,211,169,0.38));
      font-size:1.5rem;
      margin-bottom:12px;
    }
    .feature-card h3{
      margin-bottom:8px;
      color: var(--primary);
      font-size:1.2rem;
    }
    .feature-card p{
      color: var(--muted);
      font-size:0.94rem;
    }

    .menu-card{
      overflow:hidden;
      margin-bottom:18px;
    }
    .menu-card img{
      width:100%;
      height:220px;
      object-fit:cover;
    }
    .menu-body{
      padding:18px 16px 20px;
    }
    .menu-head{
      display:flex; justify-content:space-between; align-items:center; gap:12px; margin-bottom:8px;
    }
    .menu-head h3{
      font-size:1.2rem;
      color: var(--primary);
    }
    .price{
      color:var(--accent);
      font-weight:800;
      font-size:1rem;
    }
    .menu-body p{
      color: var(--muted);
      margin-bottom:12px;
      font-size:0.93rem;
    }
    .menu-tag{
      display:inline-block;
      background: rgba(212,155,104,0.12);
      color: var(--primary);
      font-size:0.68rem;
      font-weight:700;
      letter-spacing:0.06em;
      text-transform:uppercase;
      border-radius:999px;
      padding:7px 10px;
    }

    .about-wrap{
      display:grid;
      gap:18px;
    }
    .about-photo img{
      width:100%;
      height:300px;
      object-fit:cover;
      border-radius:26px;
      box-shadow: var(--shadow);
    }
    .check-list{
      list-style:none;
      display:grid;
      gap:12px;
      margin-top:16px;
    }
    .check-list li{
      display:flex; align-items:center; gap:10px; font-weight:700; color:var(--primary);
    }
    .check{
      width:24px;height:24px;border-radius:50%;
      background: rgba(61,43,36,0.08);
      display:grid;place-items:center; color:var(--primary); font-size:0.9rem;
    }

    .service-card{
      padding:20px 16px;
      margin-bottom:14px;
      text-align:center;
    }
    .service-card .icon{
      margin:0 auto 12px;
    }
    .service-card h3{
      color: var(--primary);
      font-size:1.1rem;
      margin-bottom:8px;
    }
    .service-card p{
      color: var(--muted);
      font-size:0.9rem;
    }

    .gallery-grid{
      display:grid;
      gap:12px;
    }
    .gallery-grid img{
      width:100%;
      height:180px;
      object-fit:cover;
      border-radius:18px;
      box-shadow:var(--shadow);
    }

    .reservation-card{
      padding:18px 16px;
    }
    form{
      display:grid;
      gap:12px;
    }
    .field{
      display:grid;
      gap:6px;
    }
    label{
      color: var(--primary);
      font-size:0.8rem;
      font-weight:700;
    }
    input, select, textarea{
      width:100%;
      border:1px solid rgba(61,43,36,0.12);
      background: #fffdfa;
      border-radius:12px;
      padding:12px 14px;
      font:inherit;
      color:var(--text);
      resize:vertical;
    }
    .btn.full{
      width:100%;
    }

    footer{
      background: var(--primary);
      color:#f7efe9;
      padding:32px 0;
    }
    .footer-box{
      display:flex;
      flex-direction:column;
      gap:14px;
      align-items:flex-start;
    }
    .footer-links{
      display:flex; gap:12px; flex-wrap:wrap; color: rgba(247,239,233,0.8);
      font-size:0.85rem;
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">
        <span class="brand-mark">D</span>
        <span>Dwarkesh</span>
      </div>
      <button class="menu-btn">Book</button>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="container hero-box">
        <div class="eyebrow">Luxury • Cozy • Authentic</div>
        <h1>Drink, dine, and unwind.</h1>
        <p>Premium hot beverages, bakery delights, cakes, and fast food in the heart of Vapi.</p>

        <div class="cta-row">
          <a href="#menu" class="btn primary">Menu</a>
          <a href="#reservation" class="btn secondary">Reserve</a>
        </div>

        <div class="stats">
          <div class="stat">
            <strong>Bakery</strong>
            <span>Fresh</span>
          </div>
          <div class="stat">
            <strong>Hot</strong>
            <span>Beverages</span>
          </div>
          <div class="stat">
            <strong>Dine</strong>
            <span>In</span>
          </div>
          <div class="stat">
            <strong>Fast</strong>
            <span>Food</span>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-tag">Why choose us</div>
        <h2>A cozy luxury cafe experience.</h2>
        <p class="lead">Dwarkesh Cafe brings stylish comfort, delicious flavors, and warm hospitality to Vapi.</p>

        <div class="feature-card">
          <div class="icon">☕</div>
          <h3>Premium brews</h3>
          <p>Rich coffee, cappuccino, and hot beverages made for cozy moments and quick energy boosts.</p>
        </div>

        <div class="feature-card">
          <div class="icon">🥐</div>
          <h3>Bakery delights</h3>
          <p>Fresh cookies, cakes, pastries, and sweet bites to complete every visit.</p>
        </div>

        <div class="feature-card">
          <div class="icon">🍽️</div>
          <h3>Fast food & dine-in</h3>
          <p>Enjoy calm dining, quick takeaway, and satisfying comfort food whenever you crave it.</p>
        </div>
      </div>
    </section>

    <section id="menu">
      <div class="container">
        <div class="section-tag">Our menu</div>
        <h2>Popular picks</h2>

        <div class="menu-card">
          <img src="https://images.unsplash.com/photo-1497636577773-f1231844b336?auto=format&fit=crop&w=900&q=80" alt="Cappuccino" />
          <div class="menu-body">
            <div class="menu-head">
              <h3>Classic Cappuccino</h3>
              <span class="price">₹180</span>
            </div>
            <p>Silky espresso with creamy foam and a rich finish.</p>
            <span class="menu-tag">Hot beverage</span>
          </div>
        </div>

        <div class="menu-card">
          <img src="https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=900&q=80" alt="Brownie" />
          <div class="menu-body">
            <div class="menu-head">
              <h3>Chocolate Brownie</h3>
              <span class="price">₹140</span>
            </div>
            <p>Fudgy, warm, and perfect with your coffee.</p>
            <span class="menu-tag">Bakery</span>
          </div>
        </div>

        <div class="menu-card">
          <img src="https://images.unsplash.com/photo-1525351484163-7529414344d8?auto=format&fit=crop&w=900&q=80" alt="Sandwich" />
          <div class="menu-body">
            <div class="menu-head">
              <h3>Cheese Sandwich</h3>
              <span class="price">₹220</span>
            </div>
            <p>Perfectly grilled and satisfying for a quick bite.</p>
            <span class="menu-tag">Fast food</span>
          </div>
        </div>
      </div>
    </section>

    <section>
      <div class="container about-wrap">
        <div>
          <div class="section-tag">About us</div>
          <h2>Comfort meets elegance.</h2>
          <p class="lead">Dwarkesh Cafe blends cozy ambiance with premium coffee culture and a welcoming neighborhood vibe.</p>
        </div>

        <div class="about-photo">
          <img src="https://images.unsplash.com/photo-1554118811-1e0d58224f24?auto=format&fit=crop&w=900&q=80" alt="Cafe interior" />
        </div>

        <ul class="check-list">
          <li><span class="check">✓</span> Aesthetic cozy ambience</li>
          <li><span class="check">✓</span> Dine-in and takeaway</li>
          <li><span class="check">✓</span> Bakery, cakes, and hot drinks</li>
        </ul>
      </div>
    </section>

    <section id="services">
      <div class="container">
        <div class="section-tag">Services</div>
        <h2>Easy ways to enjoy us</h2>

        <div class="service-card">
          <div class="icon">🛍️</div>
          <h3>Takeaway</h3>
          <p>Quick coffee and bites on the go.</p>
        </div>

        <div class="service-card">
          <div class="icon">🍽️</div>
          <h3>Dine In</h3>
          <p>Comfortable seating and warm ambience.</p>
        </div>

        <div class="service-card">
          <div class="icon">📦</div>
          <h3>Order</h3>
          <p>Available whenever you want your favorites.</p>
        </div>

        <div class="service-card">
          <div class="icon">🪑</div>
          <h3>Reservations</h3>
          <p>Celebrate, catch up, or simply relax.</p>
        </div>
      </div>
    </section>

    <section id="gallery">
      <div class="container">
        <div class="section-tag">Gallery</div>
        <h2>Looks like home</h2>

        <div class="gallery-grid">
          <img src="https://images.unsplash.com/photo-1442512595331-e89e73853f31?auto=format&fit=crop&w=900&q=80" alt="Cafe display" />
          <img src="https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?auto=format&fit=crop&w=900&q=80" alt="Coffee pour" />
          <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348?auto=format&fit=crop&w=900&q=80" alt="Cafe seating" />
          <img src="https://images.unsplash.com/photo-1466978913421-dad2ebd01d17?auto=format&fit=crop&w=900&q=80" alt="Bakery and coffee" />
        </div>
      </div>
    </section>

    <section id="reservation">
      <div class="container">
        <div class="section-tag">Reserve</div>
        <h2>Book your table</h2>
        <p class="lead">Choose dine-in, takeaway, or reservations. We’d love to host you.</p>

        <div class="reservation-card">
          <form>
            <div class="field">
              <label>Name</label>
              <input type="text" placeholder="Your name" />
            </div>

            <div class="field">
              <label>Phone</label>
              <input type="tel" placeholder="Your number" />
            </div>

            <div class="field">
              <label>Date</label>
              <input type="date" />
            </div>

            <div class="field">
              <label>Time</label>
              <select>
                <option>Select time</option>
                <option>9:00 AM</option>
                <option>10:30 AM</option>
                <option>12:00 PM</option>
                <option>1:30 PM</option>
                <option>3:00 PM</option>
                <option>5:30 PM</option>
                <option>7:00 PM</option>
              </select>
            </div>

            <div class="field">
              <label>Service</label>
              <select>
                <option>Select service</option>
                <option>Dine In</option>
                <option>Takeaway</option>
                <option>Order</option>
                <option>Reservation</option>
              </select>
            </div>

            <div class="field">
              <label>Notes</label>
              <textarea rows="4" placeholder="Any special request?"></textarea>
            </div>

            <button type="submit" class="btn primary full">Submit Request</button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-box">
      <div class="brand" style="color:#f7efe9;">
        <span class="brand-mark">D</span>
        <span>Dwarkesh Cafe</span>
      </div>
      <div class="footer-links">
        <a href="#about">About</a>
        <a href="#menu">Menu</a>
        <a href="#gallery">Gallery</a>
        <a href="#reservation">Reservation</a>
      </div>
      <div>© 2026 Dwarkesh Cafe</div>
    </div>
  </footer>

  <script>
    document.querySelector("form").addEventListener("submit", function(e){
      e.preventDefault();
      alert("Thank you! Your request has been received.");
      this.reset();
    });
  </script>
</body>
</html>