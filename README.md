# funrun
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Charity Fun Run 2024</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }

        .header {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem;
            position: relative;
            overflow: hidden;
        }

        .header h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: fadeIn 1.5s;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .hero-section {
            background: url('running-background.jpg') center/cover;
            height: 500px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            margin-bottom: 2rem;
        }

        .hero-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background-color: #e74c3c;
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            margin: 1rem;
            transition: transform 0.3s, background-color 0.3s;
        }

        .cta-button:hover {
            transform: scale(1.05);
            background-color: #c0392b;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-icon {
            font-size: 2.5rem;
            color: #3498db;
            margin-bottom: 1rem;
        }

        .donation-form {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            max-width: 600px;
            margin: 2rem auto;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }

        .form-group input {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .countdown {
            font-size: 2rem;
            margin: 2rem 0;
            text-align: center;
        }

        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 2rem;
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Charity Fun Run 2024</h1>
        <p>Run for a Cause - Change Lives Together</p>
    </header>

    <div class="hero-section">
        <div class="hero-overlay"></div>
        <div class="hero-content">
            <h2>Join Us in Making a Difference</h2>
            <p>Saturday, June 15th, 2024 - Central Park</p>
            <a href="#donate" class="cta-button">Donate Now</a>
            <a href="#learn-more" class="cta-button">Learn More</a>
        </div>
    </div>

    <div class="container">
        <div class="countdown" id="countdown">
            Time until event: Loading...
        </div>

        <div class="features">
            <div class="feature-card">
                <i class="fas fa-running feature-icon"></i>
                <h3>5K Fun Run</h3>
                <p>Join hundreds of runners in our annual charity event</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-heart feature-icon"></i>
                <h3>Support the Cause</h3>
                <p>100% of donations go directly to helping children in need</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-medal feature-icon"></i>
                <h3>Win Prizes</h3>
                <p>Amazing prizes for top fundraisers and runners</p>
            </div>
        </div>

        <div class="donation-form" id="donate">
            <h2>Make a Donation</h2>
            <form id="donationForm">
                <div class="form-group">
                    <label for="name">Full Name</label>
                    <input type="text" id="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" required>
                </div>
                <div class="form-group">
                    <label for="amount">Donation Amount ($)</label>
                    <input type="number" id="amount" min="5" required>
                </div>
                <button type="submit" class="cta-button">Submit Donation</button>
            </form>
        </div>

        <div id="learn-more">
            <h2>About Our Cause</h2>
            <p>Download our information package to learn more about our charity run and how your donation helps:</p>
            <a href="charity-info.pdf" class="cta-button" download>Download Info Pack</a>
        </div>
    </div>

    <footer>
        <p>Contact us: info@charityfunrun.org | Tel: (555) 123-4567</p>
        <p>© 2024 Charity Fun Run. All rights reserved.</p>
    </footer>

    <script>
        // Countdown Timer
        function updateCountdown() {
            const eventDate = new Date('June 15, 2024 09:00:00').getTime();
            const now = new Date().getTime();
            const distance = eventDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours =
