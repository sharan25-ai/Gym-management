<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FitPro Club - Transform Your Life</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #2ecc71;
            --warning: #f39c12;
            --info: #1abc9c;
            --gradient: linear-gradient(135deg, #2c3e50, #3498db);
            --gradient-accent: linear-gradient(135deg, #e74c3c, #f39c12);
        }
       
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }
       
        body {
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }
       
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
       
        /* Header Styles */
        header {
            background: rgba(44, 62, 80, 0.95);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
       
        header.scrolled {
            padding: 0.5rem 0;
            background: rgba(44, 62, 80, 0.98);
        }
       
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
       
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            animation: fadeInDown 1s ease;
        }
       
        .logo i {
            font-size: 1.8rem;
            color: var(--secondary);
        }
       
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 800;
        }
       
        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }
       
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 5px 10px;
            border-radius: 4px;
            transition: all 0.3s;
            position: relative;
        }
       
        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary);
            transition: width 0.3s ease;
        }
       
        nav a:hover::after, nav a.active::after {
            width: 100%;
        }
       
        .auth-buttons {
            display: flex;
            gap: 10px;
        }
       
        .btn {
            padding: 0.7rem 1.5rem;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 0.9rem;
        }
       
        .btn-primary {
            background: var(--secondary);
            color: white;
        }
       
        .btn-primary:hover {
            background: #2980b9;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.4);
        }
       
        .btn-outline {
            background: transparent;
            color: white;
            border: 2px solid white;
        }
       
        .btn-outline:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-3px);
        }
       
        .btn-accent {
            background: var(--accent);
            color: white;
        }
       
        .btn-accent:hover {
            background: #c0392b;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(231, 76, 60, 0.4);
        }
       
        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
                        url('https://images.unsplash.com/photo-1534438327276-14e5300c3a48?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            align-items: center;
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
       
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            animation: fadeInUp 1s ease;
        }
       
        .hero h2 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
       
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            font-family: 'Open Sans', sans-serif;
        }
       
        .hero-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 2rem;
        }
       
        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            overflow: hidden;
        }
       
        .floating-element {
            position: absolute;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 6s infinite ease-in-out;
        }
       
        .floating-element:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }
       
        .floating-element:nth-child(2) {
            width: 60px;
            height: 60px;
            top: 60%;
            left: 80%;
            animation-delay: 2s;
        }
       
        .floating-element:nth-child(3) {
            width: 100px;
            height: 100px;
            top: 80%;
            left: 20%;
            animation-delay: 4s;
        }
       
        .mouse-scroll {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }
       
        .mouse {
            width: 24px;
            height: 40px;
            border: 2px solid white;
            border-radius: 12px;
            position: relative;
            margin: 0 auto;
        }
       
        .wheel {
            width: 4px;
            height: 8px;
            background: white;
            border-radius: 2px;
            position: absolute;
            top: 8px;
            left: 50%;
            transform: translateX(-50%);
            animation: scroll 1.5s infinite;
        }
       
        /* Features Section */
        .features {
            padding: 100px 0;
            background: white;
        }
       
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }
       
        .section-title h2 {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 1rem;
            position: relative;
            display: inline-block;
        }
       
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--secondary);
            border-radius: 2px;
        }
       
        .section-title p {
            font-size: 1.1rem;
            color: #666;
            max-width: 600px;
            margin: 0 auto;
        }
       
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
       
        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
       
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 0;
            background: var(--gradient);
            transition: height 0.3s ease;
            z-index: -1;
        }
       
        .feature-card:hover::before {
            height: 100%;
        }
       
        .feature-card:hover {
            transform: translateY(-10px);
            color: white;
        }
       
        .feature-card:hover .feature-icon {
            background: white;
            color: var(--secondary);
        }
       
        .feature-card:hover h3, .feature-card:hover p {
            color: white;
        }
       
        .feature-icon {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            font-size: 2rem;
            color: var(--secondary);
            transition: all 0.3s ease;
        }
       
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
            transition: color 0.3s ease;
        }
       
        .feature-card p {
            color: #666;
            transition: color 0.3s ease;
        }
       
        /* Classes Section */
        .classes {
            padding: 100px 0;
            background: var(--light);
        }
       
        .classes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }
       
        .class-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            position: relative;
        }
       
        .class-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
       
        .class-img {
            height: 200px;
            background: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
            position: relative;
            overflow: hidden;
        }
       
        .class-img::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.3);
            transition: opacity 0.3s ease;
        }
       
        .class-card:hover .class-img::after {
            opacity: 0;
        }
       
        .class-info {
            padding: 1.5rem;
        }
       
        .class-info h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }
       
        .class-meta {
            display: flex;
            justify-content: space-between;
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }
       
        .class-card .btn {
            width: 100%;
        }
       
        /* Stats Section */
        .stats {
            padding: 80px 0;
            background: var(--gradient);
            color: white;
            text-align: center;
        }
       
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
        }
       
        .stat-item {
            padding: 2rem 1rem;
        }
       
        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 0.5rem;
            display: block;
        }
       
        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
        }
       
        /* Testimonials */
        .testimonials {
            padding: 100px 0;
            background: white;
        }
       
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
       
        .testimonial-card {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            position: relative;
        }
       
        .testimonial-card::before {
            content: '"';
            position: absolute;
            top: 10px;
            left: 20px;
            font-size: 4rem;
            color: var(--light);
            font-family: Georgia, serif;
            line-height: 1;
        }
       
        .testimonial-text {
            font-style: italic;
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 1;
        }
       
        .testimonial-author {
            display: flex;
            align-items: center;
        }
       
        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--light);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: var(--primary);
        }
       
        .author-info h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }
       
        .author-info p {
            font-size: 0.9rem;
            color: #666;
        }
       
        /* CTA Section */
        .cta {
            padding: 100px 0;
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)),
                        url('https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            text-align: center;
        }
       
        .cta h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
       
        .cta p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
       
        /* Dashboard Section */
        .dashboard {
            padding: 100px 0;
            background: var(--light);
        }
       
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
       
        .dashboard-card {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
       
        .dashboard-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
       
        .dashboard-icon {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: var(--secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            font-size: 2rem;
            color: white;
        }
       
        .dashboard-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
       
        .dashboard-card p {
            color: #666;
            margin-bottom: 1.5rem;
        }
       
        /* Footer */
        footer {
            background: var(--primary);
            color: white;
            padding: 60px 0 30px;
        }
       
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
       
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 10px;
        }
       
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 3px;
            background: var(--secondary);
        }
       
        .footer-links {
            list-style: none;
        }
       
        .footer-links li {
            margin-bottom: 10px;
        }
       
        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: color 0.3s;
        }
       
        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }
       
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
       
        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            transition: all 0.3s;
        }
       
        .social-links a:hover {
            background: var(--secondary);
            transform: translateY(-3px);
        }
       
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bbb;
            font-size: 0.9rem;
        }
       
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
       
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
       
        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
            }
            50% {
                transform: translateY(-20px) rotate(10deg);
            }
        }
       
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0) translateX(-50%);
            }
            40% {
                transform: translateY(-10px) translateX(-50%);
            }
            60% {
                transform: translateY(-5px) translateX(-50%);
            }
        }
       
        @keyframes scroll {
            0% {
                transform: translateY(0) translateX(-50%);
                opacity: 1;
            }
            100% {
                transform: translateY(15px) translateX(-50%);
                opacity: 0;
            }
        }
       
        /* Scroll Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }
       
        .fade-in.appear {
            opacity: 1;
            transform: translateY(0);
        }
       
        /* Mobile Menu */
        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
       
        /* Responsive Design */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
           
            nav {
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background: var(--primary);
                padding: 20px;
                transform: translateY(-100%);
                opacity: 0;
                transition: all 0.3s ease;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            }
           
            nav.active {
                transform: translateY(0);
                opacity: 1;
            }
           
            nav ul {
                flex-direction: column;
                gap: 15px;
            }
           
            .hero h2 {
                font-size: 2.5rem;
            }
           
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
           
            .btn {
                width: 200px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-dumbbell"></i>
                    <h1>FitPro Club</h1>
                </div>
               
                <button class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </button>
               
                <nav id="nav">
                    <ul>
                        <li><a href="#" class="active">Home</a></li>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#classes">Classes</a></li>
                        <li><a href="#dashboard">Dashboard</a></li>
                        <li><a href="#testimonials">Testimonials</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </nav>
               
                <div class="auth-buttons">
                    <button class="btn btn-outline" id="loginBtn">Login</button>
                    <button class="btn btn-primary" id="signupBtn">Join Now</button>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="floating-elements">
            <div class="floating-element"></div>
            <div class="floating-element"></div>
            <div class="floating-element"></div>
        </div>
        <div class="container">
            <div class="hero-content">
                <h2>Transform Your Body, Transform Your Life</h2>
                <p>Join our community of fitness enthusiasts and achieve your goals with personalized training programs, state-of-the-art facilities, and expert guidance.</p>
                <div class="hero-buttons">
                    <!-- Modified button with redirection -->
                    <button class="btn btn-primary" onclick="window.location.href ='microproject.html'">Start Your Journey</button>
                    <button class="btn btn-outline">View Classes</button>
                </div>
            </div>
        </div>
       
        <div class="mouse-scroll">
            <div class="mouse">
                <div class="wheel"></div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Why Choose FitPro</h2>
                <p>We offer everything you need to achieve your fitness goals in a supportive and motivating environment</p>
            </div>
           
            <div class="features-grid">
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-dumbbell"></i>
                    </div>
                    <h3>Modern Equipment</h3>
                    <p>Train with the latest fitness equipment from leading brands to maximize your results.</p>
                </div>
               
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-user-tie"></i>
                    </div>
                    <h3>Expert Trainers</h3>
                    <p>Our certified trainers provide personalized guidance to help you reach your goals faster.</p>
                </div>
               
                <div class="feature-card fade-in">
                    <div class="feature-icon">
                        <i class="fas fa-clock"></i>
                    </div>
                    <h3>Flexible Hours</h3>
                    <p>We're open early until late to fit your busy schedule. Work out when it's convenient for you.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Classes Section -->
    <section class="classes" id="classes">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Popular Classes</h2>
                <p>Join our diverse range of fitness classes designed for all levels and interests</p>
            </div>
           
            <div class="classes-grid">
                <div class="class-card fade-in">
                    <div class="class-img">
                        <i class="fas fa-spa"></i>
                    </div>
                    <div class="class-info">
                        <h3>Yoga & Mindfulness</h3>
                        <div class="class-meta">
                            <span><i class="far fa-clock"></i> 60 min</span>
                            <span><i class="fas fa-user-friends"></i> All levels</span>
                        </div>
                        <p>Improve flexibility, strength, and mental clarity with our guided yoga sessions.</p>
                        <button class="btn btn-primary" style="margin-top: 15px;">Book Now</button>
                    </div>
                </div>
               
                <div class="class-card fade-in">
                    <div class="class-img">
                        <i class="fas fa-running"></i>
                    </div>
                    <div class="class-info">
                        <h3>HIIT Training</h3>
                        <div class="class-meta">
                            <span><i class="far fa-clock"></i> 45 min</span>
                            <span><i class="fas fa-user-friends"></i> Intermediate</span>
                        </div>
                        <p>High-intensity interval training to burn calories and build endurance efficiently.</p>
                        <button class="btn btn-primary" style="margin-top: 15px;">Book Now</button>
                    </div>
                </div>
               
                <div class="class-card fade-in">
                    <div class="class-img">
                        <i class="fas fa-bicycle"></i>
                    </div>
                    <div class="class-info">
                        <h3>Spin Class</h3>
                        <div class="class-meta">
                            <span><i class="far fa-clock"></i> 50 min</span>
                            <span><i class="fas fa-user-friends"></i> All levels</span>
                        </div>
                        <p>Energizing indoor cycling sessions with motivating music and expert instructors.</p>
                        <button class="btn btn-primary" style="margin-top: 15px;">Book Now</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="container">
            <div class="stats-grid">
                <div class="stat-item fade-in">
                    <span class="stat-number" data-count="1500">0</span>
                    <span class="stat-label">Happy Members</span>
                </div>
               
                <div class="stat-item fade-in">
                    <span class="stat-number" data-count="25">0</span>
                    <span class="stat-label">Expert Trainers</span>
                </div>
               
                <div class="stat-item fade-in">
                    <span class="stat-number" data-count="50">0</span>
                    <span class="stat-label">Weekly Classes</span>
                </div>
               
                <div class="stat-item fade-in">
                    <span class="stat-number" data-count="5">0</span>
                    <span class="stat-label">Locations</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Dashboard Section -->
    <section class="dashboard" id="dashboard">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Club Dashboard</h2>
                <p>Track your fitness journey with our comprehensive dashboard</p>
            </div>
           
            <div class="dashboard-grid">
                <div class="dashboard-card fade-in">
                    <div class="dashboard-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Progress Tracking</h3>
                    <p>Monitor your fitness progress with detailed analytics and visual reports.</p>
                    <button class="btn btn-primary">View Progress</button>
                </div>
               
                <div class="dashboard-card fade-in">
                    <div class="dashboard-icon">
                        <i class="fas fa-calendar-alt"></i>
                    </div>
                    <h3>Workout Schedule</h3>
                    <p>Plan and track your workouts with our intuitive scheduling system.</p>
                    <button class="btn btn-primary">View Schedule</button>
                </div>
               
                <div class="dashboard-card fade-in">
                    <div class="dashboard-icon">
                        <i class="fas fa-trophy"></i>
                    </div>
                    <h3>Achievements</h3>
                    <p>Earn badges and rewards as you reach your fitness milestones.</p>
                    <button class="btn btn-primary">View Achievements</button>
                </div>
               
                <div class="dashboard-card fade-in">
                    <div class="dashboard-icon">
                        <i class="fas fa-heartbeat"></i>
                    </div>
                    <h3>Health Metrics</h3>
                    <p>Track vital health metrics like heart rate, BMI, and more.</p>
                    <button class="btn btn-primary">View Metrics</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Success Stories</h2>
                <p>Hear from our members who have transformed their lives with FitPro</p>
            </div>
           
            <div class="testimonials-grid">
                <div class="testimonial-card fade-in">
                    <div class="testimonial-text">
                        "I've tried many gyms before, but FitPro is different. The trainers actually care about your progress and the community is so supportive. I've lost 20 pounds in 3 months!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="author-info">
                            <h4>Sarah Johnson</h4>
                            <p>Member for 2 years</p>
                        </div>
                    </div>
                </div>
               
                <div class="testimonial-card fade-in">
                    <div class="testimonial-text">
                        "The variety of classes keeps me motivated. I never get bored! From yoga to HIIT, there's always something new to try. The facilities are always clean and well-maintained."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="author-info">
                            <h4>Michael Chen</h4>
                            <p>Member for 1 year</p>
                        </div>
                    </div>
                </div>
               
                <div class="testimonial-card fade-in">
                    <div class="testimonial-text">
                        "As a busy professional, I appreciate the flexible hours. I can come in early before work or late after meetings. The staff knows me by name and always makes me feel welcome."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="author-info">
                            <h4>Jessica Williams</h4>
                            <p>Member for 6 months</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta" id="contact">
        <div class="container">
            <div class="section-title fade-in">
                <h2>Ready to Start Your Fitness Journey?</h2>
                <p>Join today and get your first week free with no commitment. Experience the FitPro difference for yourself.</p>
                <button class="btn btn-accent" style="margin-top: 30px; padding: 1rem 2.5rem; font-size: 1.1rem;">Get Started Today</button>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>FitPro Club</h3>
                    <p>Transforming lives through fitness since 2010. Join our community and achieve your health goals.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
               
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#classes">Classes</a></li>
                        <li><a href="#dashboard">Dashboard</a></li>
                        <li><a href="#testimonials">Testimonials</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
               
                <div class="footer-column">
                    <h3>Classes</h3>
                    <ul class="footer-links">
                        <li><a href="#">Yoga</a></li>
                        <li><a href="#">Pilates</a></li>
                        <li><a href="#">HIIT</a></li>
                        <li><a href="#">Spin</a></li>
                        <li><a href="#">Strength Training</a></li>
                        <li><a href="#">Zumba</a></li>
                    </ul>
                </div>
               
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> 123 Fitness Street, Health City</li>
                        <li><i class="fas fa-phone"></i> (555) 123-4567</li>
                        <li><i class="fas fa-envelope"></i> info@fitproclub.com</li>
                        <li><i class="far fa-clock"></i> Mon-Fri: 5am-11pm, Weekends: 7am-9pm</li>
                    </ul>
                </div>
            </div>
           
            <div class="copyright">
                <p>&copy; 2023 FitPro Club. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        const menuToggle = document.getElementById('menuToggle');
        const nav = document.getElementById('nav');
       
        menuToggle.addEventListener('click', function() {
            nav.classList.toggle('active');
        });

        // Scroll animations
        const fadeElements = document.querySelectorAll('.fade-in');
       
        const appearOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -100px 0px"
        };
       
        const appearOnScroll = new IntersectionObserver(function(entries, appearOnScroll) {
            entries.forEach(entry => {
                if (!entry.isIntersecting) {
                    return;
                } else {
                    entry.target.classList.add('appear');
                    appearOnScroll.unobserve(entry.target);
                }
            });
        }, appearOptions);
       
        fadeElements.forEach(element => {
            appearOnScroll.observe(element);
        });

        // Animated counter for stats
        const counters = document.querySelectorAll('.stat-number');
        const speed = 200;
       
        const startCounter = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    counters.forEach(counter => {
                        const updateCount = () => {
                            const target = +counter.getAttribute('data-count');
                            const count = +counter.innerText;
                           
                            const inc = target / speed;
                           
                            if (count < target) {
                                counter.innerText = Math.ceil(count + inc);
                                setTimeout(updateCount, 1);
                            } else {
                                counter.innerText = target;
                            }
                        };
                       
                        updateCount();
                    });
                    startCounter.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });
       
        const statsSection = document.querySelector('.stats');
        startCounter.observe(statsSection);

        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
               
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
               
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                   
                    // Close mobile menu if open
                    nav.classList.remove('active');
                }
            });
        });

        // Interactive hover effects for dashboard cards
        const dashboardCards = document.querySelectorAll('.dashboard-card');
       
        dashboardCards.forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-15px) scale(1.03)';
            });
           
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(-10px) scale(1)';
            });
        });

        // REDIRECTION FUNCTIONALITY - ADDED THIS
        document.getElementById('startJourneyBtn').addEventListener('click', function() {
            // Replace 'dashboard.html' with the actual filename of your second HTML file
            window.location.href = 'dashboard.html';
        });
    </script>
</body>
</html>
