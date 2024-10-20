<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Riwora</title>
    <style>
        @font-face {
            font-family: 'Clash-Grotesk';
            src: url('https://fonts.cdnfonts.com/s/33156/ClashGrotesk-Medium.woff') format('woff');
            font-weight: 500;
            font-style: normal;
        }

        body {
            font-family: 'Avenir-Light', sans-serif;
            color: #000000;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            background-color: #ffffff;
            font-weight: 300;
        }

        /* Header Section */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 30px;
            background-color: rgba(255, 255, 255, 0.5); /* Darker transparent background */
            backdrop-filter: blur(10px); /* Blur effect */
            position: fixed;
            width: 100%;
            z-index: 100;
            top: 0;
            left: 0;
        }

        .logo {
            display: flex;
            align-items: center;
        }

        .logo img {
            height: 20px;
            margin-right: 5px;
        }

        .logo h1 {
            font-family: 'Clash-Grotesk', sans-serif;
            font-size: 1.3rem;
            color: rgb(0, 0, 0);
            margin: 0;
            font-weight: 300;
        }

        nav {
            display: flex;
            flex-grow: 1;
            justify-content: flex-end;
            margin-right: 40px;
        }

        .navigation ul {
            list-style: none;
            display: flex;
            gap: 25px;
            margin: 0;
            padding: 0;
        }

        .navigation a {
            text-decoration: none;
            color: #000000;
            font-size: 1rem;
            transition: color 0.3s ease;
        }

        .navigation a:hover {
            color: #ffaff2;
        }

        /* Hero Section */
        .hero {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 100vw;
            height: 100vh;
            position: relative;
            overflow: hidden;
            background: none;
        }

        /* Parallax Video Styling */
        .parallax-video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 120%;
            object-fit: cover;
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
        }

        .hero-content h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            font-weight: 300;
            color: rgb(0, 0, 0);
            max-width: 900px;
            margin: 0 auto;
            line-height: 1.5;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            line-height: 1.7;
            max-width: 700px;
            font-weight: 300;
            color: rgb(0, 0, 0);
            margin: 0 auto;
        }

        .cta-btn {
            padding: 15px 40px;
            background-color: rgba(255, 255, 255, 0.1);
            color: white;
            border-radius: 30px;
            border: 2px solid white;
            text-decoration: none;
            font-size: 1rem;
            font-weight: 500;
            transition: background-color 0.3s ease, color 0.3s ease;
            position: relative;
            top: 80px;
        }

        .cta-btn:hover {
            background-color: rgba(255, 255, 255, 0.1);
            color: #ffaff2;
        }

        /* What You Get Section */
        .features {
            background-color: #ffffff;
            padding: 60px 15px;
            text-align: center;
        }

        .features h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            font-weight: 300;
        }

        .feature-box {
            display: flex;
            justify-content: space-around;
            align-items: flex-start;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .feature-box div {
            width: 350px;
            padding: 15px;
            background-color: #1a1a1a;
            border-radius: 10px;
            margin: 15px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        /* Hover Effect */
        .feature-box div:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
        }

        .feature-box img {
            width: 100%;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        .feature-box h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            font-weight: bold;
        }

        .feature-box p {
            font-size: 0.9rem;
            line-height: 1.4;
            font-weight: 300;
        }

        /* Customer Reviews Section */
        .reviews-section {
            background-color: #ffffff;
            padding: 60px 15px;
            text-align: left; /* Align to the left */
            margin-bottom: 30px;
            max-width: 400px; /* Constrain width to keep reviews on the left */
            margin-left: 40px;
        }

        .reviews-section h2 {
            font-size: 1.8rem; /* Same as "What You Get" */
            margin-bottom: 20px;
            font-weight: 300;
        }

        .reviews-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
            position: relative;
        }

        .review {
            opacity: 0;
            transition: opacity 1s ease-in-out;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            display: flex;
            align-items: center;
            gap: 15px;
            width: 100%;
            margin-bottom: 20px;
        }

        .review img {
            width: 70px; /* Square image dimensions */
            height: 70px;
            border-radius: 8px; /* Rounded corners */
            object-fit: cover; /* Prevent stretching */
        }

        .review-content {
            text-align: left;
        }

        .review-content h3 {
            font-size: 1.1rem;
            font-weight: bold;
            margin-bottom: 5px;
            color: rgb(6, 6, 6);
        }

        .review-content p {
            font-size: 0.9rem;
            font-weight: 300;
            line-height: 1.4;
            color: #000000;
        }

        /* Counter Section */
        .counter-section {
            background-color: #ffffff;
            padding: 40px;
            text-align: center;
            color: rgb(0, 0, 0);
        }

        .counter h2 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            font-weight: 300;
        }

        .counter .number {
            font-size: 2rem;
            color: #000000;
            font-weight: 300;
        }

        /* Modal Styling */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgb(255, 255, 255);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: rgba(255, 255, 255, 0.9);
            padding: 40px;
            border-radius: 10px;
            text-align: center;
            width: 80%;
            max-width: 600px;
        }

        .modal-content h2 {
            color: white;
            margin-bottom: 30px;
        }

        .form-group {
            display: flex;
            justify-content: space-between;
            gap: 10px;
            margin-bottom: 15px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: none;
            border-radius: 5px;
        }

        input[type="submit"] {
            background-color: #84b3ff;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
        }

        input[type="submit"]:hover {
            background-color: #ffaff2;
        }

        .thank-you-message {
            color: rgb(0, 0, 0);
            font-size: 1.2rem;
            font-family: 'Avenir-Light', sans-serif;
            display: none;
            margin-top: 20px;
        }

        .close-btn {
            color: rgb(0, 0, 0);
            font-size: 24px;
            position: absolute;
            top: 20px;
            right: 40px;
            cursor: pointer;
        }

        /* Footer */
        footer {
            background-color: #ffffff;
            padding: 20px;
            text-align: center;
            color: #000000;
            font-weight: 300;
        }
    </style>
</head>
<body>

   <!-- Header with Navigation -->
<header>
    <div class="logo">
        <img src="logo.png" alt="Riwora Logo" style="height: 70px;"> <!-- Slightly smaller logo size -->
    </div>

    <!-- Right Aligned Navigation Links -->
    <nav class="navigation">
        <ul>
            <li><a href="product.html">Product</a></li>
            <li><a href="pricing.html">Pricing</a></li>
            <li><a href="login.html">Try Riwora</a></li>
        </ul>
    </nav>
</header>

<!-- Hero Section with Parallax Video and Lightened Overlay -->
<section class="hero" onmousemove="createBubbles(event)">
    <div class="background-image" style="background-image: url('your-image.jpg'); background-size: cover; background-position: center; height: 100vh; width: 100%; position: absolute; top: 0; left: 0; z-index: 0;"></div>
>

    <!-- Lightened Overlay on Video -->
    <div class="video-overlay"></div>

    <!-- Content Over Video -->
    <div class="hero-content" style="position: relative; top: -200px;"> <!-- Adjust 'top' to move content upwards -->
        <h1 style="color: black;">Watch your sales soar 5x faster</h1> <!-- Set heading color to black -->
        <p style="color: black;">Riwora automates your client follow-ups, streamlines communication, and maximizes sales efficiency, so you can focus on growing your business.</p> <!-- Set paragraph text color to black -->
        <!-- Hiding the Book a Demo button instead of removing it -->
        <a href="#" class="cta-btn" id="openModal" style="display: none;">Book a Demo</a> <!-- Hides the button -->
    </div>
    
</section>

   <!-- What You Get Section -->
<section id="product" class="features">
    <h2 style="color: #848383; font-family: 'Avenir', sans-serif; font-weight: 300;">Platform that streamlines your sales process</h2>
    <div class="feature-box">
        <!-- First Image Column -->
        <div>
            <img src="your-image-1.jpg" alt="Increased Sales Image" style="width: 100%; height: auto;">
        </div>
        <!-- Second Image Column -->
        <div>
            <img src="your-image-2.jpg" alt="Relief for Employees Image" style="width: 100%; height: auto;">
        </div>
        <!-- Third Image Column -->
        <div>
            <img src="your-image-3.jpg" alt="Competitive Advantage Image" style="width: 100%; height: auto;">
        </div>
    </div>
</section>
<!-- Flex Container to align the Reviews Section and Big Rectangular Image -->
<div style="display: flex; justify-content: flex-start; align-items: flex-start; width: 100%;">

    <!-- Customer Reviews Section -->
    <section class="reviews-section" id="reviews" style="flex: 1; margin-right: 40px;"> <!-- Spacing between reviews and image -->
        <h2>What Our Clients Say</h2>
        <div class="reviews-container">
            <div class="review" id="review1">
                <img src="your-customer-image-1.jpg" alt="Customer 1">
                <div class="review-content">
                    <h3>Huge Boost in Sales!</h3>
                    <p>"Riwora streamlined our follow-ups, increasing our sales by 30%. It’s a total game-changer for any sales team!"</p>
                </div>
            </div>

            <div class="review" id="review2">
                <img src="your-customer-image-2.jpg" alt="Customer 2">
                <div class="review-content">
                    <h3>Super Easy to Use!</h3>
                    <p>"Riwora makes follow-ups effortless. Our response time improved instantly, and our clients love the personalized attention."</p>
                </div>
            </div>

            <div class="review" id="review3">
                <img src="your-customer-image-3.jpg" alt="Customer 3">
                <div class="review-content">
                    <h3>Stress-Free Growth!</h3>
                    <p>"With Riwora, follow-ups are automatic and effective. We’re closing more deals and our team feels less overwhelmed."</p>
                </div>
            </div>
        </div>
    </section>

    <!-- New Section for One Big Rectangular Image with Text on Top -->
    <section style="flex: 0 1 600px; margin-left: 70px; margin-top: 150px; position: relative;">
        <!-- Title Text with Typing Effect -->
        <h2 id="animated-text" class="typing-effect" style="position: absolute; top: -50px; left: 0; font-family: 'Avenir', sans-serif; color: #797676; font-size: 2rem; font-weight: 300;">Connect your inventory & pricings</h2>
        
        <!-- The Image Below the Title -->
        <img src="your-big-image.jpg" alt="Big Rectangular Image" style="width: 1000px; height: 600px; object-fit: contain; border-radius: 0;">
    </section>

</div>


    <!-- Counter Section -->
    <section class="counter-section">
        <div class="counter">
            <h2>Trusted by more than <span class="number" id="counter">0</span> customers</h2>
        </div>
    </section>

    <!-- Modal for Booking a Demo -->
    <div class="modal" id="demoModal">
        <div class="modal-content">
            <span class="close-btn" id="closeModal">&times;</span>
            <h2>Book a Demo</h2>
            <form id="contactForm" action="https://formspree.io/f/xzzbpkon" method="POST">
                <div class="form-group">
                    <input type="text" name="first-name" placeholder="First Name" required>
                    <input type="text" name="last-name" placeholder="Last Name" required>
                </div>
                <div class="form-group">
                    <input type="email" name="email" placeholder="Email" required>
                    <input type="tel" name="phone" placeholder="Phone Number" required>
                </div>
                <div class="form-group">
                    <textarea name="message" rows="4" placeholder="Short Message" required></textarea>
                </div>
                <input type="submit" value="Submit">
            </form>
            <div class="thank-you-message" id="thankYouMessage">Thanks for reaching out! We'll be in touch with you shortly.</div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Riwora. All Rights Reserved.</p>
    </footer>

    <!-- JavaScript for Parallax, Bubble, Reviews Scroll, and Modal -->
    <script>
        window.addEventListener('scroll', function() {
            var scrollPosition = window.pageYOffset;
            var parallaxVideo = document.getElementById('parallaxVideo');
            
            // Adjust video position based on scroll
            parallaxVideo.style.transform = 'translateY(' + (scrollPosition * 0.5) + 'px)';
        });

        // Bubble Effect
        function createBubbles(event) {
            const hero = document.querySelector('.hero');
            const bubble = document.createElement('div');
            bubble.classList.add('bubble');
            
            // Calculate bubble position relative to hero section
            const x = event.clientX - hero.getBoundingClientRect().left;
            const y = event.clientY - hero.getBoundingClientRect().top;

            bubble.style.top = `${y}px`;
            bubble.style.left = `${x}px`;

            // Append bubble to the hero section
            hero.appendChild(bubble);

            // Remove bubble after animation completes
            setTimeout(() => {
                bubble.remove();
            }, 1000);
        }

        // Modal Script
        var modal = document.getElementById("demoModal");
        var openModalBtn = document.getElementById("openModal");
        var closeModalBtn = document.getElementById("closeModal");
        var form = document.getElementById("contactForm");
        var thankYouMessage = document.getElementById("thankYouMessage");

        openModalBtn.onclick = function() {
            modal.style.display = "flex";
        }

        closeModalBtn.onclick = function() {
            modal.style.display = "none";
        }

        window.onclick = function(event) {
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }

        // Handle Form Submission
        form.addEventListener("submit", function(e) {
            e.preventDefault(); // Prevent default form submission
            var formData = new FormData(form);

            fetch("https://formspree.io/f/xzzbpkon", {
                method: "POST",
                body: formData,
                headers: {
                    'Accept': 'application/json'
                }
            }).then(response => {
                if (response.ok) {
                    form.reset(); // Reset form fields
                    thankYouMessage.style.display = "block"; // Show thank you message
                } else {
                    alert("Oops! Something went wrong.");
                }
            }).catch(error => {
                alert("Oops! There was a problem submitting your form.");
            });
        });

        // Scrolling reviews - Smooth fade-in without blocking scroll
        window.addEventListener('scroll', function() {
            const reviews = document.querySelectorAll('.review');
            reviews.forEach((review) => {
                if (isInViewport(review)) {
                    review.style.opacity = 1; // Fade in the review
                } else {
                    review.style.opacity = 0; // Fade out when out of view
                }
            });
        });

        function isInViewport(element) {
            const rect = element.getBoundingClientRect();
            return rect.top >= 0 && rect.bottom <= (window.innerHeight || document.documentElement.clientHeight);
        }

        // Counter Animation JavaScript with Loop
        let counter = document.getElementById('counter');
        let count = 0;
        let target = 1000; // Set your target number here
        let increment = target / 100; // How fast the number will increment

        function updateCounter() {
            count += increment;
            if (count >= target) {
                counter.innerHTML = target.toLocaleString(); // Use comma in number display
                setTimeout(() => {
                    count = 0; // Reset counter
                    interval = setInterval(updateCounter, 20); // Start counting again
                }, 2000); // Pause for 2 seconds before resetting
                clearInterval(interval);
            } else {
                counter.innerHTML = Math.ceil(count).toLocaleString(); // Add comma
            }
        }

        let interval = setInterval(updateCounter, 20); // Update the number every 20 milliseconds
    </script>

</body>
</html>
