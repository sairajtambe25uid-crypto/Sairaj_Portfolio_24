 
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sairaj Yogesh Tambe | Portfolio</title>
    <meta name="description" content="Portfolio of Sairaj Yogesh Tambe, Integrated B.Tech Student, Aspiring Software Developer, and Event Coordinator.">
    
    <!-- Google Fonts: Poppins & Outfit -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- AOS Animation CSS -->
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#081B29',
                        secondary: '#00E5FF',
                        accent: '#00C896',
                        bgDark: '#050816',
                        white: '#FFFFFF'
                    },
                    fontFamily: {
                        poppins: ['Poppins', 'sans-serif'],
                        outfit: ['Outfit', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <style>
        /* Base & Scrollbar */
        body {
            background-color: #050816;
            color: #FFFFFF;
            overflow-x: hidden;
            font-family: 'Poppins', sans-serif;
            cursor: none; /* Hide default cursor for custom cursor */
        }
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Outfit', sans-serif;
        }
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #050816;
        }
        ::-webkit-scrollbar-thumb {
            background: #00E5FF;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00C896;
        }

        /* Text Gradients */
        .text-gradient {
            background: linear-gradient(90deg, #00E5FF, #00C896);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Glassmorphism */
        .glass {
            background: rgba(8, 27, 41, 0.4);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.3);
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 229, 255, 0.1);
            border-radius: 20px;
            transition: all 0.4s ease;
        }
        .glass-card:hover {
            transform: translateY(-10px);
            border-color: rgba(0, 229, 255, 0.5);
            box-shadow: 0 10px 30px rgba(0, 229, 255, 0.2);
        }

        /* Custom Cursor */
        .cursor-dot {
            width: 8px;
            height: 8px;
            background-color: #00E5FF;
            border-radius: 50%;
            position: fixed;
            top: 0; left: 0;
            transform: translate(-50%, -50%);
            pointer-events: none;
            z-index: 9999;
            transition: width 0.2s, height 0.2s, background-color 0.2s;
        }
        .cursor-outline {
            width: 30px;
            height: 30px;
            border: 2px solid #00C896;
            border-radius: 50%;
            position: fixed;
            top: 0; left: 0;
            transform: translate(-50%, -50%);
            pointer-events: none;
            z-index: 9998;
            transition: width 0.2s, height 0.2s, transform 0.1s;
        }

        /* Animations */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        .animate-float {
            animation: float 4s ease-in-out infinite;
        }
        
        @keyframes glowBorder {
            0% { box-shadow: 0 0 10px #00E5FF, inset 0 0 10px #00E5FF; border-color: #00E5FF; }
            50% { box-shadow: 0 0 30px #00C896, inset 0 0 30px #00C896; border-color: #00C896; }
            100% { box-shadow: 0 0 10px #00E5FF, inset 0 0 10px #00E5FF; border-color: #00E5FF; }
        }

        .profile-img-container {
            border-radius: 50%;
            padding: 8px;
            animation: glowBorder 4s infinite alternate;
            transition: transform 0.5s ease;
        }
        .profile-img-container:hover {
            transform: scale(1.05);
        }
        .profile-img {
            border-radius: 50%;
            width: 100%;
            height: 100%;
            object-fit: cover;
            border: 4px solid #050816;
        }

        /* Loading Screen */
        #loader {
            position: fixed;
            inset: 0;
            background: #050816;
            z-index: 10000;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: opacity 0.5s ease;
        }
        .spinner {
            width: 60px;
            height: 60px;
            border: 5px solid rgba(0, 229, 255, 0.2);
            border-top-color: #00E5FF;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        @keyframes spin { 100% { transform: rotate(360deg); } }

        /* Scroll Progress */
        #scroll-progress {
            position: fixed;
            top: 0; left: 0;
            width: 0%;
            height: 4px;
            background: linear-gradient(90deg, #00E5FF, #00C896);
            z-index: 9999;
            box-shadow: 0 0 10px #00E5FF;
        }

        /* Particles Canvas */
        #particles-js {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: -1;
        }

        /* Nav Link Hover */
        .nav-link {
            position: relative;
            color: #FFFFFF;
            transition: color 0.3s ease;
        }
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0; height: 2px;
            bottom: -4px; left: 0;
            background: #00E5FF;
            transition: width 0.3s ease;
        }
        .nav-link:hover::after, .nav-link.active::after {
            width: 100%;
        }
        .nav-link:hover, .nav-link.active {
            color: #00E5FF;
        }

        /* Gradient Buttons */
        .btn-gradient {
            background: linear-gradient(45deg, #00E5FF, #00C896);
            position: relative;
            z-index: 1;
            overflow: hidden;
            transition: all 0.3s ease;
        }
        .btn-gradient::before {
            content: '';
            position: absolute;
            top: 0; left: -100%;
            width: 100%; height: 100%;
            background: linear-gradient(45deg, #00C896, #00E5FF);
            z-index: -1;
            transition: all 0.4s ease;
        }
        .btn-gradient:hover::before {
            left: 0;
        }
        .btn-gradient:hover {
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.5);
            transform: translateY(-3px);
        }

        .btn-outline {
            border: 2px solid #00E5FF;
            color: #00E5FF;
            transition: all 0.3s ease;
        }
        .btn-outline:hover {
            background: rgba(0, 229, 255, 0.1);
            box-shadow: 0 0 15px rgba(0, 229, 255, 0.4);
            transform: translateY(-3px);
        }

        /* Timeline */
        .timeline-container::before {
            content: '';
            position: absolute;
            top: 0; bottom: 0; left: 24px;
            width: 2px;
            background: rgba(0, 229, 255, 0.2);
        }
        .timeline-dot {
            width: 16px; height: 16px;
            background: #00E5FF;
            border-radius: 50%;
            position: absolute;
            left: 17px;
            box-shadow: 0 0 10px #00E5FF;
        }

        /* Skill Bars */
        .skill-bar {
            height: 8px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            overflow: hidden;
        }
        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, #00E5FF, #00C896);
            border-radius: 4px;
            width: 0; /* Animated via JS/AOS */
            transition: width 1.5s ease-in-out;
            box-shadow: 0 0 10px #00E5FF;
        }
    </style>
</head>
<body class="antialiased">

    <!-- Loading Screen -->
    <div id="loader">
        <div class="flex flex-col items-center">
            <div class="spinner mb-4"></div>
            <h2 class="text-2xl font-outfit font-bold tracking-widest text-gradient">SAIRAJ</h2>
        </div>
    </div>

    <!-- Scroll Progress Bar -->
    <div id="scroll-progress"></div>

    <!-- Custom Cursor -->
    <div class="cursor-dot hidden md:block"></div>
    <div class="cursor-outline hidden md:block"></div>

    <!-- Particles Background Canvas -->
    <canvas id="particles-js"></canvas>

    <!-- Scroll to Top Button -->
    <button id="scrollToTop" class="fixed bottom-8 right-8 bg-gradient-to-r from-secondary to-accent w-12 h-12 rounded-full flex justify-center items-center text-primary text-xl opacity-0 translate-y-10 transition-all duration-300 z-50 hover:scale-110 hover:shadow-[0_0_20px_#00E5FF]">
        <i class="fa-solid fa-arrow-up"></i>
    </button>

    <!-- Navbar -->
    <header class="fixed top-0 w-full z-50 glass transition-all duration-300" id="navbar">
        <div class="container mx-auto px-6 py-4 flex justify-between items-center">
            <a href="#" class="text-2xl font-outfit font-bold tracking-wider flex items-center gap-2 cursor-hover">
                <span class="text-white">Sairaj</span><span class="text-gradient">.</span>
            </a>

            <!-- Desktop Nav -->
            <nav class="hidden md:flex gap-8 font-medium">
                <a href="#home" class="nav-link active cursor-hover">Home</a>
                <a href="#about" class="nav-link cursor-hover">About</a>
                <a href="#skills" class="nav-link cursor-hover">Skills</a>
                <a href="#experience" class="nav-link cursor-hover">Experience</a>
                <a href="#projects" class="nav-link cursor-hover">Projects</a>
                <a href="#contact" class="nav-link cursor-hover">Contact</a>
            </nav>

            <!-- Mobile Menu Btn -->
            <button class="md:hidden text-2xl text-white focus:outline-none" id="mobile-menu-btn">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>

        <!-- Mobile Nav -->
        <div class="md:hidden absolute top-full left-0 w-full glass hidden flex-col items-center py-6 gap-6 shadow-xl" id="mobile-menu">
            <a href="#home" class="mobile-link text-lg">Home</a>
            <a href="#about" class="mobile-link text-lg">About</a>
            <a href="#skills" class="mobile-link text-lg">Skills</a>
            <a href="#experience" class="mobile-link text-lg">Experience</a>
            <a href="#projects" class="mobile-link text-lg">Projects</a>
            <a href="#contact" class="mobile-link text-lg">Contact</a>
        </div>
    </header>

    <main>
        <!-- Home Section -->
        <section id="home" class="min-h-screen flex items-center justify-center pt-20 relative px-6">
            <div class="container mx-auto grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                
                <!-- Text Content -->
                <div data-aos="fade-right" data-aos-duration="1000">
                    <p class="text-secondary text-lg mb-2 font-medium">Hi, I'm</p>
                    <h1 class="text-5xl md:text-7xl font-extrabold mb-4 leading-tight">
                        SAIRAJ YOGESH <br> 
                        <span class="text-gradient">TAMBE</span>
                    </h1>
                    <h2 class="text-2xl md:text-3xl font-semibold mb-4 h-10">
                        I am a <span id="typed-text" class="text-accent"></span>
                    </h2>
                    <p class="text-gray-300 text-lg mb-8 italic border-l-4 border-secondary pl-4">
                        "Learning • Building • Leading • Growing"
                    </p>
                    <div class="flex flex-wrap gap-4">
                        <a href="resume.pdf" target="_blank" class="btn-gradient px-8 py-3 rounded-full font-semibold cursor-hover shadow-lg">
                            <i class="fa-solid fa-file-alt mr-2"></i> View Resume
                        </a>
                        <a href="#contact" class="btn-outline px-8 py-3 rounded-full font-semibold cursor-hover bg-transparent">
                            <i class="fa-solid fa-paper-plane mr-2"></i> Contact Me
                        </a>
                    </div>
                </div>

                <!-- Profile Image -->
                <div class="flex justify-center items-center" data-aos="fade-left" data-aos-duration="1000" data-aos-delay="200">
                    <div class="relative w-72 h-72 md:w-96 md:h-96 animate-float">
                        <!-- Glass frame / Glow container -->
                        <div class="profile-img-container w-full h-full glass">
                            <img src="profile.jpg" alt="Sairaj Yogesh Tambe" class="profile-img">
                        </div>
                        
                        <!-- Floating badges -->
                        <div class="absolute top-10 -left-6 glass px-4 py-2 rounded-xl border border-secondary/30 flex items-center gap-2 animate-bounce cursor-hover" style="animation-duration: 3s;">
                            <i class="fa-solid fa-code text-secondary"></i> <span class="text-sm font-medium">Developer</span>
                        </div>
                        <div class="absolute bottom-10 -right-6 glass px-4 py-2 rounded-xl border border-accent/30 flex items-center gap-2 animate-bounce cursor-hover" style="animation-duration: 4s; animation-delay: 1s;">
                            <i class="fa-solid fa-users text-accent"></i> <span class="text-sm font-medium">Leader</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Highlights -->
        <section class="py-12 relative z-10 px-6 -mt-10">
            <div class="container mx-auto grid grid-cols-2 md:grid-cols-4 gap-6">
                <!-- Card 1 -->
                <div class="glass-card p-6 text-center cursor-hover" data-aos="fade-up" data-aos-delay="0">
                    <i class="fa-solid fa-graduation-cap text-3xl text-secondary mb-3"></i>
                    <h3 class="font-bold text-lg">2nd Year</h3>
                    <p class="text-xs text-gray-400">Integrated B.Tech</p>
                </div>
                <!-- Card 2 -->
                <div class="glass-card p-6 text-center cursor-hover" data-aos="fade-up" data-aos-delay="100">
                    <i class="fa-solid fa-university text-3xl text-accent mb-3"></i>
                    <h3 class="font-bold text-lg">Sanjivani</h3>
                    <p class="text-xs text-gray-400">University Student</p>
                </div>
                <!-- Card 3 -->
                <div class="glass-card p-6 text-center cursor-hover" data-aos="fade-up" data-aos-delay="200">
                    <i class="fa-solid fa-laptop-code text-3xl text-secondary mb-3"></i>
                    <h3 class="font-bold text-lg">Software</h3>
                    <p class="text-xs text-gray-400">Developer</p>
                </div>
                <!-- Card 4 -->
                <div class="glass-card p-6 text-center cursor-hover" data-aos="fade-up" data-aos-delay="300">
                    <i class="fa-solid fa-calendar-check text-3xl text-accent mb-3"></i>
                    <h3 class="font-bold text-lg">Events</h3>
                    <p class="text-xs text-gray-400">Management</p>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="py-20 px-6 relative">
            <div class="container mx-auto">
                <div class="text-center mb-16" data-aos="fade-down">
                    <h2 class="text-4xl font-bold font-outfit mb-2">About <span class="text-gradient">Me</span></h2>
                    <div class="w-20 h-1 bg-gradient-to-r from-secondary to-accent mx-auto rounded-full"></div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                    <!-- About Text -->
                    <div class="glass-card p-8" data-aos="fade-right">
                        <h3 class="text-2xl font-semibold mb-4 text-secondary">Who am I?</h3>
                        <p class="text-gray-300 leading-relaxed mb-6">
                            I am <strong class="text-white">Sairaj Yogesh Tambe</strong>, a passionate Second-Year Integrated B.Tech student at Sanjivani University. I enjoy learning modern technologies, building web applications, participating in technical activities, managing events, and collaborating with teams. 
                        </p>
                        <p class="text-gray-300 leading-relaxed">
                            I am continuously improving my technical, communication, and leadership skills to become a successful software engineer. Bridging the gap between creative problem solving and technical implementation is what drives me everyday.
                        </p>
                    </div>

                    <!-- Education -->
                    <div class="glass-card p-8" data-aos="fade-left">
                        <h3 class="text-2xl font-semibold mb-6 text-accent flex items-center gap-3">
                            <i class="fa-solid fa-book-open"></i> Education
                        </h3>
                        <div class="relative timeline-container pl-6 py-2">
                            <div class="timeline-dot top-3"></div>
                            <h4 class="text-xl font-bold text-white">Integrated B.Tech</h4>
                            <p class="text-secondary font-medium mb-1">Second Year (Current)</p>
                            <p class="text-gray-400 text-sm">School of Engineering and Technology</p>
                            <p class="text-gray-300 mt-2 font-semibold">Sanjivani University</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="py-20 px-6 relative bg-gradient-to-b from-transparent to-[rgba(8,27,41,0.5)]">
            <div class="container mx-auto">
                <div class="text-center mb-16" data-aos="fade-down">
                    <h2 class="text-4xl font-bold font-outfit mb-2">My <span class="text-gradient">Skills</span></h2>
                    <div class="w-20 h-1 bg-gradient-to-r from-secondary to-accent mx-auto rounded-full"></div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                    
                    <!-- Technical Skills -->
                    <div data-aos="fade-right">
                        <h3 class="text-2xl font-semibold mb-6 flex items-center gap-3 text-secondary">
                            <i class="fa-solid fa-microchip"></i> Technical Skills
                        </h3>
                        
                        <div class="space-y-6 glass-card p-6">
                            <!-- Programming -->
                            <div>
                                <h4 class="text-sm font-semibold text-gray-300 mb-2">Programming (C, C++, Python)</h4>
                                <div class="skill-bar">
                                    <div class="skill-progress" data-width="85%"></div>
                                </div>
                            </div>
                            <!-- Web -->
                            <div>
                                <h4 class="text-sm font-semibold text-gray-300 mb-2">Web (HTML5, CSS3, JavaScript)</h4>
                                <div class="skill-bar">
                                    <div class="skill-progress" data-width="90%"></div>
                                </div>
                            </div>
                            <!-- Version Control -->
                            <div>
                                <h4 class="text-sm font-semibold text-gray-300 mb-2">Version Control (Git, GitHub)</h4>
                                <div class="skill-bar">
                                    <div class="skill-progress" data-width="80%"></div>
                                </div>
                            </div>
                            <!-- Tools -->
                            <div>
                                <h4 class="text-sm font-semibold text-gray-300 mb-2">Tools (Canva, Microsoft Office)</h4>
                                <div class="skill-bar">
                                    <div class="skill-progress" data-width="95%"></div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Professional Skills -->
                    <div data-aos="fade-left">
                        <h3 class="text-2xl font-semibold mb-6 flex items-center gap-3 text-accent">
                            <i class="fa-solid fa-users-gear"></i> Professional Skills
                        </h3>
                        <div class="flex flex-wrap gap-4 glass-card p-6 h-full content-start">
                            <span class="px-4 py-2 rounded-full border border-secondary/50 bg-secondary/10 text-sm hover:bg-secondary hover:text-primary transition-all duration-300 cursor-hover">Leadership</span>
                            <span class="px-4 py-2 rounded-full border border-accent/50 bg-accent/10 text-sm hover:bg-accent hover:text-primary transition-all duration-300 cursor-hover">Communication</span>
                            <span class="px-4 py-2 rounded-full border border-secondary/50 bg-secondary/10 text-sm hover:bg-secondary hover:text-primary transition-all duration-300 cursor-hover">Event Management</span>
                            <span class="px-4 py-2 rounded-full border border-accent/50 bg-accent/10 text-sm hover:bg-accent hover:text-primary transition-all duration-300 cursor-hover">Teamwork</span>
                            <span class="px-4 py-2 rounded-full border border-secondary/50 bg-secondary/10 text-sm hover:bg-secondary hover:text-primary transition-all duration-300 cursor-hover">Public Speaking</span>
                            <span class="px-4 py-2 rounded-full border border-accent/50 bg-accent/10 text-sm hover:bg-accent hover:text-primary transition-all duration-300 cursor-hover">Strategic Thinking</span>
                            <span class="px-4 py-2 rounded-full border border-secondary/50 bg-secondary/10 text-sm hover:bg-secondary hover:text-primary transition-all duration-300 cursor-hover">Problem Solving</span>
                            <span class="px-4 py-2 rounded-full border border-accent/50 bg-accent/10 text-sm hover:bg-accent hover:text-primary transition-all duration-300 cursor-hover">Critical Thinking</span>
                            <span class="px-4 py-2 rounded-full border border-secondary/50 bg-secondary/10 text-sm hover:bg-secondary hover:text-primary transition-all duration-300 cursor-hover">Time Management</span>
                            <span class="px-4 py-2 rounded-full border border-accent/50 bg-accent/10 text-sm hover:bg-accent hover:text-primary transition-all duration-300 cursor-hover">Photography</span>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Experience & Certifications -->
        <section id="experience" class="py-20 px-6 relative">
            <div class="container mx-auto">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                    
                    <!-- Experience -->
                    <div data-aos="fade-right">
                        <h2 class="text-3xl font-bold font-outfit mb-8 flex items-center gap-3">
                            <span class="text-gradient">Experience</span>
                        </h2>
                        
                        <div class="space-y-8 relative timeline-container pl-6">
                            <!-- Exp 1 -->
                            <div class="relative">
                                <div class="timeline-dot top-2"></div>
                                <div class="glass-card p-6 ml-2">
                                    <h4 class="text-xl font-bold text-white">Event Management Community</h4>
                                    <h5 class="text-secondary font-medium mb-3">Sanjivani Cha Raja</h5>
                                    <p class="text-sm text-gray-400 mb-2">Responsibilities:</p>
                                    <ul class="list-disc list-inside text-gray-300 text-sm space-y-1">
                                        <li>Event Planning & Execution</li>
                                        <li>Team Coordination</li>
                                        <li>Leadership</li>
                                    </ul>
                                </div>
                            </div>
                            
                            <!-- Exp 2 -->
                            <div class="relative">
                                <div class="timeline-dot top-2" style="background:#00C896; box-shadow:0 0 10px #00C896;"></div>
                                <div class="glass-card p-6 ml-2">
                                    <h4 class="text-xl font-bold text-white">University Induction Program</h4>
                                    <h5 class="text-accent font-medium mb-3">Core Team Member</h5>
                                    <ul class="list-disc list-inside text-gray-300 text-sm space-y-1">
                                        <li>Photography Team Member</li>
                                        <li>Discipline Committee Member</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Certifications & Achievements -->
                    <div data-aos="fade-left">
                        <h2 class="text-3xl font-bold font-outfit mb-8 flex items-center gap-3">
                            <span class="text-gradient">Achievements</span> & Certs
                        </h2>
                        
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <!-- Cert 1 -->
                            <div class="glass-card p-4 flex items-start gap-4 cursor-hover">
                                <div class="w-10 h-10 rounded-full bg-secondary/20 flex items-center justify-center text-secondary shrink-0">
                                    <i class="fa-brands fa-jira"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm font-bold text-white">Software with Jira</h4>
                                    <p class="text-xs text-gray-400">LinkedIn Learning</p>
                                </div>
                            </div>
                            <!-- Cert 2 -->
                            <div class="glass-card p-4 flex items-start gap-4 cursor-hover">
                                <div class="w-10 h-10 rounded-full bg-accent/20 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-comments"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm font-bold text-white">Communication Skills</h4>
                                    <p class="text-xs text-gray-400">Mindluster</p>
                                </div>
                            </div>
                            <!-- Cert 3 -->
                            <div class="glass-card p-4 flex items-start gap-4 cursor-hover">
                                <div class="w-10 h-10 rounded-full bg-secondary/20 flex items-center justify-center text-secondary shrink-0">
                                    <i class="fa-solid fa-robot"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm font-bold text-white">AI Impact Summit 2026</h4>
                                    <p class="text-xs text-gray-400">Participant / Upskill India</p>
                                </div>
                            </div>
                            <!-- Cert 4 -->
                            <div class="glass-card p-4 flex items-start gap-4 cursor-hover">
                                <div class="w-10 h-10 rounded-full bg-accent/20 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-chess-knight"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm font-bold text-white">Chess Competition</h4>
                                    <p class="text-xs text-gray-400">Participant</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="py-20 px-6 relative bg-gradient-to-b from-[rgba(8,27,41,0.5)] to-transparent">
            <div class="container mx-auto">
                <div class="text-center mb-16" data-aos="fade-down">
                    <h2 class="text-4xl font-bold font-outfit mb-2">Featured <span class="text-gradient">Projects</span></h2>
                    <div class="w-20 h-1 bg-gradient-to-r from-secondary to-accent mx-auto rounded-full"></div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    
                    <!-- Project 1 -->
                    <div class="glass-card overflow-hidden group" data-aos="fade-up" data-aos-delay="0">
                        <div class="h-48 overflow-hidden relative">
                            <!-- Image placeholder -->
                            <img src="https://placehold.co/600x400/081b29/00e5ff?text=Portfolio+Website" alt="Portfolio Website" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                            <div class="absolute inset-0 bg-primary/40 group-hover:bg-transparent transition-all duration-300"></div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-bold mb-2 text-white group-hover:text-secondary transition-colors">Personal Portfolio Website</h3>
                            <p class="text-gray-400 text-sm mb-4 line-clamp-3">A premium, modern, fully responsive personal portfolio website with Glassmorphism UI, smooth scroll animations, and interactive elements to showcase skills and projects.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-secondary">HTML/CSS</span>
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-secondary">JavaScript</span>
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-secondary">Tailwind</span>
                            </div>
                            <div class="flex gap-4">
                                <a href="#" class="btn-outline flex-1 text-center py-2 rounded-lg text-sm font-semibold cursor-hover"><i class="fa-brands fa-github"></i> Code</a>
                                <a href="#" class="btn-gradient flex-1 text-center py-2 rounded-lg text-sm font-semibold cursor-hover"><i class="fa-solid fa-external-link-alt"></i> Live</a>
                            </div>
                        </div>
                    </div>

                    <!-- Project 2 -->
                    <div class="glass-card overflow-hidden group" data-aos="fade-up" data-aos-delay="100">
                        <div class="h-48 overflow-hidden relative">
                            <img src="https://placehold.co/600x400/081b29/00c896?text=Student+Mgmt+System" alt="Student Management System" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                            <div class="absolute inset-0 bg-primary/40 group-hover:bg-transparent transition-all duration-300"></div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-bold mb-2 text-white group-hover:text-accent transition-colors">Student Management System</h3>
                            <p class="text-gray-400 text-sm mb-4 line-clamp-3">A comprehensive system developed to manage student records, attendance, and performance metrics efficiently for educational institutions.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-accent">Python</span>
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-accent">MySQL</span>
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-accent">UI/UX</span>
                            </div>
                            <div class="flex gap-4">
                                <a href="#" class="btn-outline flex-1 text-center py-2 rounded-lg text-sm font-semibold cursor-hover" style="border-color:#00C896; color:#00C896;"><i class="fa-brands fa-github"></i> Code</a>
                                <a href="#" class="btn-gradient flex-1 text-center py-2 rounded-lg text-sm font-semibold cursor-hover"><i class="fa-solid fa-external-link-alt"></i> Live</a>
                            </div>
                        </div>
                    </div>

                    <!-- Project 3 -->
                    <div class="glass-card overflow-hidden group" data-aos="fade-up" data-aos-delay="200">
                        <div class="h-48 overflow-hidden relative">
                            <img src="https://placehold.co/600x400/081b29/ffffff?text=Event+Mgmt+System" alt="Event Management System" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                            <div class="absolute inset-0 bg-primary/40 group-hover:bg-transparent transition-all duration-300"></div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-bold mb-2 text-white group-hover:text-secondary transition-colors">Event Management System</h3>
                            <p class="text-gray-400 text-sm mb-4 line-clamp-3">A robust platform built to streamline the planning, registration, and coordination of university and corporate events.</p>
                            <div class="flex flex-wrap gap-2 mb-6">
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-white">C++</span>
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-white">Data Structures</span>
                                <span class="text-xs px-2 py-1 bg-white/10 rounded-md text-white">Logic</span>
                            </div>
                            <div class="flex gap-4">
                                <a href="#" class="btn-outline flex-1 text-center py-2 rounded-lg text-sm font-semibold cursor-hover"><i class="fa-brands fa-github"></i> Code</a>
                                <a href="#" class="btn-gradient flex-1 text-center py-2 rounded-lg text-sm font-semibold cursor-hover"><i class="fa-solid fa-external-link-alt"></i> Live</a>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="py-20 px-6 relative">
            <div class="container mx-auto">
                <div class="text-center mb-16" data-aos="fade-down">
                    <h2 class="text-4xl font-bold font-outfit mb-2">Get In <span class="text-gradient">Touch</span></h2>
                    <div class="w-20 h-1 bg-gradient-to-r from-secondary to-accent mx-auto rounded-full"></div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 max-w-6xl mx-auto items-center">
                    
                    <!-- Contact Form (UI) -->
                    <div class="glass-card p-8" data-aos="fade-right">
                        <h3 class="text-2xl font-bold mb-6 text-white">Send a Message</h3>
                        <form class="space-y-4" onsubmit="event.preventDefault(); alert('Form submitted successfully!');">
                            <div>
                                <input type="text" placeholder="Your Name" class="w-full bg-white/5 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-secondary focus:ring-1 focus:ring-secondary transition-all cursor-hover" required>
                            </div>
                            <div>
                                <input type="email" placeholder="Your Email" class="w-full bg-white/5 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-secondary focus:ring-1 focus:ring-secondary transition-all cursor-hover" required>
                            </div>
                            <div>
                                <textarea rows="4" placeholder="Your Message" class="w-full bg-white/5 border border-white/10 rounded-lg px-4 py-3 text-white focus:outline-none focus:border-secondary focus:ring-1 focus:ring-secondary transition-all cursor-hover resize-none" required></textarea>
                            </div>
                            <button type="submit" class="btn-gradient w-full py-3 rounded-lg font-bold text-lg cursor-hover">
                                Send Message <i class="fa-solid fa-paper-plane ml-2"></i>
                            </button>
                        </form>
                    </div>

                    <!-- Contact Info -->
                    <div class="space-y-8" data-aos="fade-left">
                        <p class="text-gray-300 text-lg leading-relaxed mb-8">
                            Whether you want to discuss a project, talk about event management, or just say hi, my inbox is always open. Let's connect and build something awesome together!
                        </p>
                        
                        <div class="flex flex-col gap-6">
                            <!-- Email -->
                            <a href="mailto:sairaj.tambe_25uid@sanjivani.edu.in" target="_blank" class="flex items-center gap-4 group cursor-hover w-fit">
                                <div class="w-12 h-12 rounded-full glass flex justify-center items-center text-xl text-secondary group-hover:bg-secondary group-hover:text-primary group-hover:shadow-[0_0_15px_#00E5FF] transition-all duration-300">
                                    <i class="fa-solid fa-envelope"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm text-gray-400">Email</h4>
                                    <p class="text-white font-medium group-hover:text-secondary transition-colors break-all">sairaj.tambe_25uid@sanjivani.edu.in</p>
                                </div>
                            </a>

                            <!-- Phone -->
                            <a href="tel:+919834823397" class="flex items-center gap-4 group cursor-hover w-fit">
                                <div class="w-12 h-12 rounded-full glass flex justify-center items-center text-xl text-accent group-hover:bg-accent group-hover:text-primary group-hover:shadow-[0_0_15px_#00C896] transition-all duration-300">
                                    <i class="fa-solid fa-phone"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm text-gray-400">Phone</h4>
                                    <p class="text-white font-medium group-hover:text-accent transition-colors">+91 98348 23397</p>
                                </div>
                            </a>
                        </div>

                        <!-- Socials -->
                        <div class="pt-6 border-t border-white/10 flex gap-4">
                            <a href="https://github.com/sairajtambe25uid-crypto" target="_blank" class="w-12 h-12 rounded-full glass flex justify-center items-center text-xl text-white hover:bg-white hover:text-primary hover:shadow-[0_0_15px_#FFFFFF] transition-all duration-300 cursor-hover">
                                <i class="fa-brands fa-github"></i>
                            </a>
                            <a href="https://www.instagram.com/sairaj_tambe_7933" target="_blank" class="w-12 h-12 rounded-full glass flex justify-center items-center text-xl text-pink-500 hover:bg-pink-500 hover:text-white hover:shadow-[0_0_15px_#ec4899] transition-all duration-300 cursor-hover">
                                <i class="fa-brands fa-instagram"></i>
                            </a>
                            <a href="https://www.linkedin.com/in/sairaj-tambe-502999419" target="_blank" class="w-12 h-12 rounded-full glass flex justify-center items-center text-xl text-blue-500 hover:bg-blue-500 hover:text-white hover:shadow-[0_0_15px_#3b82f6] transition-all duration-300 cursor-hover" title="LinkedIn">
                                <i class="fa-brands fa-linkedin-in"></i>
                            </a>
                        </div>
                        
                        <!-- Resume Download -->
                        <div class="pt-4" id="resume">
                            <a href="resume.pdf" download="Sairaj_Tambe_Resume.pdf" target="_blank" class="inline-flex items-center gap-2 btn-outline px-6 py-3 rounded-full font-semibold cursor-hover">
                                <i class="fa-solid fa-download"></i> Download Resume
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="py-8 border-t border-white/10 bg-[#02040a] relative z-10 text-center">
        <p class="text-gray-400 font-poppins">
            &copy; 2026 | Designed and Developed by <span class="text-gradient font-bold">Sairaj Yogesh Tambe</span>
        </p>
    </footer>

    <!-- Scripts -->
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script src="https://unpkg.com/typed.js@2.1.0/dist/typed.umd.js"></script>
    
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            // 1. Loading Screen
            setTimeout(() => {
                const loader = document.getElementById('loader');
                loader.style.opacity = '0';
                setTimeout(() => { loader.style.display = 'none'; }, 500);
            }, 1500);

            // 2. Initialize AOS Animation
            AOS.init({
                once: true,
                offset: 50,
                duration: 800,
                easing: 'ease-in-out'
            });

            // 3. Typed.js
            var typed = new Typed('#typed-text', {
                strings: ['Integrated B.Tech Student', 'Aspiring Software Developer', 'Event Coordinator', 'Tech Enthusiast', 'Team Leader'],
                typeSpeed: 50,
                backSpeed: 30,
                backDelay: 1500,
                loop: true
            });

            // 4. Custom Cursor
            const cursorDot = document.querySelector('.cursor-dot');
            const cursorOutline = document.querySelector('.cursor-outline');
            
            // Only activate custom cursor on non-touch devices
            if (window.matchMedia("(pointer: fine)").matches) {
                window.addEventListener('mousemove', (e) => {
                    const posX = e.clientX;
                    const posY = e.clientY;

                    cursorDot.style.left = `${posX}px`;
                    cursorDot.style.top = `${posY}px`;

                    cursorOutline.animate({
                        left: `${posX}px`,
                        top: `${posY}px`
                    }, { duration: 500, fill: "forwards" });
                });

                // Hover effect for links and buttons
                const hoverElements = document.querySelectorAll('.cursor-hover, a, button, input, textarea');
                hoverElements.forEach(el => {
                    el.addEventListener('mouseenter', () => {
                        cursorOutline.style.width = '50px';
                        cursorOutline.style.height = '50px';
                        cursorOutline.style.backgroundColor = 'rgba(0, 229, 255, 0.1)';
                    });
                    el.addEventListener('mouseleave', () => {
                        cursorOutline.style.width = '30px';
                        cursorOutline.style.height = '30px';
                        cursorOutline.style.backgroundColor = 'transparent';
                    });
                });
            }

            // 5. Scroll Progress Bar & Sticky Nav & Scroll to Top
            const scrollProgress = document.getElementById('scroll-progress');
            const navbar = document.getElementById('navbar');
            const scrollToTopBtn = document.getElementById('scrollToTop');
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-link');

            window.addEventListener('scroll', () => {
                // Progress bar
                const scrollTop = document.documentElement.scrollTop;
                const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
                const scrollPercent = (scrollTop / scrollHeight) * 100;
                scrollProgress.style.width = `${scrollPercent}%`;

                // Navbar styling
                if (scrollTop > 50) {
                    navbar.classList.add('shadow-lg', 'bg-opacity-90');
                    navbar.style.padding = '10px 0';
                } else {
                    navbar.classList.remove('shadow-lg', 'bg-opacity-90');
                    navbar.style.padding = '16px 0';
                }

                // Scroll to top button
                if (scrollTop > 500) {
                    scrollToTopBtn.classList.remove('opacity-0', 'translate-y-10');
                    scrollToTopBtn.classList.add('opacity-100', 'translate-y-0');
                } else {
                    scrollToTopBtn.classList.add('opacity-0', 'translate-y-10');
                    scrollToTopBtn.classList.remove('opacity-100', 'translate-y-0');
                }

                // Active Nav Link
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    const sectionHeight = section.clientHeight;
                    if (scrollTop >= (sectionTop - 200)) {
                        current = section.getAttribute('id');
                    }
                });

                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href') === `#${current}`) {
                        link.classList.add('active');
                    }
                });
            });

            // Scroll to top action
            scrollToTopBtn.addEventListener('click', () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // 6. Mobile Menu Toggle
            const menuBtn = document.getElementById('mobile-menu-btn');
            const mobileMenu = document.getElementById('mobile-menu');
            const mobileLinks = document.querySelectorAll('.mobile-link');

            menuBtn.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
                mobileMenu.classList.toggle('flex');
            });

            mobileLinks.forEach(link => {
                link.addEventListener('click', () => {
                    mobileMenu.classList.add('hidden');
                    mobileMenu.classList.remove('flex');
                });
            });

            // 7. Animate Skill Bars on scroll
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if(entry.isIntersecting) {
                        const progress = entry.target.querySelector('.skill-progress');
                        if(progress) {
                            progress.style.width = progress.getAttribute('data-width');
                        }
                    }
                });
            });
            document.querySelectorAll('.skill-bar').forEach(bar => {
                observer.observe(bar);
            });

            // 8. Particle Background Animation
            const canvas = document.getElementById('particles-js');
            const ctx = canvas.getContext('2d');
            let particlesArray;

            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;

            window.addEventListener('resize', () => {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
                initParticles();
            });

            class Particle {
                constructor(x, y, directionX, directionY, size, color) {
                    this.x = x;
                    this.y = y;
                    this.directionX = directionX;
                    this.directionY = directionY;
                    this.size = size;
                    this.color = color;
                }
                draw() {
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2, false);
                    ctx.fillStyle = this.color;
                    ctx.fill();
                }
                update() {
                    if (this.x > canvas.width || this.x < 0) {
                        this.directionX = -this.directionX;
                    }
                    if (this.y > canvas.height || this.y < 0) {
                        this.directionY = -this.directionY;
                    }
                    this.x += this.directionX;
                    this.y += this.directionY;
                    this.draw();
                }
            }

            function initParticles() {
                particlesArray = [];
                let numberOfParticles = (canvas.height * canvas.width) / 15000;
                for (let i = 0; i < numberOfParticles; i++) {
                    let size = (Math.random() * 2) + 1;
                    let x = (Math.random() * ((innerWidth - size * 2) - (size * 2)) + size * 2);
                    let y = (Math.random() * ((innerHeight - size * 2) - (size * 2)) + size * 2);
                    let directionX = (Math.random() * 0.4) - 0.2;
                    let directionY = (Math.random() * 0.4) - 0.2;
                    let color = Math.random() > 0.5 ? 'rgba(0, 229, 255, 0.2)' : 'rgba(0, 200, 150, 0.2)';
                    
                    particlesArray.push(new Particle(x, y, directionX, directionY, size, color));
                }
            }

            function animateParticles() {
                requestAnimationFrame(animateParticles);
                ctx.clearRect(0, 0, innerWidth, innerHeight);
                for (let i = 0; i < particlesArray.length; i++) {
                    particlesArray[i].update();
                }
                connectParticles();
            }

            function connectParticles() {
                let opacityValue = 1;
                for (let a = 0; a < particlesArray.length; a++) {
                    for (let b = a; b < particlesArray.length; b++) {
                        let distance = ((particlesArray[a].x - particlesArray[b].x) * (particlesArray[a].x - particlesArray[b].x))
                            + ((particlesArray[a].y - particlesArray[b].y) * (particlesArray[a].y - particlesArray[b].y));
                        if (distance < (canvas.width / 7) * (canvas.height / 7)) {
                            opacityValue = 1 - (distance / 15000);
                            ctx.strokeStyle = `rgba(0, 229, 255, ${opacityValue * 0.15})`;
                            ctx.lineWidth = 1;
                            ctx.beginPath();
                            ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
                            ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
                            ctx.stroke();
                        }
                    }
                }
            }

            initParticles();
            animateParticles();
        });
    </script>
</body>
</html>
