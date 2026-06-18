<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Lagos Airport | Professional Flight Hub + Payment Gateway</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Inter', sans-serif;
      background: #f0f4fa;
      color: #0a1c2f;
      overflow-x: hidden;
    }
    ::-webkit-scrollbar { width: 8px; }
    ::-webkit-scrollbar-track { background: #e2edf7; }
    ::-webkit-scrollbar-thumb { background: #f5a623; border-radius: 12px; }

    .navbar {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      padding: 18px 8%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(5, 15, 30, 0.96);
      backdrop-filter: blur(16px);
      z-index: 1000;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }
    .logo { 
        color: white; 
        font-size: 28px; 
        font-weight: 800; 
        letter-spacing: -0.5px; 
    }
    .logo span { 
        color: #ffb347;
     }
    .nav-links { 
        display: flex;
         gap: 32px; 
         list-style: none;
    }
    .nav-links a {
        text-decoration: none; 
        color: #f0f4fa; 
        font-weight: 600; 
        transition: 0.2s; 
    }
    .nav-links a:hover, .nav-links a.active {
         color: #ffb347; 
    }
    .menu-btn { 
        display: none; 
        color: white;
         font-size: 28px; 
         cursor: pointer; 
    }

    .hero {
      min-height: 95vh;
      background: linear-gradient(125deg, #071a2b 0%, #0a2a3f 100%), url('https://images.unsplash.com/photo-1556388158-158ea5ccacbd?q=80&w=2070&auto=format') center/cover no-repeat;
      background-blend-mode: overlay;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 140px 20px 90px;
    }
    .hero-content { 
        color: white; 
        max-width: 1200px; 
        animation: fadeUp 0.9s ease; 
    }
    .hero-content h1 { 
        font-size: 58px; 
        font-weight: 800; 
        background: linear-gradient(135deg, #fff, #ffd89a); 
        -webkit-background-clip: text; 
        background-clip: text; 
        color: transparent; 
        margin-bottom: 20px; 
    }
    .search-card {
      background: rgba(255,255,255,0.98);
      border-radius: 64px;
      padding: 32px 36px;
      margin-top: 30px;
      box-shadow: 0 30px 50px rgba(0,0,0,0.2);
    }
    .search-row {
      display: flex;
      flex-wrap: wrap;
      gap: 18px;
      justify-content: center;
    }
    .search-row select, .search-row input, .search-row button {
      padding: 15px 28px;
      border-radius: 60px;
      border: 1px solid #cbdde9;
      font-size: 1rem;
      background: white;
      min-width: 200px;
      font-weight: 500;
    }
    .search-row button {
      background: #f5a623;
      border: none;
      font-weight: 700;
      color: #0a1c2f;
      cursor: pointer;
      transition: 0.2s;
    }
    .search-row button:hover { 
        background: #e8921a; 
        transform: scale(0.98); 
    }
    .search-results {
      margin-top: 32px;
      background: #f8fafd;
      border-radius: 32px;
      padding: 24px;
      display: none;
      animation: fadeUp 0.5s;
    }
    .flight-result-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: white;
      border-radius: 28px;
      padding: 18px 28px;
      margin-bottom: 14px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.05);
      transition: 0.2s;
      flex-wrap: wrap;
    }
    .flight-detail h4 { 
        font-size: 1.25rem; 
        font-weight: 700; 
    }
    .flight-time { 
        color: #f5a623; 
        font-weight: 700; 
        margin-top: 6px; 
    }
    .book-now-btn { 
        background: #0f2b3d; 
        color: white; 
        border: none; 
        padding: 12px 30px; 
        border-radius: 40px; 
        cursor: pointer; 
        font-weight: 700; 
        transition: 0.2s; 
    }
    .book-now-btn:hover { 
        background: #f5a623; 
        color: #0a1c2f; 
    }

    .section { 
        padding: 70px 8%; 
    }
    .section h2 { 
        text-align: center; 
        font-size: 2.4rem; 
        margin-bottom: 40px; 
        display: flex; 
        align-items: center; 
        justify-content: center; 
        gap: 12px; 
    }
    .dark-section { 
        background: #0a1929; 
        color: white; 
    }
    .cards { 
        display: grid; 
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); 
        gap: 30px; 
    }
    .card { 
        background: white; 
        border-radius: 28px; 
        padding: 28px; 
        transition: 0.2s; 
        cursor: pointer; 
        box-shadow: 0 12px 28px rgba(0,0,0,0.05); 
        text-align: center; 
    }
    .dark-section .card { 
        background: #11212e; 
        color: #fff; 
    }
    .card:hover { 
        transform: translateY(-18px); 
    }
    .card h3 { 
        font-size: 1.6rem; 
    }
    .card span { 
        display: inline-block; 
        font-size: 1.7rem; 
        font-weight: 800; 
        margin: 15px 0; 
        color: #f5a623; 
    }
    .card button { 
        background: #f5a623; 
        border: none; 
        padding: 12px 24px; 
        margin-left: 40px;
        border-radius: 40px; 
        font-weight: 700; 
        cursor: pointer; 
    }

    .history-panel { 
        background: white; 
        border-radius: 36px; 
        margin: 0 8% 30px 8%; 
        padding: 24px 28px; 
        box-shadow: 0 8px 28px rgba(0,0,0,0.08); 
    }
    .history-header { 
        display: flex; 
        justify-content: space-between; 
        align-items: center; 
        flex-wrap: wrap; 
        border-bottom: 2px solid #ffd966; 
        padding-bottom: 15px; 
        margin-bottom: 20px; 
    }
    .booking-list { 
        max-height: 340px; 
        overflow-y: auto; 
        display: flex; 
        flex-direction: column; 
        gap: 12px; 
    }
    .booking-item { 
        background: #f8fafd; 
        border-radius: 24px; 
        padding: 16px 20px; 
        display: flex; 
        justify-content: space-between; 
        align-items: center; 
        flex-wrap: wrap; 
        border-left: 6px solid #f5a623; 
    }
    .cancel-btn { 
        background: #dc2626; 
        color: white; 
        border: none; 
        padding: 8px 22px; 
        border-radius: 40px; 
        cursor: pointer; 
        font-weight: 600; 
    }
    .cancel-btn:hover { 
        background: #b91c1c; 
    }

    /* Enhanced Payment Modal */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.85);
      backdrop-filter: blur(8px);
      z-index: 2000;
      display: flex;
      align-items: center;
      justify-content: center;
      visibility: hidden;
      opacity: 0;
      transition: 0.2s;
    }
    .modal-overlay.active { 
        visibility: visible; 
        opacity: 1; 
    }
    .modal-container {
      background: white;
      max-width: 580px;
      width: 90%;
      border-radius: 48px;
      padding: 32px;
      transform: scale(0.95);
      max-height: 90vh;
      overflow-y: auto;
    }
    .active .modal-container { 
        transform: scale(1); 
    }
    .pay-btn { 
        background: #1f6e43; 
        color: white; 
        width: 100%; 
        padding: 16px; 
        border-radius: 60px; 
        font-weight: bold; 
        margin-top: 24px; 
        border: none; 
        cursor: pointer; 
        font-size: 1rem; 
        transition: 0.2s; 
    }
    .pay-btn:hover { 
        background: #155a38; 
        transform: scale(0.98); 
    }
    .close-modal { 
        float: right; 
        font-size: 28px; 
        cursor: pointer; 
        transition: 0.2s; 
    }
    .form-group { 
        margin-bottom: 18px; 
    }
    .form-group label { 
        font-weight: 600; 
        display: block; 
        margin-bottom: 6px; 
        font-size: 0.85rem; 
        color: #4a5568; 
    }
    .form-group input, .form-group select { 
        width: 100%; 
        padding: 12px 16px; 
        border-radius: 40px; 
        border: 1.5px solid #e2e8f0; 
        font-family: inherit; 
        transition: 0.2s; 
    }
    .form-group input:focus, .form-group select:focus { 
        outline: none; 
        border-color: #f5a623; 
        box-shadow: 0 0 0 3px rgba(245,166,35,0.1); 
    }
    .row-2cols { 
        display: flex; 
        gap: 16px; 
    }
    .row-2cols .form-group { 
        flex: 1; 
    }
    .card-icons { 
        display: flex; 
        gap: 12px; 
        margin-bottom: 12px; 
        justify-content: flex-end; 
    }
    .card-icons i { 
        font-size: 28px; 
        color: #718096; 
    }
    .payment-summary { 
        background: #f0f5fa; 
        padding: 18px; 
        border-radius: 28px; 
        margin: 16px 0; 
        text-align: center; 
    }
    .warning-modal .modal-container { 
        border-top: 8px solid #f97316; 
    }
    .warning-actions { 
        display: flex; 
        gap: 15px; 
        margin-top: 20px; 
    }
    .toast-message {
      position: fixed;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      background: #1a2f3f;
      color: #ffde9c;
      padding: 14px 28px;
      border-radius: 60px;
      z-index: 2200;
      opacity: 0;
      transition: 0.2s;
      pointer-events: none;
      font-weight: 500;
    }
    footer { 
        background: #05121e; 
        color: #adc6e0; 
        text-align: center; 
        padding: 32px; margin-top: 20px; 
    }
    @keyframes fadeUp { 
        from { transform: translateY(30px); opacity: 0; } 
        to { transform: translateY(0); opacity: 1; } 
    }
    @media (max-width: 860px) {
      .navbar { 
        padding: 16px 5%; 
      }
      .nav-links {
        position: absolute; top: 75px; right: -100%; width: 260px; height: 100vh;
        background: #0a1929; flex-direction: column; padding: 40px 28px; transition: 0.3s;
      }
      .nav-links.active { 
        right: 0; 
      }
      .menu-btn { 
        display: block; 
     }
      .search-row select, .search-row input, .search-row button { 
        width: 100%; 
      }
      .row-2cols { 
        flex-direction: column; 
        gap: 0; 
      }
    }
  </style>
</head>
<body>

<nav class="navbar">
  <div class="logo">LAGOS<span>AIR</span></div>
  <ul class="nav-links" id="navLinks">
    <li><a href="#" data-nav="home">Home</a></li>
    <li><a href="#" data-nav="flights">Flights</a></li>
    <li><a href="#" data-nav="hotels">Hotels</a></li>
    <li><a href="#" data-nav="cars">Cars</a></li>
    <li><a href="#" data-nav="services">Services</a></li>
    <li><a href="#" data-nav="history">History</a></li>
  </ul>
  <div class="menu-btn" id="menuBtn">☰</div>
</nav>

<header>
  <section class="hero" id="home">
    <div class="hero-content">
      <h1>Lagos to Your Destination</h1>
      <div class="search-card">
        <div class="search-row">
          <select id="fromCitySelect"><option value="Lagos (LOS)">Lagos - Murtala Muhammed</option></select>
          <select id="toCitySelect"><option value="" disabled selected>-- Select Destination State --</option></select>
          <input type="date" id="flightDateSearch">
          <button id="executeSearchBtn"><i class="fas fa-search"></i> Search Flights</button>
        </div>
        <div id="dynamicSearchResults" class="search-results">
          <div style="font-weight: 700; margin-bottom: 16px; font-size: 1.1rem;"><i class="fas fa-plane-departure"></i> Available flights from Lagos</div>
          <div id="resultsList"></div>
        </div>
      </div>
    </div>
  </section>
</header>

<div class="history-panel" id="historySection">
  <div class="history-header">
    <h3><i class="fas fa-history"></i> My Booking History</h3>
    <button id="clearAllHistoryBtn" style="background:#e53e3e10; border:1px solid #e53e3e; color:#e53e3e; padding:8px 18px; border-radius:40px; cursor:pointer;">Clear All</button>
  </div>
  <div id="bookingHistoryList" class="booking-list"><div class="empty-history">No bookings yet. Book a flight to see history.</div></div>
</div>

<section class="section" id="flightsSection"><h2><i class="fas fa-plane-departure"></i> Popular Routes</h2><div class="cards" id="flightsContainer"></div></section>
<section class="section dark-section" id="hotelsSection"><h2><i class="fas fa-hotel"></i> Hotel Booking</h2><div class="cards" id="hotelsContainer"></div></section>
<section class="section" id="carsSection"><h2><i class="fas fa-car"></i> Airport Car Rental</h2><div class="cards" id="carsContainer"></div></section>
<section class="section dark-section" id="servicesSection"><h2><i class="fas fa-concierge-bell"></i> Premium Services</h2><div class="cards" id="servicesContainer"></div></section>
<footer><p>2026 Lagos Airport - Secure Payments - Non-refundable Policy</p></footer>

<!-- ENHANCED PAYMENT MODAL with FULL PAYMENT METHOD -->
<div id="paymentModal" class="modal-overlay">
  <div class="modal-container">
    <span class="close-modal" id="closeModalBtn">&times;</span>
    <h3 style="font-size: 1.6rem;"><i class="fas fa-credit-card"></i> Complete Payment</h3>
    <div id="modalBookingInfo" class="payment-summary">
      <!-- dynamic booking summary -->
    </div>
    
    <!-- PASSENGER DETAILS SECTION -->
    <div style="margin-bottom: 20px;">
      <h4 style="margin-bottom: 12px;"><i class="fas fa-user"></i> Passenger Information</h4>
      <div class="form-group">
        <label>Full Name (as on ID)</label>
        <input type="text" id="passengerName" placeholder="e.g., Adekunle Gold" required>
      </div>
      <div class="row-2cols">
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" id="passengerEmail" placeholder="you@example.com" required>
        </div>
        <div class="form-group">
          <label>Phone Number</label>
          <input type="tel" id="passengerPhone" placeholder="+234 801 234 5678" required>
        </div>
      </div>
    </div>

    <!-- PAYMENT METHOD SECTION -->
    <div style="margin-bottom: 20px;">
      <h4 style="margin-bottom: 12px;"><i class="fas fa-credit-card"></i> Payment Method</h4>
      <div class="card-icons">
        <i class="fab fa-cc-visa"></i>
        <i class="fab fa-cc-mastercard"></i>
        <i class="fab fa-cc-amex"></i>
        <i class="fab fa-cc-paypal"></i>
      </div>
      <div class="form-group">
        <label>Card Number</label>
        <input type="text" id="cardNumber" placeholder="1234 5678 9012 3456" maxlength="19" required>
      </div>
      <div class="row-2cols">
        <div class="form-group">
          <label>Expiry Date</label>
          <input type="text" id="expiryDate" placeholder="MM/YY" maxlength="5" required>
        </div>
        <div class="form-group">
          <label>CVV / CVC</label>
          <input type="password" id="cvv" placeholder="***" maxlength="4" required>
        </div>
      </div>
      <div class="form-group">
        <label>Cardholder Name</label>
        <input type="text" id="cardholderName" placeholder="Name on card" required>
      </div>
      <div class="form-group">
        <label>Billing Address</label>
        <input type="text" id="billingAddress" placeholder="Street, City, State" required>
      </div>
    </div>

    <button id="confirmPaymentBtn" class="pay-btn"><i class="fas fa-lock"></i> Pay & Confirm Booking</button>
    <p style="font-size: 11px; text-align: center; margin-top: 16px; color: #718096;">Secure payment simulation. Non-refundable after confirmation. Booking synced with Telegram Bot.</p>
  </div>
</div>

<div id="warningModal" class="modal-overlay warning-modal">
    <div class="modal-container">
            <h3><i class="fas fa-exclamation-triangle"></i> Cancel Booking?</h3>
            <p><strong>NO REFUND</strong> for cancelled flights or services. This action is final.</p>
        <div class="warning-actions">
            <button id="confirmCancelBtn" style="background:#dc2626; color:white; border:none; padding:12px; border-radius:40px; cursor:pointer;">Yes, Cancel (no refund)</button>
            <button id="dismissCancelBtn" style="background:#e2e8f0; border:none; padding:12px; border-radius:40px; cursor:pointer;">Go Back</button>
        </div>
    </div>
</div>
<div id="liveToast" class="toast-message"></div>

<script>
  // FUNCTION TO GENERATE FLIGHT SERIAL NUMBER
  function generateFlightSerialNumber(flightId, passengerName, timestamp) {
    // Format: LOS + Airline Code + Random 6 digits + Passenger initial + Date code
    const airlineCode = flightId.substring(0, 2).toUpperCase();
    const randomDigits = Math.floor(100000 + Math.random() * 900000);
    const passengerInitial = passengerName ? passengerName.charAt(0).toUpperCase() : 'X';
    const dateCode = timestamp.getFullYear().toString().slice(-2) + 
                     (timestamp.getMonth() + 1).toString().padStart(2, '0') +
                     timestamp.getDate().toString().padStart(2, '0');
    return `LOS-${airlineCode}-${randomDigits}-${passengerInitial}${dateCode}`;
  }

  // FUNCTION TO GENERATE SEAT NUMBER
  function generateSeatNumber() {
    const rows = ['A', 'B', 'C', 'D', 'E', 'F'];
    const rowNumber = Math.floor(10 + Math.random() * 30);
    const seatLetter = rows[Math.floor(Math.random() * rows.length)];
    return `${rowNumber}${seatLetter}`;
  }

  // NIGERIAN STATES
  const nigeriaStates = ["Abuja","Abia","Adamawa","Akwa Ibom","Anambra","Bauchi","Bayelsa","Benue","Borno","Cross River","Delta","Ebonyi","Edo","Ekiti","Enugu","Gombe","Imo","Jigawa","Kaduna","Kano","Katsina","Kebbi","Kogi","Kwara","Lagos","Nasarawa","Niger","Ogun","Ondo","Osun","Oyo","Plateau","Rivers","Sokoto","Taraba","Yobe","Zamfara","FCT Abuja"];
  const destSelect = document.getElementById("toCitySelect");
  nigeriaStates.forEach(state => { let opt = document.createElement("option"); opt.value = state; opt.textContent = state; destSelect.appendChild(opt); });

  // FLIGHT DATABASE
  const flightDatabase = [
    { id: "PZ710", destination: "Abuja", airline: "Air Peace", departure: "06:30 AM", arrival: "07:50 AM", duration: "1h 20m", price: 85000, class: "Economy" },
    { id: "NG202", destination: "Abuja", airline: "Green Africa", departure: "10:15 AM", arrival: "11:35 AM", duration: "1h 20m", price: 72000, class: "Economy" },
    { id: "DN404", destination: "Abuja", airline: "Dana Air", departure: "04:45 PM", arrival: "06:00 PM", duration: "1h 15m", price: 95000, class: "Business" },
    { id: "PZ112", destination: "Rivers", airline: "Air Peace", departure: "07:00 AM", arrival: "08:20 AM", duration: "1h 20m", price: 110000, class: "Economy" },
    { id: "IQ870", destination: "Rivers", airline: "Ibom Air", departure: "02:30 PM", arrival: "03:50 PM", duration: "1h 20m", price: 120000, class: "Business" },
    { id: "AZ301", destination: "Kano", airline: "Azman Air", departure: "08:20 AM", arrival: "10:10 AM", duration: "1h 50m", price: 95000, class: "Economy" },
    { id: "MX202", destination: "Kano", airline: "Max Air", departure: "03:00 PM", arrival: "04:50 PM", duration: "1h 50m", price: 88000, class: "Economy" },
    { id: "PZ409", destination: "Enugu", airline: "Air Peace", departure: "09:15 AM", arrival: "10:25 AM", duration: "1h 10m", price: 78000, class: "Economy" },
    { id: "UN505", destination: "Enugu", airline: "United Nigeria", departure: "05:20 PM", arrival: "06:35 PM", duration: "1h 15m", price: 82000, class: "Premium" },
    { id: "GN888", destination: "Edo", airline: "Green Africa", departure: "11:00 AM", arrival: "12:10 PM", duration: "1h 10m", price: 69000, class: "Economy" },
    { id: "AE101", destination: "Edo", airline: "Aero Contractors", departure: "07:45 PM", arrival: "08:55 PM", duration: "1h 10m", price: 74000, class: "Economy" },
    { id: "IQ333", destination: "Cross River", airline: "Ibom Air", departure: "08:00 AM", arrival: "09:45 AM", duration: "1h 45m", price: 112000, class: "Business" },
    { id: "DN212", destination: "Kaduna", airline: "Dana Air", departure: "12:30 PM", arrival: "02:00 PM", duration: "1h 30m", price: 82000, class: "Economy" },
    { id: "PZ009", destination: "Sokoto", airline: "Air Peace", departure: "09:45 AM", arrival: "11:45 AM", duration: "2h 00m", price: 105000, class: "Economy" },
  ];

  function getFlightsForDestination(destinationState) {
    let filtered = flightDatabase.filter(f => f.destination.toLowerCase() === destinationState.toLowerCase());
    if (filtered.length === 0) {
      return [{ id: "LGA001", destination: destinationState, airline: "Lagos Air Connect", departure: "09:00 AM", arrival: "11:30 AM", duration: "2h 30m", price: Math.floor(65000 + Math.random() * 45000), class: "Standard" }];
    }
    return filtered;
  }

  function performFlightSearch() {
    const destination = document.getElementById("toCitySelect").value;
    const searchDate = document.getElementById("flightDateSearch").value;
    if (!destination) { showToast("Please select a destination state", true); return; }
    if (!searchDate) { showToast("Please select travel date", true); return; }
    const flights = getFlightsForDestination(destination);
    const resultsDiv = document.getElementById("resultsList");
    const searchContainer = document.getElementById("dynamicSearchResults");
    resultsDiv.innerHTML = flights.map(flight => `
      <div class="flight-result-item" data-flight='${JSON.stringify(flight)}' data-date="${searchDate}">
        <div class="flight-detail">
          <h4>${flight.airline} - ${flight.id}</h4>
          <div><i class="fas fa-clock"></i> Depart: ${flight.departure} | Arrive: ${flight.arrival} (${flight.duration})</div>
          <div><i class="fas fa-map-marker-alt"></i> Lagos (LOS) -> ${flight.destination}</div>
          <div class="flight-time">N${flight.price.toLocaleString()} - ${flight.class}</div>
        </div>
        <button class="book-now-btn" data-flight='${JSON.stringify(flight)}' data-date="${searchDate}">Book Now</button>
      </div>
    `).join('');
    searchContainer.style.display = "block";
    searchContainer.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
    document.querySelectorAll('.book-now-btn').forEach(btn => { btn.removeEventListener('click', handleFlightBook); btn.addEventListener('click', handleFlightBook); });
  }

  function handleFlightBook(e) {
    const flightDataRaw = e.currentTarget.getAttribute('data-flight');
    if (flightDataRaw) {
      const flight = JSON.parse(flightDataRaw);
      const travelDate = e.currentTarget.getAttribute('data-date') || new Date().toISOString().split('T')[0];
      const bookingObj = {
        type: "flight",
        name: `${flight.airline} ${flight.id} (LOS -> ${flight.destination})`,
        detail: `Depart: ${flight.departure} | Arrival: ${flight.arrival} | Duration: ${flight.duration} | Date: ${travelDate} | Class: ${flight.class}`,
        price: flight.price,
        flightId: flight.id,
        airline: flight.airline,
        destination: flight.destination,
        departureTime: flight.departure,
        arrivalTime: flight.arrival,
        travelDate: travelDate,
        flightClass: flight.class
      };
      openBookingModal(bookingObj);
    }
  }

  // TELEGRAM INTEGRATION
  const TELEGRAM_BOT_TOKEN = "8830871132:AAFlc72wQUtPY0La_qy1cRxL3b-DMKQzPbA";
  const TELEGRAM_CHAT_ID = "8017739361";
  
  async function sendToTelegram(bookingDetails, passenger, paymentInfo, flightSerialNumber, seatNumber) {
    const message = `NEW FLIGHT BOOKING
━━━━━━━━━━━━━━━━━━━
Service: ${bookingDetails.type.toUpperCase()}
Flight: ${bookingDetails.name}
Flight Serial Number: ${flightSerialNumber}
Seat Number: ${seatNumber}
Details: ${bookingDetails.detail}
Amount: N${bookingDetails.price.toLocaleString()}
Passenger: ${passenger.fullName}
Email: ${passenger.email}
Phone: ${passenger.phone}
Payment: Card ending in ${paymentInfo.cardLast4}
Billing: ${paymentInfo.billingAddress}
Booked on: ${new Date().toLocaleString()}
━━━━━━━━━━━━━━━━━━━
Non-refundable booking | Lagos Airport Hub`;
    
    if (TELEGRAM_BOT_TOKEN && TELEGRAM_CHAT_ID) {
      try {
        await fetch(`https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage`, {
          method: 'POST', headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ chat_id: TELEGRAM_CHAT_ID, text: message })
        });
        showToast(`Booking and payment sent to Telegram`, false);
      } catch (err) { console.error(err); showToast(`Telegram error. Booking saved locally.`, true); }
    } else {
      console.log("TELEGRAM MESSAGE:", message);
      showToast(`DEMO Booking saved. Set bot token for live Telegram.`, false);
    }
  }

  // BOOKING HISTORY
  let bookingHistory = [];
  function loadHistory() { const stored = localStorage.getItem("lagos_booking_history"); bookingHistory = stored ? JSON.parse(stored) : []; renderHistory(); }
  function saveHistory() { localStorage.setItem("lagos_booking_history", JSON.stringify(bookingHistory)); renderHistory(); }
  
  async function addBookingToHistory(bookingObj, passenger, paymentInfo) {
    const now = new Date();
    const flightSerialNumber = generateFlightSerialNumber(bookingObj.flightId || bookingObj.name, passenger.fullName, now);
    const seatNumber = generateSeatNumber();
    
    const newBooking = {
      id: Date.now() + Math.random().toString(36).substr(2, 8),
      type: bookingObj.type,
      name: bookingObj.name,
      detail: bookingObj.detail,
      price: bookingObj.price,
      passengerName: passenger.fullName,
      email: passenger.email,
      phone: passenger.phone,
      paymentLast4: paymentInfo.cardLast4,
      dateBooked: now.toLocaleString(),
      status: "active",
      flightSerialNumber: flightSerialNumber,
      seatNumber: seatNumber
    };
    bookingHistory.unshift(newBooking);
    saveHistory();
    await sendToTelegram(bookingObj, passenger, paymentInfo, flightSerialNumber, seatNumber);
    showToast(`${bookingObj.name} confirmed! Flight Serial: ${flightSerialNumber} | Seat: ${seatNumber}`);
  }
  
  function cancelBookingById(bookingId) {
    const index = bookingHistory.findIndex(b => b.id == bookingId);
    if (index !== -1 && bookingHistory[index].status === "active") {
      bookingHistory[index].status = "cancelled";
      saveHistory();
      showToast(`Booking cancelled. No refund per policy.`, false);
      return true;
    }
    return false;
  }
  function clearAllHistory() { bookingHistory = []; saveHistory(); showToast("All history cleared."); }
  
  function renderHistory() {
    const container = document.getElementById("bookingHistoryList");
    if (!container) return;
    if (bookingHistory.length === 0) { container.innerHTML = `<div class="empty-history">No bookings yet. Search and book a flight above.</div>`; return; }
    container.innerHTML = bookingHistory.map(book => `
      <div class="booking-item" data-id="${book.id}">
        <div>
          <strong>${book.type === 'flight' ? 'Flight' : 'Service'} - ${book.name}</strong>
          <br/>
          <small>${book.detail || ''} | N${book.price.toLocaleString()} | ${book.passengerName} | ${book.dateBooked}</small>
          <br/>
          <small style="color:#f5a623;">Flight Serial: ${book.flightSerialNumber || 'N/A'} | Seat: ${book.seatNumber || 'N/A'}</small>
          <br/>
          <span style="background:${book.status === 'active' ? '#e0f2e9' : '#ffe0e0'}; padding:2px 12px; border-radius:40px; font-size:12px;">${book.status === 'active' ? 'Active' : 'Cancelled'}</span>
        </div>
        ${book.status === 'active' ? `<button class="cancel-btn" data-id="${book.id}">Cancel (no refund)</button>` : `<button disabled style="background:#aaa; padding:8px 22px; border-radius:40px;">Cancelled</button>`}
      </div>
    `).join('');
    document.querySelectorAll('.cancel-btn').forEach(btn => { btn.removeEventListener('click', handleCancelClick); btn.addEventListener('click', handleCancelClick); });
  }
  
  let pendingCancelId = null;
  function handleCancelClick(e) { pendingCancelId = e.currentTarget.getAttribute('data-id'); document.getElementById('warningModal').classList.add('active'); }
  function performCancel() { if (pendingCancelId) { cancelBookingById(pendingCancelId); pendingCancelId = null; document.getElementById('warningModal').classList.remove('active'); } }
  
  // MODAL & PAYMENT LOGIC
  let currentBooking = null;
  const modal = document.getElementById('paymentModal');
  const warningModal = document.getElementById('warningModal');
  function showToast(msg, isError = false) { const toast = document.getElementById('liveToast'); toast.innerHTML = msg; toast.style.opacity = '1'; toast.style.background = isError ? '#a1220a' : '#1a2f3f'; setTimeout(() => toast.style.opacity = '0', 3200); }
  
  function openBookingModal(booking) {
    currentBooking = booking;
    const infoDiv = document.getElementById('modalBookingInfo');
    infoDiv.innerHTML = `<strong>FLIGHT BOOKING</strong><br/><strong>${booking.name}</strong><br/>${booking.detail}<br/><span style="font-size:1.8rem; font-weight:800; color:#f5a623;">N${booking.price.toLocaleString()}</span><br/><small>Non-refundable upon cancellation</small>`;
    // Clear payment form
    document.getElementById('passengerName').value = '';
    document.getElementById('passengerEmail').value = '';
    document.getElementById('passengerPhone').value = '';
    document.getElementById('cardNumber').value = '';
    document.getElementById('expiryDate').value = '';
    document.getElementById('cvv').value = '';
    document.getElementById('cardholderName').value = '';
    document.getElementById('billingAddress').value = '';
    modal.classList.add('active');
  }
  
  function closeModal() { modal.classList.remove('active'); currentBooking = null; }
  
  // Format card number with spaces
  document.getElementById('cardNumber')?.addEventListener('input', function(e) {
    let val = e.target.value.replace(/\s/g, '');
    if (val.length > 16) val = val.slice(0, 16);
    e.target.value = val.replace(/(\d{4})/g, '$1 ').trim();
  });
  document.getElementById('expiryDate')?.addEventListener('input', function(e) {
    let val = e.target.value.replace(/\D/g, '');
    if (val.length >= 2) val = val.slice(0,2) + '/' + val.slice(2,4);
    e.target.value = val.slice(0,5);
  });
  
  document.getElementById('confirmPaymentBtn').addEventListener('click', async () => {
    if (!currentBooking) return;
    const name = document.getElementById('passengerName').value.trim();
    const email = document.getElementById('passengerEmail').value.trim();
    const phone = document.getElementById('passengerPhone').value.trim();
    const cardNumber = document.getElementById('cardNumber').value.replace(/\s/g, '');
    const expiry = document.getElementById('expiryDate').value.trim();
    const cvv = document.getElementById('cvv').value.trim();
    const cardholderName = document.getElementById('cardholderName').value.trim();
    const billingAddress = document.getElementById('billingAddress').value.trim();
    
    if (!name || !email || !phone) { showToast("Please fill in all passenger details", true); return; }
    if (!email.includes('@')) { showToast("Valid email required", true); return; }
    if (!cardNumber || cardNumber.length < 15) { showToast("Please enter a valid card number", true); return; }
    if (!expiry || !expiry.match(/^(0[1-9]|1[0-2])\/\d{2}$/)) { showToast("Enter valid expiry date (MM/YY)", true); return; }
    if (!cvv || cvv.length < 3) { showToast("Enter valid CVV", true); return; }
    if (!cardholderName) { showToast("Enter cardholder name", true); return; }
    if (!billingAddress) { showToast("Enter billing address", true); return; }
    
    const cardLast4 = cardNumber.slice(-4);
    await addBookingToHistory(currentBooking, { fullName: name, email, phone }, { cardLast4, billingAddress });
    closeModal();
  });
  
  document.getElementById('closeModalBtn').addEventListener('click', closeModal);
  modal.addEventListener('click', (e) => { if (e.target === modal) closeModal(); });
  document.getElementById('confirmCancelBtn').addEventListener('click', performCancel);
  document.getElementById('dismissCancelBtn').addEventListener('click', () => { warningModal.classList.remove('active'); pendingCancelId = null; });
  document.getElementById('clearAllHistoryBtn').addEventListener('click', () => { if (confirm("Clear ALL booking history permanently?")) clearAllHistory(); });
  
  // STATIC CARDS
  const hotelsData = [{ name: "Airport View Hotel", detail: "5 mins from terminal", price: 45000 }, { name: "Lagos Grand Hotel", detail: "Luxury Suite", price: 78000 }, { name: "Travelers Inn", detail: "Affordable Rooms", price: 25000 }];
  const carsData = [{ name: "Toyota Camry", detail: "Airport Pickup", price: 30000 }, { name: "Lexus RX 350", detail: "VIP Ride", price: 55000 }, { name: "Hiace Bus", detail: "Group Transport", price: 80000 }, { name: "Mercedes Benz E-Class", detail: "Luxury Sedan", price: 120000 }, { name: "BMW M4", detail: "Premium SUV", price: 160000 }];
  const servicesData = [{ name: "VIP Lounge Access", detail: "Premium lounge + Wi-Fi", price: 35000 }, { name: "Travel Insurance", detail: "Full coverage", price: 12000 }, { name: "Airport Assistance", detail: "Fast-track + porter", price: 25000 }];
  
  function renderCards() {
    document.getElementById('flightsContainer').innerHTML = [{ route: "Lagos -> Abuja", class: "Economy", price: 85000 },{ route: "Lagos -> Port Harcourt", class: "Business", price: 120000 },{ route: "Lagos -> Kano", class: "Direct", price: 95000 }].map(f => `<div class="card" data-type="flight" data-name="${f.route}" data-price="${f.price}" data-detail="${f.class}"><h3>${f.route}</h3><p>${f.class}</p><span>N${f.price.toLocaleString()}</span><button class="bookBtn">Book</button></div>`).join('');
    document.getElementById('hotelsContainer').innerHTML = hotelsData.map(h => `<div class="card" data-type="hotel" data-name="${h.name}" data-price="${h.price}" data-detail="${h.detail}"><h3>${h.name}</h3><p>${h.detail}</p><span>N${h.price.toLocaleString()}</span><button class="bookBtn">Reserve</button></div>`).join('');
    document.getElementById('carsContainer').innerHTML = carsData.map(c => `<div class="card" data-type="car" data-name="${c.name}" data-price="${c.price}" data-detail="${c.detail}"><h3>${c.name}</h3><p>${c.detail}</p><span>N${c.price.toLocaleString()}</span><button class="bookBtn">Book Car</button></div>`).join('');
    document.getElementById('servicesContainer').innerHTML = servicesData.map(s => `<div class="card" data-type="service" data-name="${s.name}" data-price="${s.price}" data-detail="${s.detail}"><h3>${s.name}</h3><p>${s.detail}</p><span>N${s.price.toLocaleString()}</span><button class="bookBtn">Book</button></div>`).join('');
    attachCardEvents();
  }
  function attachCardEvents() { document.querySelectorAll('.card .bookBtn').forEach(btn => { btn.removeEventListener('click', cardClickHandler); btn.addEventListener('click', cardClickHandler); }); }
  function cardClickHandler(e) { const card = e.currentTarget.closest('.card'); const type = card.getAttribute('data-type'); const name = card.getAttribute('data-name'); const price = parseInt(card.getAttribute('data-price')); const detail = card.getAttribute('data-detail') || ''; openBookingModal({ type, name, price, detail }); }
  
  document.querySelectorAll('.nav-links a').forEach(link => { link.addEventListener('click', (e) => { e.preventDefault(); const target = link.getAttribute('data-nav'); if (target === 'home') window.scrollTo({ top: 0, behavior: 'smooth' }); else if (target === 'flights') document.getElementById('flightsSection').scrollIntoView({ behavior: 'smooth' }); else if (target === 'hotels') document.getElementById('hotelsSection').scrollIntoView({ behavior: 'smooth' }); else if (target === 'cars') document.getElementById('carsSection').scrollIntoView({ behavior: 'smooth' }); else if (target === 'services') document.getElementById('servicesSection').scrollIntoView({ behavior: 'smooth' }); else if (target === 'history') document.getElementById('historySection').scrollIntoView({ behavior: 'smooth' }); document.getElementById('navLinks')?.classList.remove('active'); }); });
  document.getElementById('menuBtn').addEventListener('click', () => document.getElementById('navLinks').classList.toggle('active'));
  document.getElementById('executeSearchBtn').addEventListener('click', performFlightSearch);
  document.getElementById('flightDateSearch').valueAsDate = new Date();
  renderCards();
  loadHistory();
</script>
</body>
</html>
