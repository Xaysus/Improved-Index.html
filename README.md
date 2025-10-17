<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XAYSUS | Official Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #ff4444;
            --primary-dark: #cc3333;
            --secondary: #ffaa00;
            --dark: #0a0a0a;
            --dark-light: #1a1a1a;
            --text: #fff;
            --text-light: #ccc;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: var(--dark);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            padding: 1rem 2rem;
            z-index: 1000;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .nav-links {
            display: flex;
            justify-content: center;
            list-style: none;
            gap: 3rem;
        }

        .nav-links a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--primary);
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a:hover:after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, var(--dark-light) 0%, var(--dark) 100%);
            position: relative;
            overflow: hidden;
        }

        .hero:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 30%, rgba(255, 68, 68, 0.1), transparent 70%);
        }

        .hero-content h1 {
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: var(--primary);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 68, 68, 0.4);
            position: relative;
            overflow: hidden;
        }

        .cta-button:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            background: var(--primary-dark);
            box-shadow: 0 6px 20px rgba(255, 68, 68, 0.6);
        }

        .cta-button:hover:before {
            left: 100%;
        }

        /* Music Section */
        .music-section {
            padding: 5rem 2rem;
            background: #111;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary);
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title:after {
            content: '';
            position: absolute;
            width: 60%;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--primary), transparent);
            bottom: -10px;
            left: 20%;
        }

        .music-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .track-card {
            background: var(--dark-light);
            border-radius: 15px;
            padding: 1.5rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .track-card:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .track-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 68, 68, 0.3);
        }

        .track-card:hover:before {
            transform: scaleX(1);
        }

        .track-info h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--text);
        }

        .track-info p {
            color: var(--text-light);
            margin-bottom: 1rem;
        }

        /* Custom Audio Player */
        .audio-player {
            width: 100%;
            margin-top: 1rem;
            background: #2a2a2a;
            border-radius: 50px;
            padding: 10px 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .play-pause {
            background: var(--primary);
            border: none;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            color: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .play-pause:hover {
            background: var(--primary-dark);
            transform: scale(1.05);
        }

        .progress-container {
            flex-grow: 1;
            height: 5px;
            background: #444;
            border-radius: 5px;
            cursor: pointer;
            position: relative;
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 5px;
            width: 0%;
            transition: width 0.1s linear;
        }

        .time {
            font-size: 0.8rem;
            color: var(--text-light);
            min-width: 40px;
            text-align: center;
        }

        /* About Section */
        .about-section {
            padding: 5rem 2rem;
            background: var(--dark);
            text-align: center;
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .about-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            text-align: left;
            line-height: 1.8;
        }

        /* Contact Section */
        .contact-section {
            padding: 5rem 2rem;
            background: #111;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .social-link {
            color: var(--text);
            text-decoration: none;
            padding: 0.8rem 1.5rem;
            border: 2px solid var(--primary);
            border-radius: 25px;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .social-link:hover {
            background: var(--primary);
            color: #000;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 68, 68, 0.4);
        }

        /* Footer */
        footer {
            background: var(--dark);
            padding: 2rem;
            text-align: center;
            color: #666;
        }

        /* Loading Animation */
        .loader {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: var(--primary);
            animation: spin 1s ease-in-out infinite;
            margin-right: 10px;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }

            .nav-links {
                gap: 1.5rem;
            }

            .music-grid {
                grid-template-columns: 1fr;
            }

            .social-links {
                flex-direction: column;
                align-items: center;
            }
            
            .social-link {
                width: 200px;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#music">Music</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>XAYSUS</h1>
            <p>Rapper • Producer • Creative</p>
            <a href="#music" class="cta-button">Listen Now</a>
        </div>
    </section>

    <!-- Music Section -->
    <section id="music" class="music-section">
        <h2 class="section-title">Latest Tracks</h2>
        <div class="music-grid">
            <!-- Track 1 -->
            <div class="track-card">
                <div class="track-info">
                    <h3>Midnight Vibes</h3>
                    <p>Single • 2024</p>
                    <div class="audio-player" data-src="your-track-1.mp3">
                        <button class="play-pause"><i class="fas fa-play"></i></button>
                        <div class="progress-container">
                            <div class="progress-bar"></div>
                        </div>
                        <div class="time">0:00</div>
                    </div>
                </div>
            </div>

            <!-- Track 2 -->
            <div class="track-card">
                <div class="track-info">
                    <h3>Urban Dreams</h3>
                    <p>Single • 2024</p>
                    <div class="audio-player" data-src="your-track-2.mp3">
                        <button class="play-pause"><i class="fas fa-play"></i></button>
                        <div class="progress-container">
                            <div class="progress-bar"></div>
                        </div>
                        <div class="time">0:00</div>
                    </div>
                </div>
            </div>

            <!-- Track 3 -->
            <div class="track-card">
                <div class="track-info">
                    <h3>Street Poet</h3>
                    <p>Single • 2024</p>
                    <div class="audio-player" data-src="your-track-3.mp3">
                        <button class="play-pause"><i class="fas fa-play"></i></button>
                        <div class="progress-container">
                            <div class="progress-bar"></div>
                        </div>
                        <div class="time">0:00</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about-section">
        <h2 class="section-title">About</h2>
        <div class="about-content">
            <p>XAYSUS is an innovative artist blending raw lyricism with atmospheric production. With roots in urban culture and a vision that transcends genres, XAYSUS creates music that resonates with both the streets and the soul.</p>
            <p>Drawing inspiration from life's struggles and triumphs, each track tells a story of resilience, ambition, and authenticity. From underground beginnings to growing recognition, XAYSUS remains dedicated to the craft and the message.</p>
            <p>Recent collaborations include work with emerging producers and features on popular urban music platforms, establishing XAYSUS as a voice for the new generation of hip-hop artists.</p>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section">
        <h2 class="section-title">Connect With Me</h2>
        <div class="social-links">
            <a href="#" class="social-link"><i class="fab fa-spotify"></i> Spotify</a>
            <a href="#" class="social-link"><i class="fab fa-instagram"></i> Instagram</a>
            <a href="#" class="social-link"><i class="fab fa-youtube"></i> YouTube</a>
            <a href="#" class="social-link"><i class="fab fa-soundcloud"></i> SoundCloud</a>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 XAYSUS. All rights reserved.</p>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Add scroll effect to navbar
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(10, 10, 10, 0.98)';
                navbar.style.padding = '0.8rem 2rem';
            } else {
                navbar.style.background = 'rgba(10, 10, 10, 0.95)';
                navbar.style.padding = '1rem 2rem';
            }
        });

        // Custom Audio Player Functionality
        document.querySelectorAll('.audio-player').forEach(player => {
            const playPauseBtn = player.querySelector('.play-pause');
            const progressBar = player.querySelector('.progress-bar');
            const progressContainer = player.querySelector('.progress-container');
            const timeDisplay = player.querySelector('.time');
            const audioSrc = player.getAttribute('data-src');
            
            // Create audio element
            const audio = new Audio();
            audio.src = audioSrc;
            
            let isPlaying = false;
            
            // Format time (convert seconds to mm:ss)
            function formatTime(seconds) {
                const mins = Math.floor(seconds / 60);
                const secs = Math.floor(seconds % 60);
                return `${mins}:${secs < 10 ? '0' : ''}${secs}`;
            }
            
            // Update progress bar and time
            function updateProgress() {
                const progressPercent = (audio.currentTime / audio.duration) * 100;
                progressBar.style.width = `${progressPercent}%`;
                timeDisplay.textContent = formatTime(audio.currentTime);
            }
            
            // Set progress on click
            function setProgress(e) {
                const width = this.clientWidth;
                const clickX = e.offsetX;
                const duration = audio.duration;
                
                audio.currentTime = (clickX / width) * duration;
            }
            
            // Toggle play/pause
            function togglePlay() {
                if (isPlaying) {
                    audio.pause();
                    playPauseBtn.innerHTML = '<i class="fas fa-play"></i>';
                } else {
                    audio.play();
                    playPauseBtn.innerHTML = '<i class="fas fa-pause"></i>';
                }
                isPlaying = !isPlaying;
            }
            
            // Reset player when audio ends
            audio.addEventListener('ended', () => {
                playPauseBtn.innerHTML = '<i class="fas fa-play"></i>';
                progressBar.style.width = '0%';
                timeDisplay.textContent = '0:00';
                isPlaying = false;
            });
            
            // Update progress as audio plays
            audio.addEventListener('timeupdate', updateProgress);
            
            // Set up event listeners
            playPauseBtn.addEventListener('click', togglePlay);
            progressContainer.addEventListener('click', setProgress);
            
            // Set initial time display
            audio.addEventListener('loadedmetadata', () => {
                timeDisplay.textContent = '0:00';
            });
        });
    </script>
</body>
</html>
