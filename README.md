<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Bio</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'JetBrains Mono', monospace;
            background: linear-gradient(135deg, #0d1117 0%, #161b22 50%, #21262d 100%);
            color: #f0f6fc;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
        }
        
        .header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .name {
            font-size: 2.5rem;
            font-weight: 700;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { filter: drop-shadow(0 0 5px rgba(255, 107, 107, 0.3)); }
            to { filter: drop-shadow(0 0 20px rgba(78, 205, 196, 0.5)); }
        }
        
        .title {
            font-size: 1.2rem;
            color: #8b949e;
            margin-bottom: 1rem;
        }
        
        .typing-text {
            font-size: 1rem;
            color: #4ecdc4;
            border-right: 2px solid #4ecdc4;
            padding-right: 5px;
            animation: typing 4s steps(40, end) infinite, blink-caret 1s step-end infinite;
            white-space: nowrap;
            overflow: hidden;
        }
        
        @keyframes typing {
            0% { width: 0; }
            50% { width: 100%; }
            100% { width: 0; }
        }
        
        @keyframes blink-caret {
            0%, 50% { border-color: transparent; }
            51%, 100% { border-color: #4ecdc4; }
        }
        
        .interests-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }
        
        .interest-card {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 2rem;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        .interest-card:hover {
            transform: translateY(-10px);
            border-color: #4ecdc4;
            box-shadow: 0 10px 30px rgba(78, 205, 196, 0.2);
        }
        
        .interest-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(78, 205, 196, 0.1), transparent);
            transition: 0.5s;
        }
        
        .interest-card:hover::before {
            left: 100%;
        }
        
        .card-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }
        
        .japanese { color: #ff6b6b; }
        .linux { color: #4ecdc4; }
        .coffee { color: #d4af37; }
        
        .card-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: #f0f6fc;
        }
        
        .card-description {
            color: #8b949e;
            line-height: 1.6;
            margin-bottom: 1rem;
        }
        
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }
        
        .tech-tag {
            background: linear-gradient(45deg, #30363d, #21262d);
            color: #f0f6fc;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            border: 1px solid #4ecdc4;
            transition: all 0.3s ease;
        }
        
        .tech-tag:hover {
            background: rgba(78, 205, 196, 0.2);
            transform: scale(1.05);
        }
        
        .stats-section {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 2rem;
            margin: 2rem 0;
            text-align: center;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
            margin-top: 1rem;
        }
        
        .stat-item {
            padding: 1rem;
        }
        
        .stat-number {
            font-size: 2rem;
            font-weight: 700;
            color: #4ecdc4;
        }
        
        .stat-label {
            color: #8b949e;
            font-size: 0.9rem;
        }
        
        .terminal {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 1rem;
            font-family: 'JetBrains Mono', monospace;
            margin: 2rem 0;
            overflow-x: auto;
        }
        
        .terminal-header {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }
        
        .terminal-btn {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }
        
        .btn-red { background: #ff5f56; }
        .btn-yellow { background: #ffbd2e; }
        .btn-green { background: #27ca3f; }
        
        .terminal-content {
            color: #4ecdc4;
        }
        
        .prompt {
            color: #ff6b6b;
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin: 2rem 0;
        }
        
        .contact-link {
            background: rgba(33, 38, 45, 0.8);
            border: 1px solid #30363d;
            color: #f0f6fc;
            text-decoration: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .contact-link:hover {
            border-color: #4ecdc4;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(78, 205, 196, 0.2);
        }
        
        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .floating-element {
            position: absolute;
            opacity: 0.1;
            animation: float-random 10s linear infinite;
        }
        
        @keyframes float-random {
            0% { transform: translateY(100vh) rotate(0deg); }
            100% { transform: translateY(-100vh) rotate(360deg); }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-element" style="left: 10%; animation-delay: -2s; font-size: 2rem;">🍃</div>
        <div class="floating-element" style="left: 20%; animation-delay: -4s; font-size: 1.5rem;">⚡</div>
        <div class="floating-element" style="left: 80%; animation-delay: -6s; font-size: 2.5rem;">🐧</div>
        <div class="floating-element" style="left: 70%; animation-delay: -8s; font-size: 1.8rem;">☕</div>
        <div class="floating-element" style="left: 40%; animation-delay: -1s; font-size: 2rem;">🌸</div>
    </div>

    <div class="container">
        <header class="header">
            <div class="profile-img">👨‍💻</div>
            <h1 class="name">Your Name</h1>
            <p class="title">Code Craftsman • Linux Enthusiast • Coffee Artist</p>
            <div class="typing-text">printf("Hello, World! ようこそ");</div>
        </header>

        <div class="terminal">
            <div class="terminal-header">
                <div class="terminal-btn btn-red"></div>
                <div class="terminal-btn btn-yellow"></div>
                <div class="terminal-btn btn-green"></div>
            </div>
            <div class="terminal-content">
                <span class="prompt">user@arch</span>:~$ whoami<br>
                Passionate developer who loves clean code, perfect coffee, and cozy anime moments ☕🌸<br>
                <span class="prompt">user@arch</span>:~$ ls interests/<br>
                japanese-culture/  linux-systems/  coffee-brewing/  anime/  open-source/<br>
                <span class="prompt">user@arch</span>:~$ cat philosophy.txt<br>
                "Code like poetry, brew like art, live like adventure, chill like anime"
            </div>
        </div>

        <div class="interests-grid">
            <div class="interest-card">
                <span class="card-icon japanese">🎌</span>
                <h3 class="card-title">Japanese Culture</h3>
                <p class="card-description">
                    Fascinated by Japanese aesthetics, philosophy, and technology. 
                    Learning the language and exploring the beautiful intersection of tradition and innovation.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">日本語学習</span>
                    <span class="tech-tag">Anime</span>
                    <span class="tech-tag">Philosophy</span>
                    <span class="tech-tag">Design</span>
                </div>
            </div>

            <div class="interest-card">
                <span class="card-icon linux">🐧</span>
                <h3 class="card-title">Arch Linux</h3>
                <p class="card-description">
                    BTW, I use Arch! Love the minimalism, control, and philosophy. 
                    Always tinkering with configs and exploring the depths of the Linux ecosystem.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">i3wm</span>
                    <span class="tech-tag">Vim</span>
                    <span class="tech-tag">Terminal</span>
                    <span class="tech-tag">Shell Scripting</span>
                </div>
            </div>

            <div class="interest-card">
                <span class="card-icon coffee">☕</span>
                <h3 class="card-title">Barista Life</h3>
                <p class="card-description">
                    Crafting perfect espresso shots and latte art by day. 
                    The precision and artistry of coffee making mirrors the elegance of clean code.
                </p>
                <div class="tech-stack">
                    <span class="tech-tag">Espresso</span>
                    <span class="tech-tag">Latte Art</span>
                    <span class="tech-tag">Pour Over</span>
                    <span class="tech-tag">Coffee Science</span>
                </div>
            </div>
        </div>

        <div class="stats-section">
            <h3 style="color: #4ecdc4; margin-bottom: 1rem;">⚡ Quick Stats</h3>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number">∞</div>
                    <div class="stat-label">Cups of Coffee</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">24/7</div>
                    <div class="stat-label">Arch Uptime Goal</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">漢字</div>
                    <div class="stat-label">Learning Kanji</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">KISS</div>
                    <div class="stat-label">Code Philosophy</div>
                </div>
            </div>
        </div>

        <div class="contact-links">
            <a href="#" class="contact-link">
                <span>📧</span> Email
            </a>
            <a href="#" class="contact-link">
                <span>💼</span> LinkedIn
            </a>
            <a href="#" class="contact-link">
                <span>🌐</span> Portfolio
            </a>
            <a href="#" class="contact-link">
                <span>📱</span> Twitter
            </a>
        </div>

        <div class="terminal" style="text-align: center;">
            <div class="terminal-content">
                <span class="prompt">user@arch</span>:~$ fortune<br>
                "The best code is written with coffee in hand and Arch in heart"<br>
                <span class="prompt">user@arch</span>:~$ exit<br>
                Thanks for visiting! がんばって！ ☕🐧🎌
            </div>
        </div>
    </div>

    <script>
        // Add some interactive elements
        document.addEventListener('DOMContentLoaded', function() {
            // Create more floating elements dynamically
            const floatingContainer = document.querySelector('.floating-elements');
            const symbols = ['⚡', '🐧', '☕', '🌸', '🎌', '💻', '🍃'];
            
            setInterval(() => {
                if (document.querySelectorAll('.floating-element').length < 15) {
                    const element = document.createElement('div');
                    element.className = 'floating-element';
                    element.textContent = symbols[Math.floor(Math.random() * symbols.length)];
                    element.style.left = Math.random() * 100 + '%';
                    element.style.fontSize = (Math.random() * 2 + 1) + 'rem';
                    element.style.animationDelay = '-' + Math.random() * 10 + 's';
                    floatingContainer.appendChild(element);
                    
                    setTimeout(() => {
                        element.remove();
                    }, 10000);
                }
            }, 3000);
            
            // Add hover effects to cards
            document.querySelectorAll('.interest-card').forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.background = 'rgba(78, 205, 196, 0.05)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.background = 'rgba(33, 38, 45, 0.8)';
                });
            });
        });
    </script>
</body>
</html>
