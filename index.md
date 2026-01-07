<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project NANDA - SF Bay Area Chapter</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #f9f9f9;
            color: #000000;
            font-family: 'Poppins', sans-serif;
            line-height: 1.5;
            -webkit-font-smoothing: antialiased;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        ul {
            list-style: none;
        }

        /* Layout Utilities */
        .container,
        section,
        footer {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .divider {
            border: none;
            border-top: 1px solid #000;
            margin: 0;
            opacity: 0.1;
        }

        /* Header */
        .site-header {
            min-height: 100vh;
            width: 100%;
            display: flex;
            flex-direction: column;
            background-image: url('assets/header.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            position: relative;
            padding: 0;
        }

        .site-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.5);
            z-index: 0;
        }

        .site-header > * {
            position: relative;
            z-index: 1;
        }

        .header-top,
        .hero-content {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding-left: 2rem;
            padding-right: 2rem;
        }

        .header-top {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            padding-top: 2rem;
            flex: 0 0 auto;
        }

        .header-icons {
            display: flex;
            gap: 1.5rem;
            padding: 0;
        }

        .social-link {
            font-size: 1.5rem;
            color: #000;
            transition: transform 0.2s, color 0.2s;
        }

        .social-link:hover {
            transform: translateY(-2px);
            opacity: 0.7;
        }

        .hero-content {
            flex: 1 0 auto;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-start;
            padding-bottom: 10vh;
        }

        .hero-content .main-title {
            font-size: 3.5rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            margin-bottom: 1.5rem;
            line-height: 1.1;
            font-family: 'Poppins', sans-serif;
        }

        .subtitle {
            font-size: 1.2rem;
            color: #000;
            max-width: 800px;
            margin: 0;
            text-align: left;
            text-shadow: 0 1px 1px rgba(255, 255, 255, 0.8);
        }

        .hero-btn {
            margin-top: 2rem;
        }

        /* Stats Section */
        .stats-section {
            display: flex;
            justify-content: space-around;
            padding: 4rem 2rem;
            text-align: center;
        }

        .stat-number {
            display: block;
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 0.9rem;
            color: #555;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }

        /* Section Titles */
        .section-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 2rem;
        }

        /* Speakers Section */
        .speakers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .speaker-card {
            display: flex;
            flex-direction: column;
        }

        .speaker-image-placeholder {
            width: 100%;
            aspect-ratio: 3/4;
            border: 1px solid #000;
            border-radius: 4px;
            margin-bottom: 1rem;
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease;
        }

        .speaker-image-placeholder:hover {
            transform: scale(1.02);
            border-color: #000;
            background-color: #fff;
        }

        .speaker-name {
            font-size: 1.1rem;
            font-weight: 600;
        }

        .speaker-role {
            font-size: 0.9rem;
            color: #555;
        }

        /* Events Section */
        .events-section {
            display: flex;
            flex-direction: column;
            gap: 3rem;
        }

        .event-item {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 2rem;
            align-items: start;
        }

        .event-image-placeholder {
            width: 100%;
            height: 200px;
            border: 1px solid #000;
            border-radius: 4px;
        }

        .event-name {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .event-meta {
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #ddd;
            padding-bottom: 0.5rem;
            margin-bottom: 1rem;
            font-size: 0.85rem;
            color: #555;
        }

        .event-desc {
            color: #333;
            font-size: 0.95rem;
        }

        /* Involve Section */
        .involve-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
        }

        .involve-card {
            border: 1px solid #000;
            padding: 2.5rem;
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            height: 100%;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .involve-card:hover {
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px);
        }

        .card-title {
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        .card-desc {
            font-size: 1rem;
            color: #333;
            margin-bottom: 2rem;
            flex-grow: 1;
        }

        .btn {
            display: inline-block;
            border: 1px solid #000;
            padding: 0.8rem 1.5rem;
            width: fit-content;
            border-radius: 4px;
            font-weight: 600;
            transition: all 0.3s ease;
            color: #000;
        }

        .btn:hover {
            background-color: #000;
            color: #fff;
        }

        /* Footer */
        .site-footer {
            padding: 4rem 2rem;
            text-align: center;
            border-top: 1px solid #000;
            opacity: 0.9;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 3rem;
        }

        .footer-links a {
            font-size: 1.2rem;
            font-weight: 600;
            opacity: 0.8;
            transition: opacity 0.3s;
        }

        .footer-links a:hover {
            opacity: 1;
            text-decoration: underline;
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .site-header {
                min-height: auto;
            }

            .hero-content {
                padding: 4rem 0;
            }

            .hero-content .main-title {
                font-size: 2.5rem;
            }

            .stats-section {
                flex-wrap: wrap;
                gap: 2rem;
            }

            .stat-item {
                width: 45%;
            }

            .event-item {
                grid-template-columns: 1fr;
            }

            .involve-grid {
                grid-template-columns: 1fr;
            }

            .footer-links {
                gap: 1.5rem;
                flex-wrap: wrap;
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header class="site-header">
        <div class="header-top">
            <div class="spacer"></div> 
            <div class="header-icons">
                <a href="https://chat.whatsapp.com/L5jfpeQCv200INAZuziole" title="WhatsApp" class="social-link"><i class="fab fa-whatsapp"></i></a>
                <a href="https://www.linkedin.com/showcase/agentic-web-sf-bay-area-chapter/" title="LinkedIn" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                <a href="https://lu.ma/nanda" title="Luma Events" class="social-link"><i class="fas fa-calendar-day"></i></a> 
            </div>
        </div>
        
        <div class="hero-content">
            <h1 class="main-title">Project NANDA<br>SF Bay Area Chapter</h1>
            <p class="subtitle">The SF Bay Area chapter of Project NANDA serves as a regional hub for advancing decentralized AI-agent infrastructure. We convene builders, researchers, and institutions to develop open standards, grow the ecosystem, and accelerate real-world deployment.</p>
            <a href="https://projectnanda.org" class="btn hero-btn">Learn More About Project NANDA &rarr;</a>
        </div>
    </header>

    <hr class="divider">

    <!-- Stats Section -->
    <section class="stats-section fade-in">
        <div class="stat-item">
            <span class="stat-number">XX</span>
            <span class="stat-label">Events Conducted</span>
        </div>
        <div class="stat-item">
            <span class="stat-number">XX</span>
            <span class="stat-label">Total Members</span>
        </div>
        <div class="stat-item">
            <span class="stat-number">XX</span>
            <span class="stat-label">Communities Served</span>
        </div>
        <div class="stat-item">
            <span class="stat-number">XX</span>
            <span class="stat-label">Partner Institution</span>
        </div>
    </section>

    <hr class="divider">

    <!-- Speakers Section -->
    <section class="speakers-section fade-in">
        <h2 class="section-title">Previous Speakers</h2>
        <div class="speakers-grid">
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
            <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
             <div class="speaker-card">
                <div class="speaker-image-placeholder"></div>
                <h3 class="speaker-name">Speaker Name</h3>
                <p class="speaker-role">Affiliation</p>
            </div>
        </div>
    </section>

    <hr class="divider">

    <!-- Events Section -->
    <section class="events-section fade-in">
        <h2 class="section-title">Previous Events</h2>
        
        <div class="event-item">
            <div class="event-image-placeholder"></div>
            <div class="event-details">
                <h3 class="event-name">Event Name</h3>
                <div class="event-meta">
                    <span>Location</span>
                    <span>Date/Time</span>
                </div>
                <p class="event-desc">
                    Lorem ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.
                </p>
            </div>
        </div>

        <div class="event-item">
            <div class="event-image-placeholder"></div>
            <div class="event-details">
                <h3 class="event-name">Event Name</h3>
                <div class="event-meta">
                    <span>Location</span>
                    <span>Date/Time</span>
                </div>
                <p class="event-desc">
                    Lorem ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.
                </p>
            </div>
        </div>
    </section>

    <hr class="divider">

    <!-- Get Involved Section -->
    <section class="involve-section fade-in">
        <h2 class="section-title">Get Involved</h2>
        <div class="involve-grid">
            <div class="involve-card">
                <h3 class="card-title">Become a Member</h3>
                <p class="card-desc">Lorem ipsum dolor sit amet consectetur adipiscing elit. Dolor sit omne consectetur adipiscing elit quisque faucibus.</p>
                <a href="https://docs.google.com/forms/d/e/1FAIpQLSdgQdotRNij4mE9MAHXHESgWsl8nsJhVzUue91d-jK9fySbdQ/viewform" class="btn">Join Now &rarr;</a>
            </div>
            <div class="involve-card">
                <h3 class="card-title">Join As A Leader</h3>
                <p class="card-desc">Lorem ipsum dolor sit amet consectetur adipiscing elit. Dolor sit omne consectetur adipiscing elit quisque faucibus.</p>
                <a href="https://docs.google.com/forms/d/e/1FAIpQLSdgQdotRNij4mE9MAHXHESgWsl8nsJhVzUue91d-jK9fySbdQ/viewform" class="btn">Join Now &rarr;</a>
            </div>
        </div>
    </section>

    <hr class="divider">

    <!-- Footer -->
    <footer class="site-footer">
        <div class="footer-links">
            <a href="https://x.com/ProjNanda">Twitter</a>
            <a href="https://github.com/projnanda">GitHub</a>
            <a href="https://chat.whatsapp.com/L5jfpeQCv200INAZuziole">WhatsApp</a>
            <a href="https://lu.ma/nanda">Event</a>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Intersection Observer for fade-in animations
            const observerOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);

            const fadeElements = document.querySelectorAll('.fade-in');
            fadeElements.forEach(el => observer.observe(el));
        });
    </script>
</body>
</html>
