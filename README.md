<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Verification Human</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&display=swap');

        :root {
            --primary-color: #3498db;
            --secondary-color: #e74c3c;
            --background-color: #ecf0f1;
            --text-color: #2c3e50;
            --shadow-color: rgba(0, 0, 0, 0.1);
        }

        body {
            margin: 0;
            padding: 0;
            font-family: 'Montserrat', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: var(--background-color);
            overflow: hidden;
        }

        .container {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 50px;
            box-shadow: 0 15px 35px var(--shadow-color);
            max-width: 550px;
            width: 90%;
            text-align: center;
            position: relative;
            z-index: 10;
            overflow: hidden;
            backdrop-filter: blur(10px);
        }

        .container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, var(--primary-color) 0%, transparent 70%);
            opacity: 0.1;
            z-index: -1;
            animation: pulse 15s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        h2 {
            color: var(--primary-color);
            font-size: 36px;
            margin-bottom: 30px;
            position: relative;
            display: inline-block;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--secondary-color);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .container:hover h2::after {
            transform: scaleX(1);
        }

        .question {
            font-size: 24px;
            color: var(--text-color);
            margin-bottom: 40px;
            font-weight: 600;
            position: relative;
            padding-bottom: 15px;
        }

        .question::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 2px;
            background-color: var(--primary-color);
        }

        .answer-options {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 25px;
        }

        .answer-option {
            background-color: var(--primary-color);
            color: white;
            padding: 18px 35px;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 18px;
            width: 80%;
            max-width: 300px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }

        .answer-option::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(120deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: all 0.5s;
        }

        .answer-option:hover::before {
            left: 100%;
        }

        .answer-option:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 25px rgba(52, 152, 219, 0.4);
        }

        .animated-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.7;
        }

        .particle {
            position: absolute;
            border-radius: 50%;
            background-color: var(--primary-color);
            opacity: 0.3;
            animation: float 20s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); }
            25% { transform: translateY(-100px) translateX(50px); }
            50% { transform: translateY(-50px) translateX(-50px); }
            75% { transform: translateY(-150px) translateX(100px); }
        }

        @media (max-width: 600px) {
            .container {
                padding: 40px;
            }

            h2 {
                font-size: 30px;
            }

            .question {
                font-size: 20px;
            }

            .answer-option {
                font-size: 16px;
                padding: 15px 30px;
            }
        }
    </style>
</head>
<body>
    <div class="animated-background" id="particles"></div>

    <div class="container">
        <h2><i class="fas fa-user-shield"></i> Verification Human</h2>
        <div class="question">Apakah Anda fans Bayern Munchen?</div>
        <div class="answer-options">
            <div class="answer-option" onclick="selectOption(this, 'gabut.html')">
                <i class="fas fa-thumbs-up"></i> Iya, saya fans berat
            </div>
            <div class="answer-option" onclick="selectOption(this, 'bar.html')">
                <i class="fas fa-times"></i> Tidak, saya fans Barcelona
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
    <script>
        // Particle animation
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            particle.style.width = `${Math.random() * 10 + 5}px`;
            particle.style.height = particle.style.width;
            particle.style.left = `${Math.random() * 100}vw`;
            particle.style.top = `${Math.random() * 100}vh`;
            particle.style.animationDuration = `${Math.random() * 10 + 10}s`;
            particle.style.animationDelay = `${Math.random() * 5}s`;
            particlesContainer.appendChild(particle);
        }

        // GSAP animations
        gsap.from('.container', {duration: 1, opacity: 0, y: 50, ease: 'power3.out'});
        gsap.from('.answer-option', {duration: 0.8, opacity: 0, y: 20, stagger: 0.2, ease: 'power3.out', delay: 0.5});

        // Option selection animation
        function selectOption(element, url) {
            gsap.to(element, {
                duration: 0.3,
                scale: 0.95,
                backgroundColor: '#2ecc71',
                onComplete: () => {
                    window.location.href = url;
                }
            });
        }

        // Hover animations
        const options = document.querySelectorAll('.answer-option');
        options.forEach(option => {
            option.addEventListener('mouseenter', () => {
                gsap.to(option, {duration: 0.3, scale: 1.05, y: -5});
            });
            option.addEventListener('mouseleave', () => {
                gsap.to(option, {duration: 0.3, scale: 1, y: 0});
            });
        });
    </script>
</body>
</html>
