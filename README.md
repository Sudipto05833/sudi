<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Creative Vision - Beyond Design. It's an Experience.</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter & a display font for headlines -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800;900&family=Montserrat:wght@700;800;900&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            overflow-x: hidden; /* Prevent horizontal scrolling */
            scroll-behavior: smooth; /* Smooth scrolling for anchor links */
        }
        /* Custom colors for Tailwind */
        .bg-electric-blue { background-color: #007bff; }
        .text-electric-blue { color: #007bff; }
        .bg-coral-red { background-color: #ff6b6b; }
        .text-coral-red { color: #ff6b6b; }
        .bg-charcoal-black { background-color: #2c3e50; }
        .text-charcoal-black { color: #2c3e50; }
        .bg-sunshine-yellow { background-color: #ffeaa7; }
        .text-sunshine-yellow { color: #ffeaa7; }
        .bg-gradient-hero {
            background-image: linear-gradient(to bottom right, #007bff, #ff6b6b);
        }
        .bg-gradient-section {
            background-image: linear-gradient(to top left, #007bff, #ff6b6b);
        }
        .bg-gradient-cta {
            background-image: linear-gradient(to right, #007bff, #ff6b6b);
        }

        /* Custom animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
            animation: fadeIn 1s ease-out forwards;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        .animate-bounce-hover:hover {
            animation: bounce 0.6s ease-in-out;
        }

        @keyframes textReveal {
            from { width: 0; opacity: 0; }
            to { width: 100%; opacity: 1; }
        }
        .animate-text-reveal {
            overflow: hidden;
            white-space: nowrap;
            animation: textReveal 1.5s steps(15, end) forwards;
            animation-delay: 1s; /* Delay after initial fade-in */
        }

        @keyframes scrollDown {
            0%, 100% { transform: translateY(0); opacity: 1; }
            50% { transform: translateY(10px); opacity: 0.7; }
        }
        .animate-scroll-down {
            animation: scrollDown 1.5s infinite ease-in-out;
        }

        /* Custom carousel styling */
        .carousel-container {
            position: relative;
            overflow: hidden;
        }
        .carousel-slide {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }
        .carousel-item {
            min-width: 100%;
            box-sizing: border-box;
        }
        .carousel-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            z-index: 10;
            border-radius: 50%;
        }
        .carousel-button.prev { left: 10px; }
        .carousel-button.next { right: 10px; }

        /* Floating WhatsApp/Phone icon */
        .floating-contact {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
        }
        .floating-contact a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            background-color: #25D366; /* WhatsApp green */
            color: white;
            border-radius: 50%;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }
        .floating-contact a:hover {
            transform: scale(1.1);
        }
        .floating-contact .fa-phone {
            background-color: #007bff; /* Electric Blue for phone */
        }

        /* Responsive adjustments for asymmetrical layout */
        @media (min-width: 768px) {
            .portfolio-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }
        }
        @media (max-width: 767px) {
            .portfolio-grid {
                grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            }
        }

        /* Motion Graphic Overlay */
        .motion-graphic-overlay .overlay-content {
            position: absolute;
            inset: 0;
            background-color: rgba(0, 0, 0, 0.7);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .motion-graphic-overlay:hover .overlay-content {
            opacity: 1;
        }
        .motion-graphic-overlay .overlay-content i {
            font-size: 3rem;
            color: white;
            margin-bottom: 0.5rem;
        }

        /* Accordion styles for Our Process */
        .accordion-header {
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .accordion-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        .accordion-content.active {
            max-height: 200px; /* Adjust as needed for content */
        }
    </style>
</head>
<body class="bg-charcoal-black text-white">

    <!-- Header/Navigation (Optional, but good for quick links) -->
    <header class="fixed top-0 left-0 w-full bg-charcoal-black bg-opacity-90 z-50 py-4 shadow-lg">
        <nav class="container mx-auto flex justify-between items-center px-4">
            <a href="#hero" class="text-2xl font-extrabold text-sunshine-yellow">Creative Vision</a>
            <div class="hidden md:flex space-x-8">
                <a href="#hero" class="text-white hover:text-electric-blue transition duration-300">Home</a>
                <a href="#about" class="text-white hover:text-electric-blue transition duration-300">About</a>
                <a href="#portfolio" class="text-white hover:text-electric-blue transition duration-300">Portfolio</a>
                <a href="#services" class="text-white hover:text-electric-blue transition duration-300">Services</a>
                <a href="#testimonials" class="text-white hover:text-electric-blue transition duration-300">Testimonials</a>
                <a href="#contact" class="text-white hover:text-electric-blue transition duration-300">Contact</a>
            </div>
            <!-- Mobile Menu Button (Hamburger) -->
            <button class="md:hidden text-white text-2xl" id="mobile-menu-button">
                <i class="fas fa-bars"></i>
            </button>
        </nav>
        <!-- Mobile Menu Overlay -->
        <div id="mobile-menu" class="hidden md:hidden fixed inset-0 bg-charcoal-black bg-opacity-95 z-40 flex flex-col items-center justify-center space-y-8 text-xl">
            <button class="absolute top-4 right-4 text-white text-3xl" id="close-mobile-menu">
                <i class="fas fa-times"></i>
            </button>
            <a href="#hero" class="text-white hover:text-electric-blue transition duration-300" onclick="closeMobileMenu()">Home</a>
            <a href="#about" class="text-white hover:text-electric-blue transition duration-300" onclick="closeMobileMenu()">About</a>
            <a href="#portfolio" class="text-white hover:text-electric-blue transition duration-300" onclick="closeMobileMenu()">Portfolio</a>
            <a href="#services" class="text-white hover:text-electric-blue transition duration-300" onclick="closeMobileMenu()">Services</a>
            <a href="#testimonials" class="text-white hover:text-electric-blue transition duration-300" onclick="closeMobileMenu()">Testimonials</a>
            <a href="#contact" class="text-white hover:text-electric-blue transition duration-300" onclick="closeMobileMenu()">Contact</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="relative h-screen flex items-center justify-center p-4 md:p-8 bg-gradient-hero overflow-hidden">
        <!-- Subtle background shapes/gradients for dynamism -->
        <div class="absolute top-0 left-0 w-64 h-64 bg-electric-blue rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-fade-in" style="animation-delay: 0.2s;"></div>
        <div class="absolute bottom-0 right-0 w-96 h-96 bg-coral-red rounded-full mix-blend-multiply filter blur-xl opacity-30 animate-fade-in" style="animation-delay: 0.4s;"></div>

        <div class="container mx-auto text-center z-10 animate-fade-in">
            <h1 class="text-4xl md:text-6xl lg:text-7xl font-extrabold leading-tight mb-4 drop-shadow-lg font-['Montserrat']">
                Beyond Design. It's an <span class="inline-block animate-text-reveal">Experience.</span>
            </h1>
            <p class="text-lg md:text-xl text-gray-200 mb-8 max-w-3xl mx-auto">
                We don't just create visuals; we craft compelling narratives that resonate and drive results. Specializing in <span class="font-semibold text-sunshine-yellow">Brand Identity, UI/UX, and Motion Graphics</span>.
            </p>
            <div class="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-6">
                <a href="#portfolio" class="bg-sunshine-yellow text-charcoal-black hover:bg-white font-bold py-3 px-8 rounded-full shadow-lg transition duration-300 ease-in-out transform hover:scale-105 animate-bounce-hover">
                    View Our Portfolio
                </a>
                <a href="#contact" class="bg-transparent border-2 border-white text-white hover:bg-white hover:text-charcoal-black font-bold py-3 px-8 rounded-full shadow-lg transition duration-300 ease-in-out transform hover:scale-105">
                    Let's Discuss Your Project
                </a>
            </div>
        </div>

        <!-- Scroll Down Arrow -->
        <a href="#about" class="absolute bottom-10 left-1/2 transform -translate-x-1/2 text-white text-4xl animate-scroll-down">
            <i class="fas fa-chevron-down"></i>
        </a>
    </section>

    <!-- About Us/Me Section -->
    <section id="about" class="py-16 md:py-24 bg-charcoal-black">
        <div class="container mx-auto px-4 grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div class="animate-fade-in" style="animation-delay: 0.2s;">
                <img src="https://placehold.co/600x400/007bff/ffffff?text=Creative+Vision+Team" alt="Creative Vision Team" class="rounded-xl shadow-lg w-full h-auto object-cover">
            </div>
            <div class="animate-fade-in" style="animation-delay: 0.4s;">
                <h2 class="text-3xl md:text-5xl font-bold mb-6 text-coral-red font-['Montserrat']">The Vision Behind the Varnish</h2>
                <p class="text-lg text-gray-300 mb-6">
                    We are <span class="font-semibold text-sunshine-yellow">Creative Vision</span>, a boutique design studio dedicated to transforming ideas into impactful visual realities. With <span class="font-semibold text-electric-blue">10+ years</span> of expertise, we blend cutting-edge design principles with strategic thinking to deliver solutions that are not just beautiful, but highly effective.
                </p>
                <p class="text-lg text-gray-300 mb-8">
                    We believe in collaborative partnerships, meticulous attention to detail, and pushing creative boundaries to achieve unparalleled results for our clients across <span class="font-semibold text-electric-blue">tech, lifestyle, and e-commerce</span> industries.
                </p>

                <!-- Our Process Accordion -->
                <div class="bg-gray-800 rounded-lg p-6 shadow-md mb-6">
                    <div class="accordion-header text-xl font-semibold text-sunshine-yellow" onclick="toggleAccordion('process-accordion')">
                        Our Process
                        <i class="fas fa-chevron-down transform transition-transform duration-300" id="process-accordion-icon"></i>
                    </div>
                    <div class="accordion-content mt-4" id="process-accordion">
                        <ul class="list-disc list-inside text-gray-300 space-y-2">
                            <li><span class="font-semibold">Discovery:</span> Understanding your vision and goals.</li>
                            <li><span class="font-semibold">Strategy:</span> Crafting a tailored design roadmap.</li>
                            <li><span class="font-semibold">Design & Development:</span> Bringing concepts to life.</li>
                            <li><span class="font-semibold">Review & Refine:</span> Iterative feedback for perfection.</li>
                            <li><span class="font-semibold">Launch:</span> Delivering impactful visual solutions.</li>
                        </ul>
                    </div>
                </div>

                <!-- Link to Testimonials (already have a section) -->
                <a href="#testimonials" class="text-electric-blue hover:underline text-lg font-semibold">View Client Testimonials <i class="fas fa-arrow-right ml-2"></i></a>
            </div>
        </div>
    </section>

    <!-- Featured Work/Portfolio Showcase -->
    <section id="portfolio" class="py-16 md:py-24 bg-charcoal-black">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-5xl font-bold text-center mb-4 text-electric-blue font-['Montserrat'] animate-fade-in" style="animation-delay: 0.6s;">Our Craft in Action</h2>
            <p class="text-lg md:text-xl text-gray-300 text-center mb-12 max-w-2xl mx-auto animate-fade-in" style="animation-delay: 0.8s;">
                A glimpse into our diverse range of projects, each a testament to strategic design and creative execution.
            </p>

            <!-- Filter Options -->
            <div class="flex flex-wrap justify-center gap-4 mb-12 animate-fade-in" style="animation-delay: 1s;">
                <button class="px-6 py-2 rounded-full bg-electric-blue text-white hover:bg-coral-red transition duration-300">All</button>
                <button class="px-6 py-2 rounded-full bg-gray-700 text-white hover:bg-electric-blue transition duration-300">Brand Identity</button>
                <button class="px-6 py-2 rounded-full bg-gray-700 text-white hover:bg-electric-blue transition duration-300">Web Design</button>
                <button class="px-6 py-2 rounded-full bg-gray-700 text-white hover:bg-electric-blue transition duration-300">Print</button>
                <button class="px-6 py-2 rounded-full bg-gray-700 text-white hover:bg-electric-blue transition duration-300">Motion Graphics</button>
                <button class="px-6 py-2 rounded-full bg-gray-700 text-white hover:bg-electric-blue transition duration-300">Illustration</button>
                <button class="px-6 py-2 rounded-full bg-gray-700 text-white hover:bg-electric-blue transition duration-300">Packaging</button>
            </div>

            <div class="grid portfolio-grid gap-6 md:gap-8 auto-rows-fr">
                <!-- Portfolio Item 1: Social Media Post -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 1.2s;">
                    <img src="https://placehold.co/600x400/007bff/ffffff?text=Dynamic+Social+Post" alt="Social Media Post Mockup" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Dynamic Social Post</p>
                        <p class="text-gray-300 text-sm">Social Media, Digital Marketing</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 2: Motion Graphic Preview -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in motion-graphic-overlay" style="animation-delay: 1.4s;">
                    <img src="https://placehold.co/600x400/ff6b6b/ffffff?text=Animated+Explainer+Video" alt="Motion Graphic Mockup" class="w-full h-auto object-cover">
                    <div class="overlay-content">
                        <i class="fas fa-play-circle"></i>
                        <p class="text-white text-xl font-semibold mb-2">Animated Explainer</p>
                        <p class="text-gray-300 text-sm">Motion Graphics, Video</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 3: Logo Design 1 -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 1.6s;">
                    <img src="https://placehold.co/600x400/ffeaa7/2c3e50?text=Modern+Brand+Logo" alt="Logo Design Mockup A" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity:0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Modern Brand Logo</p>
                        <p class="text-gray-300 text-sm">Brand Identity, Logo Design</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 4: Ad Banner 1 -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 1.8s;">
                    <img src="https://placehold.co/600x400/007bff/ffffff?text=Campaign+Ad+Banner" alt="Ad Banner Mockup 1" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity:0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Campaign Ad Banner</p>
                        <p class="text-gray-300 text-sm">Digital Marketing, Ads</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 5: Branding -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 2.0s;">
                    <img src="https://placehold.co/600x400/ff6b6b/ffffff?text=Comprehensive+Branding" alt="Branding Mockup" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity:0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Comprehensive Branding</p>
                        <p class="text-gray-300 text-sm">Brand Identity, Strategy</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 6: Web Design -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 2.2s;">
                    <img src="https://placehold.co/600x400/ffeaa7/2c3e50?text=Responsive+Website+Design" alt="Website Design Mockup" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity:0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Responsive Website</p>
                        <p class="text-gray-300 text-sm">UI/UX Design, Web</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 7: Packaging Design -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 2.4s;">
                    <img src="https://placehold.co/600x400/007bff/ffffff?text=Product+Packaging" alt="Packaging Design Mockup" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity:0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Product Packaging</p>
                        <p class="text-gray-300 text-sm">Print Design, Packaging</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
                <!-- Portfolio Item 8: Illustration -->
                <div class="relative group rounded-xl overflow-hidden shadow-lg transform hover:scale-105 transition duration-300 ease-in-out bg-gray-800 animate-fade-in" style="animation-delay: 2.6s;">
                    <img src="https://placehold.co/600x400/ff6b6b/ffffff?text=Custom+Illustration" alt="Illustration Mockup" class="w-full h-auto object-cover">
                    <div class="absolute inset-0 bg-charcoal-black bg-opacity-70 flex flex-col items-center justify-center opacity:0 group-hover:opacity-100 transition-opacity duration-300 p-4 text-center">
                        <p class="text-white text-xl font-semibold mb-2">Custom Illustration</p>
                        <p class="text-gray-300 text-sm">Illustration, Digital Art</p>
                        <button class="mt-4 bg-sunshine-yellow text-charcoal-black text-sm py-2 px-4 rounded-full hover:bg-white transition duration-300">View Project</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Offered Section -->
    <section id="services" class="py-16 md:py-24 bg-gradient-section text-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-5xl font-bold text-center mb-12 font-['Montserrat'] animate-fade-in" style="animation-delay: 0.2s;">What We Bring to Your Brand</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Service 1: Brand Identity & Strategy -->
                <div class="bg-charcoal-black p-8 rounded-xl shadow-lg text-center transform hover:scale-105 transition duration-300 ease-in-out animate-fade-in" style="animation-delay: 0.4s;">
                    <i class="fas fa-lightbulb text-4xl text-sunshine-yellow mb-4 animate-bounce-hover"></i>
                    <h3 class="text-xl font-semibold mb-2">Brand Identity & Strategy</h3>
                    <p class="text-gray-300">Logo Design, Brand Guidelines, Visual Storytelling that defines your essence.</p>
                </div>
                <!-- Service 2: UI/UX Design -->
                <div class="bg-charcoal-black p-8 rounded-xl shadow-lg text-center transform hover:scale-105 transition duration-300 ease-in-out animate-fade-in" style="animation-delay: 0.6s;">
                    <i class="fas fa-desktop text-4xl text-sunshine-yellow mb-4 animate-bounce-hover"></i>
                    <h3 class="text-xl font-semibold mb-2">UI/UX Design</h3>
                    <p class="text-gray-300">Website & App Design, User Flow optimization, and interactive Prototyping.</p>
                </div>
                <!-- Service 3: Print & Editorial Design -->
                <div class="bg-charcoal-black p-8 rounded-xl shadow-lg text-center transform hover:scale-105 transition duration-300 ease-in-out animate-fade-in" style="animation-delay: 0.8s;">
                    <i class="fas fa-print text-4xl text-sunshine-yellow mb-4 animate-bounce-hover"></i>
                    <h3 class="text-xl font-semibold mb-2">Print & Editorial Design</h3>
                    <p class="text-gray-300">Brochures, Packaging, Publications, and impactful Marketing Collateral.</p>
                </div>
                <!-- Service 4: Motion Graphics & Animation -->
                <div class="bg-charcoal-black p-8 rounded-xl shadow-lg text-center transform hover:scale-105 transition duration-300 ease-in-out animate-fade-in" style="animation-delay: 1.0s;">
                    <i class="fas fa-film text-4xl text-sunshine-yellow mb-4 animate-bounce-hover"></i>
                    <h3 class="text-xl font-semibold mb-2">Motion Graphics & Animation</h3>
                    <p class="text-gray-300">Engaging Explainer Videos, dynamic Animated Logos, and captivating Social Media Content.</p>
                </div>
                <!-- Service 5: Illustration & Iconography -->
                <div class="bg-charcoal-black p-8 rounded-xl shadow-lg text-center transform hover:scale-105 transition duration-300 ease-in-out animate-fade-in" style="animation-delay: 1.2s;">
                    <i class="fas fa-pencil-ruler text-4xl text-sunshine-yellow mb-4 animate-bounce-hover"></i>
                    <h3 class="text-xl font-semibold mb-2">Illustration & Iconography</h3>
                    <p class="text-gray-300">Unique Custom Artwork, informative Infographics, and bespoke Icon Sets.</p>
                </div>
                <!-- Service 6: Digital Marketing Collateral -->
                <div class="bg-charcoal-black p-8 rounded-xl shadow-lg text-center transform hover:scale-105 transition duration-300 ease-in-out animate-fade-in" style="animation-delay: 1.4s;">
                    <i class="fas fa-bullhorn text-4xl text-sunshine-yellow mb-4 animate-bounce-hover"></i>
                    <h3 class="text-xl font-semibold mb-2">Digital Marketing Collateral</h3>
                    <p class="text-gray-300">High-impact Social Media Graphics, engaging Banner Ads, and effective Email Templates.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Client Testimonials / Social Proof -->
    <section id="testimonials" class="py-16 md:py-24 bg-charcoal-black">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-5xl font-bold text-center mb-12 text-coral-red font-['Montserrat'] animate-fade-in" style="animation-delay: 0.2s;">Voices of Our Success</h2>
            <div class="carousel-container relative max-w-4xl mx-auto rounded-xl shadow-xl overflow-hidden animate-fade-in" style="animation-delay: 0.4s;">
                <div class="carousel-slide" id="testimonial-slide">
                    <!-- Testimonial 1 -->
                    <div class="carousel-item p-8 bg-gray-800 rounded-xl text-center flex-shrink-0">
                        <img src="https://placehold.co/80x80/007bff/ffffff?text=JD" alt="Jane Doe" class="rounded-full mx-auto mb-4 border-2 border-sunshine-yellow">
                        <p class="text-lg md:text-xl italic mb-4 text-gray-200">"What an amazing experience working with Creative Vision! Their ability to capture our vision and translate it into a stunning brand identity was simply remarkable. Highly recommend!"</p>
                        <p class="font-semibold text-electric-blue">- Jane Doe, CEO of InnovateTech Solutions</p>
                        <div class="text-sunshine-yellow mt-2">
                            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                        </div>
                    </div>
                    <!-- Testimonial 2 -->
                    <div class="carousel-item p-8 bg-gray-800 rounded-xl text-center flex-shrink-0">
                        <img src="https://placehold.co/80x80/ff6b6b/ffffff?text=JS" alt="John Smith" class="rounded-full mx-auto mb-4 border-2 border-sunshine-yellow">
                        <p class="text-lg md:text-xl italic mb-4 text-gray-200">"The motion graphics they produced for us were breathtaking. We saw an immediate increase in engagement and positive feedback."</p>
                        <p class="font-semibold text-electric-blue">- John Smith, Marketing Director at Global Solutions</p>
                        <div class="text-sunshine-yellow mt-2">
                            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star-half-alt"></i>
                        </div>
                    </div>
                    <!-- Testimonial 3 -->
                    <div class="carousel-item p-8 bg-gray-800 rounded-xl text-center flex-shrink-0">
                        <img src="https://placehold.co/80x80/ffeaa7/2c3e50?text=EW" alt="Emily White" class="rounded-full mx-auto mb-4 border-2 border-sunshine-yellow">
                        <p class="text-lg md:text-xl italic mb-4 text-gray-200">"Professional, creative, and always on time. Creative Vision is our go-to for all design needs, consistently exceeding expectations."</p>
                        <p class="font-semibold text-electric-blue">- Emily White, Founder of EcoBloom Ventures</p>
                        <div class="text-sunshine-yellow mt-2">
                            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                        </div>
                    </div>
                </div>
                <button class="carousel-button prev" onclick="moveCarousel(-1)">&#10094;</button>
                <button class="carousel-button next" onclick="moveCarousel(1)">&#10095;</button>
            </div>
        </div>
    </section>

    <!-- CTA Section - Final Push -->
    <section class="py-16 md:py-24 bg-gradient-cta text-white text-center">
        <div class="container mx-auto px-4 animate-fade-in" style="animation-delay: 0.2s;">
            <h2 class="text-3xl md:text-5xl font-bold mb-8 font-['Montserrat']">Ready to Elevate Your Brand?</h2>
            <p class="text-lg md:text-xl text-gray-200 mb-10 max-w-2xl mx-auto">
                Let's discuss your next big idea. We're excited to turn your vision into a visual masterpiece.
            </p>
            <div class="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-6">
                <a href="#contact" class="bg-sunshine-yellow text-charcoal-black hover:bg-white font-bold py-4 px-10 rounded-full shadow-xl transition duration-300 ease-in-out transform hover:scale-105 animate-bounce-hover">
                    Start Your Project Today
                </a>
                <a href="#contact" class="bg-transparent border-2 border-white text-white hover:bg-white hover:text-charcoal-black font-bold py-4 px-10 rounded-full shadow-xl transition duration-300 ease-in-out transform hover:scale-105">
                    Schedule a Free Consultation
                </a>
            </div>
        </div>
    </section>

    <!-- Contact Information / Footer -->
    <footer id="contact" class="bg-charcoal-black py-16 md:py-24 text-gray-300">
        <div class="container mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-12">
            <!-- Contact Info -->
            <div>
                <h3 class="text-2xl font-bold mb-6 text-sunshine-yellow">Get In Touch</h3>
                <p class="mb-2"><i class="fas fa-envelope mr-3 text-electric-blue"></i> <a href="mailto:info@creativevision.com" class="hover:underline">info@creativevision.com</a></p>
                <p class="mb-2"><i class="fas fa-phone-alt mr-3 text-electric-blue"></i> <a href="tel:+919002614378" class="hover:underline">+91 9002614378</a></p>
                <p><i class="fas fa-map-marker-alt mr-3 text-electric-blue"></i> Kanthalpota, Krishnanagar, Nadia, West Bengal 741101, India</p>
            </div>

            <!-- Quick Links -->
            <div>
                <h3 class="text-2xl font-bold mb-6 text-sunshine-yellow">Quick Links</h3>
                <ul class="space-y-2">
                    <li><a href="#hero" class="hover:text-electric-blue transition duration-300">Home</a></li>
                    <li><a href="#portfolio" class="hover:text-electric-blue transition duration-300">Portfolio</a></li>
                    <li><a href="#about" class="hover:text-electric-blue transition duration-300">About</a></li>
                    <li><a href="#services" class="hover:text-electric-blue transition duration-300">Services</a></li>
                    <li><a href="#contact" class="hover:text-electric-blue transition duration-300">Contact</a></li>
                    <li><a href="#" class="hover:text-electric-blue transition duration-300">Privacy Policy</a></li>
                    <li><a href="#" class="hover:text-electric-blue transition duration-300">Terms of Service</a></li>
                </ul>
            </div>

            <!-- Social Media & Copyright -->
            <div class="flex flex-col items-center md:items-start">
                <h3 class="text-2xl font-bold mb-6 text-sunshine-yellow">Connect With Us</h3>
                <div class="flex space-x-6 mb-8">
                    <a href="https://www.facebook.com/Creativevision5/" target="_blank" class="text-white hover:text-electric-blue transform hover:scale-110 transition duration-300"><i class="fab fa-facebook-f text-3xl"></i></a>
                    <a href="https://www.instagram.com/creativevision048/" target="_blank" class="text-white hover:text-electric-blue transform hover:scale-110 transition duration-300"><i class="fab fa-instagram text-3xl"></i></a>
                    <a href="https://linkedin.com/yourprofile" target="_blank" class="text-white hover:text-electric-blue transform hover:scale-110 transition duration-300"><i class="fab fa-linkedin-in text-3xl"></i></a>
                    <a href="https://behance.net/yourprofile" target="_blank" class="text-white hover:text-electric-blue transform hover:scale-110 transition duration-300"><i class="fab fa-behance text-3xl"></i></a>
                    <a href="https://dribbble.com/yourprofile" target="_blank" class="text-white hover:text-electric-blue transform hover:scale-110 transition duration-300"><i class="fab fa-dribbble text-3xl"></i></a>
                </div>
                <p class="text-sm text-gray-500 mt-auto">&copy; <span id="current-year"></span> Creative Vision. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Floating WhatsApp/Phone Icon -->
    <div class="floating-contact">
        <a href="https://wa.me/919002614378" target="_blank" class="mb-4">
            <i class="fab fa-whatsapp text-3xl"></i>
        </a>
        <a href="tel:+919002614378" class="bg-electric-blue">
            <i class="fas fa-phone text-3xl"></i>
        </a>
    </div>

    <script>
        // Get current year for footer copyright
        document.getElementById('current-year').textContent = new Date().getFullYear();

        // Carousel functionality
        let currentSlide = 0;
        const slides = document.getElementById('testimonial-slide');
        const totalSlides = slides.children.length;

        function moveCarousel(direction) {
            currentSlide = (currentSlide + direction + totalSlides) % totalSlides;
            slides.style.transform = `translateX(-${currentSlide * 100}%)`;
        }

        // Auto-advance carousel
        setInterval(() => {
            moveCarousel(1);
        }, 5000); // Change slide every 5 seconds

        // Intersection Observer for fade-in animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate-fade-in');
                    // Remove the animation-delay style once animated to prevent re-triggering on scroll
                    entry.target.style.animationDelay = '';
                    observer.unobserve(entry.target); // Stop observing once animated
                }
            });
        }, { threshold: 0.1 }); // Trigger when 10% of the element is visible

        document.querySelectorAll('.animate-fade-in').forEach(element => {
            // Only observe elements that haven't been animated yet (check for animation-delay)
            if (element.style.animationDelay) {
                observer.observe(element);
            }
        });

        // Accordion functionality for "Our Process"
        function toggleAccordion(id) {
            const content = document.getElementById(id);
            const icon = document.getElementById(id + '-icon');
            if (content.classList.contains('active')) {
                content.classList.remove('active');
                content.style.maxHeight = null;
                icon.classList.remove('rotate-180');
            } else {
                content.classList.add('active');
                content.style.maxHeight = content.scrollHeight + "px"; // Set max-height to content height
                icon.classList.add('rotate-180');
            }
        }

        // Mobile Menu Toggle
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const closeMobileMenuButton = document.getElementById('close-mobile-menu');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.remove('hidden');
        });

        closeMobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.add('hidden');
        });

        function closeMobileMenu() {
            mobileMenu.classList.add('hidden');
        }
    </script>
</body>
</html>
