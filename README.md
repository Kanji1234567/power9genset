# power9genset

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Power9 Genset Auto Service - Offering expert generator installation, maintenance, and repair services.">
    <meta name="keywords" content="generator, service, maintenance, repair, installation, Power9 Genset">
    <meta name="author" content="Power9 Genset">
    <title>Power9 Genset Auto Service</title>
    <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <style>
        /* General reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Open Sans', sans-serif;
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }

        /* Header Section */
        header {
            background-color: #003c3f;
            color: white;
            text-align: center;
            padding: 40px 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        header h1 {
            font-size: 3rem;
            letter-spacing: 2px;
        }

        /* Navigation */
        nav {
            background-color: #004d40;
            padding: 15px 0;
            text-align: center;
            position: sticky;
            top: 0;
            width: 100%;
            z-index: 100;
        }
        nav a {
            color: white;
            text-decoration: none;
            font-size: 18px;
            margin: 0 20px;
            padding: 12px;
            display: inline-block;
            transition: all 0.3s ease;
        }
        nav a:hover {
            background-color: #00897b;
            border-radius: 5px;
        }

        /* Hero Section */
        .hero {
            background-image: url('background.jpg');
            background-size: cover;
            background-position: center;
            padding: 100px 20px;
            color: white;
            text-align: center;
            border-bottom: 5px solid #004d40;
        }
        .hero h2 {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        .hero button {
            padding: 15px 30px;
            background-color: #004d40;
            color: white;
            border: none;
            font-size: 18px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .hero button:hover {
            background-color: #00796b;
        }

        /* Section Layout */
        .section {
            padding: 80px 20px;
            text-align: center;
            background-color: #ffffff;
            margin: 40px 0;
            border-radius: 10px;
            box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.1);
        }

        .services-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
        }
        .service-item {
            background-color: #ffffff;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            width: 280px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .service-item:hover {
            transform: scale(1.05);
            box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.2);
        }
        .service-item i {
            font-size: 50px;
            color: #00695c;
        }
        .service-item h3 {
            font-size: 1.6rem;
            margin-top: 15px;
            color: #333;
        }

        /* Testimonials Section */
        .testimonial-carousel {
            display: flex;
            overflow-x: auto;
            gap: 20px;
            padding: 20px;
            justify-content: center;
        }
        .testimonial {
            background-color: #eeeeee;
            padding: 20px;
            border-radius: 8px;
            width: 300px;
            box-shadow: 2px 2px 10px rgba(0,0,0,0.1);
        }
        .testimonial p {
            font-style: italic;
            margin-bottom: 15px;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 30px auto;
            padding: 30px;
            background-color: #f4f4f4;
            border-radius: 10px;
            box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.1);
        }
        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-size: 16px;
        }
        .contact-form button {
            width: 100%;
            padding: 15px;
            background-color: #004d40;
            color: white;
            border: none;
            font-size: 18px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .contact-form button:hover {
            background-color: #00796b;
        }

        /* Footer */
        footer {
            background-color: #003c3f;
            color: white;
            text-align: center;
            padding: 40px 0;
            margin-top: 40px;
        }
        footer a {
            color: white;
            margin: 0 10px;
            text-decoration: none;
            font-size: 18px;
        }
        footer a:hover {
            text-decoration: underline;
        }

        /* Media Query for Mobile */
        @media (max-width: 768px) {
            .services-list {
                flex-direction: column;
                align-items: center;
            }
            .testimonial-carousel {
                flex-direction: column;
            }
        }
    </style>
    <script>
        // Search Function for Services
        function searchService() {
            let input = document.getElementById('search').value.toLowerCase();
            let services = document.querySelectorAll('.services-list .service-item');
            let found = false;
            services.forEach(service => {
                if (service.innerText.toLowerCase().includes(input)) {
                    service.style.display = "block";
                    found = true;
                } else {
                    service.style.display = "none";
                }
            });
            document.getElementById('no-results').style.display = found ? "none" : "block";
        }

        // Validate Contact Form
        function validateForm() {
            let name = document.forms["contactForm"]["name"].value;
            let email = document.forms["contactForm"]["email"].value;
            let message = document.forms["contactForm"]["message"].value;
            if (name === "" || email === "" || message === "") {
                alert("All fields are required.");
                return false;
            }
            return true;
        }
    </script>
</head>
<body>
    <!-- Header Section -->
    <header>
        <h1>Power9 Genset Auto Service</h1>
    </header>

    <!-- Navigation -->
    <nav>
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#testimonials">Testimonials</a>
        <a href="#contact">Contact</a>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <h2>Your Trusted Generator Experts</h2>
        <p>Installation, Maintenance, and Repair Services for Your Generators.</p>
        <button onclick="window.location.href='#contact'">Contact Us Today</button>
    </section>

    <!-- About Us Section -->
    <section id="about" class="section">
        <h2>About Us</h2>
        <p>At Power9 Genset, we specialize in providing top-quality generator services. Whether you need installation, repair, or regular maintenance, our experienced team ensures your systems run smoothly.</p>
    </section>

    <!-- Services Section -->
    <section id="services" class="section">
        <h2>Our Services</h2>
        <div class="services-list">
            <div class="service-item">
                <i class="fas fa-cogs"></i>
                <h3>Installation</h3>
                <p>We offer professional generator installation services tailored to your needs, ensuring efficiency and reliability.</p>
            </div>
            <div class="service-item">
                <i class="fas fa-wrench"></i>
                <h3>Maintenance</h3>
                <p>Regular maintenance to ensure your generator is always ready to perform when you need it most.</p>
            </div>
            <div class="service-item">
                <i class="fas fa-plug"></i>
                <h3>Sales & Consultation</h3>
                <p>Explore our range of generators and get expert advice to choose the perfect one for your requirements.</p>
            </div>
            <div class="service-item">
                <i class="fas fa-headset"></i>
                <h3>Emergency Support</h3>
                <p>Our 24/7 emergency support guarantees that we are always there when you need us the most.</p>
            </div>
        </div>
        <p id="no-results" style="display:none; color:red;">No results found.</p>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="section">
        <h2>What Our Clients Say</h2>
        <div class="testimonial-carousel">
            <div class="testimonial">
                <p>"Power9 Genset's service was incredible. My generator has never run better!"</p>
                <h4>- John Doe</h4>
            </div>
            <div class="testimonial">
                <p>"Reliable and professional! I highly recommend them for all generator services."</p>
                <h4>- Jane Smith</h4>
            </div>
        </div>
    </section>

    <!-- Contact Form Section -->
    <section id="contact" class="section">
        <h2>Contact Us</h2>
        <form name="contactForm" onsubmit="return validateForm()" method="POST" action="YOUR_FORM_ID">
            <input type="text" name="name" placeholder="Your Name" required>
            <input type="email" name="email" placeholder="Your Email" required>
            <textarea name="message" placeholder="Your Message" required></textarea>
            <button type="submit">Submit</button>
        </form>
    </section>

    <!-- Footer Section -->
    <footer>
        <p>&copy; 2025 Power9 Genset Auto Service</p>
        <div>
            <a href="#">Facebook</a>
            <a href="#">Twitter</a>
            <a href="#">Instagram</a>
        </div>
    </footer>
</body>
</html>
