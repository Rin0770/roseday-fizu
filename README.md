# roseday-fizu
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌹 For My Fizu 🦋</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --rose-dark: #8B0A50;
            --rose-primary: #E91E63;
            --rose-light: #F8BBD9;
            --rose-pale: #FCE4EC;
            --gold: #FFD700;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #1a0a0f 0%, #2d0a1a 50%, #1a0510 100%);
            min-height: 100vh;
            overflow-x: hidden;
            color: white;
        }

        /* Floating Elements */
        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }

        .floating-item {
            position: absolute;
            animation: floatUp linear infinite;
            opacity: 0.7;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% { opacity: 0.7; }
            90% { opacity: 0.7; }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--rose-primary);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--rose-primary), 0 0 20px var(--rose-primary);
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
        }

        .butterfly {
            position: absolute;
            font-size: 1.8rem;
            animation: flyButterfly 20s ease-in-out infinite;
        }

        @keyframes flyButterfly {
            0%, 100% { transform: translate(0, 0) rotateY(0deg); }
            25% { transform: translate(150px, -80px) rotateY(180deg); }
            50% { transform: translate(80px, -150px) rotateY(0deg); }
            75% { transform: translate(-80px, -60px) rotateY(180deg); }
        }

        /* Screens */
        .screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            z-index: 10;
            text-align: center;
            overflow-y: auto;
        }

        .screen.active {
            display: flex;
        }

        /* Welcome Screen */
        #welcomeScreen {
            background: radial-gradient(circle at center, rgba(233, 30, 99, 0.2) 0%, transparent 70%);
        }

        .welcome-rose {
            font-size: 10rem;
            animation: pulse 2s infinite, glowRose 2s infinite;
            cursor: pointer;
            transition: transform 0.3s;
            filter: drop-shadow(0 0 30px rgba(233, 30, 99, 0.8));
        }

        .welcome-rose:hover {
            transform: scale(1.2) rotate(10deg);
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        @keyframes glowRose {
            0%, 100% { filter: drop-shadow(0 0 30px rgba(233, 30, 99, 0.8)); }
            50% { filter: drop-shadow(0 0 60px rgba(255, 107, 157, 1)) drop-shadow(0 0 80px rgba(233, 30, 99, 0.8)); }
        }

        .welcome-title {
            font-family: 'Great Vibes', cursive;
            font-size: 4rem;
            background: linear-gradient(45deg, #ff6b9d, #FFD700, #ff6b9d, #FFD700);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: shimmer 3s infinite;
            margin-top: 20px;
            text-shadow: 0 0 30px rgba(255, 215, 0, 0.3);
        }

        @keyframes shimmer {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .tap-hint {
            font-size: 1.3rem;
            color: var(--rose-light);
            margin-top: 30px;
            animation: fadeInOut 2s infinite;
        }

        @keyframes fadeInOut {
            0%, 100% { opacity: 0.5; transform: translateY(0); }
            50% { opacity: 1; transform: translateY(-5px); }
        }

        .loading-hearts {
            display: flex;
            gap: 15px;
            margin-top: 25px;
        }

        .loading-heart {
            font-size: 1.8rem;
            animation: bounce 1.4s infinite ease-in-out;
        }

        .loading-heart:nth-child(1) { animation-delay: 0s; }
        .loading-heart:nth-child(2) { animation-delay: 0.2s; }
        .loading-heart:nth-child(3) { animation-delay: 0.4s; }

        @keyframes bounce {
            0%, 80%, 100% { transform: scale(1); }
            40% { transform: scale(1.4); }
        }

        /* Headlines Screen */
        #headlinesScreen {
            background: radial-gradient(circle at center, rgba(233, 30, 99, 0.15) 0%, transparent 70%);
            padding: 30px 15px;
        }

        .headlines-title {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            color: var(--gold);
            margin-bottom: 40px;
            text-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
            animation: slideDown 1s ease;
        }

        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .headlines-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            max-width: 1200px;
            width: 100%;
        }

        .headline-card {
            background: linear-gradient(135deg, rgba(233, 30, 99, 0.25), rgba(139, 10, 80, 0.35));
            border: 2px solid rgba(233, 30, 99, 0.4);
            border-radius: 25px;
            padding: 30px 25px;
            backdrop-filter: blur(10px);
            animation: cardAppear 0.8s ease forwards;
            opacity: 0;
            transform: translateY(50px) scale(0.9);
            transition: all 0.3s;
        }

        .headline-card:hover {
            transform: translateY(-5px) scale(1.02);
            border-color: var(--gold);
            box-shadow: 0 10px 40px rgba(233, 30, 99, 0.3);
        }

        .headline-card:nth-child(1) { animation-delay: 0.2s; }
        .headline-card:nth-child(2) { animation-delay: 0.4s; }
        .headline-card:nth-child(3) { animation-delay: 0.6s; }
        .headline-card:nth-child(4) { animation-delay: 0.8s; }

        @keyframes cardAppear {
            to { opacity: 1; transform: translateY(0) scale(1); }
        }

        .headline-card .icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .headline-card h3 {
            font-family: 'Dancing Script', cursive;
            font-size: 1.6rem;
            color: var(--gold);
            margin-bottom: 15px;
        }

        .headline-card p {
            font-size: 1rem;
            line-height: 1.9;
            color: #fff;
        }

        .continue-btn {
            margin-top: 50px;
            padding: 18px 60px;
            font-size: 1.4rem;
            font-family: 'Dancing Script', cursive;
            background: linear-gradient(135deg, var(--rose-primary), var(--rose-dark));
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            animation: cardAppear 0.8s ease 1s forwards;
            opacity: 0;
            box-shadow: 0 8px 35px rgba(233, 30, 99, 0.5);
        }

        .continue-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 15px 50px rgba(233, 30, 99, 0.7);
        }

        /* Game Screen */
        #gameScreen {
            background: radial-gradient(circle at center, rgba(233, 30, 99, 0.2) 0%, transparent 70%);
        }

        .game-container {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .game-heart {
            font-size: 6rem;
            animation: heartbeat 1s infinite;
            margin-bottom: 30px;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            25% { transform: scale(1.1); }
            50% { transform: scale(1); }
            75% { transform: scale(1.15); }
        }

        .game-question {
            font-family: 'Great Vibes', cursive;
            font-size: 3.5rem;
            color: var(--rose-light);
            margin-bottom: 50px;
            text-shadow: 0 0 30px rgba(233, 30, 99, 0.5);
            animation: slideDown 1s ease;
        }

        .game-buttons {
            display: flex;
            gap: 40px;
            align-items: center;
            justify-content: center;
            flex-wrap: wrap;
            min-height: 150px;
        }

        .game-btn {
            padding: 22px 65px;
            font-size: 1.6rem;
            font-family: 'Poppins', sans-serif;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .yes-btn {
            background: linear-gradient(135deg, #4CAF50, #2E7D32);
            color: white;
            box-shadow: 0 8px 35px rgba(76, 175, 80, 0.5);
        }

        .yes-btn:hover {
            box-shadow: 0 15px 50px rgba(76, 175, 80, 0.7);
        }

        .no-btn {
            background: linear-gradient(135deg, #f44336, #c62828);
            color: white;
            box-shadow: 0 8px 35px rgba(244, 67, 54, 0.5);
            transition: all 0.2s;
        }

        .game-message {
            margin-top: 40px;
            font-size: 1.4rem;
            color: var(--rose-light);
            min-height: 30px;
            opacity: 0;
            transition: all 0.3s;
        }

        .game-message.show {
            opacity: 1;
        }

        /* Heart Burst Animation */
        .heart-burst {
            position: fixed;
            font-size: 3rem;
            animation: burstUp 1.5s ease forwards;
            pointer-events: none;
            z-index: 1000;
        }

        @keyframes burstUp {
            0% { opacity: 1; transform: scale(0) rotate(0deg); }
            50% { opacity: 1; transform: scale(1.3) rotate(180deg); }
            100% { opacity: 0; transform: scale(0.5) rotate(360deg) translateY(-200px); }
        }

        /* Messages Screen */
        #messagesScreen {
            background: radial-gradient(circle at center, rgba(233, 30, 99, 0.15) 0%, transparent 70%);
            justify-content: flex-start;
            padding-top: 50px;
        }

        .messages-container {
            max-width: 650px;
            width: 100%;
            padding: 20px;
        }

        .message-box {
            background: linear-gradient(135deg, rgba(233, 30, 99, 0.2), rgba(139, 10, 80, 0.3));
            border: 2px solid rgba(233, 30, 99, 0.4);
            border-radius: 25px;
            padding: 35px 30px;
            margin-bottom: 25px;
            backdrop-filter: blur(10px);
            animation: messageSlide 0.8s ease forwards;
            opacity: 0;
            transform: translateX(-50px);
        }

        @keyframes messageSlide {
            to { opacity: 1; transform: translateX(0); }
        }

        .message-box h3 {
            font-family: 'Great Vibes', cursive;
            font-size: 2rem;
            color: var(--gold);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .message-box p {
            font-size: 1.1rem;
            line-height: 2.1;
            color: #fff;
            white-space: pre-line;
        }

        .message-divider {
            text-align: center;
            font-size: 2.5rem;
            margin: 15px 0;
            animation: pulse 1.5s infinite;
        }

        /* Motivation Screen */
        #motivationScreen {
            background: radial-gradient(circle at center, rgba(255, 215, 0, 0.1) 0%, transparent 70%);
        }

        .motivation-box {
            max-width: 600px;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.08), rgba(255, 215, 0, 0.12));
            border: 3px solid rgba(255, 215, 0, 0.4);
            border-radius: 30px;
            padding: 45px 35px;
            backdrop-filter: blur(15px);
            animation: scaleIn 1s ease;
            box-shadow: 0 0 50px rgba(255, 215, 0, 0.2);
        }

        @keyframes scaleIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        .motivation-box .stars {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .motivation-box h3 {
            font-family: 'Great Vibes', cursive;
            font-size: 2.8rem;
            color: var(--gold);
            margin-bottom: 30px;
        }

        .motivation-box p {
            font-size: 1.25rem;
            line-height: 2.3;
            color: #fff;
            white-space: pre-line;
        }

        /* Final Screen */
        #finalScreen {
            background: radial-gradient(circle at center, rgba(233, 30, 99, 0.25) 0%, transparent 70%);
        }

        .final-message {
            max-width: 700px;
            background: linear-gradient(135deg, rgba(233, 30, 99, 0.2), rgba(139, 10, 80, 0.35));
            border: 3px solid rgba(255, 215, 0, 0.5);
            border-radius: 35px;
            padding: 50px 40px;
            backdrop-filter: blur(15px);
            animation: finalReveal 1.5s ease;
            box-shadow: 0 0 60px rgba(233, 30, 99, 0.4), 0 0 100px rgba(255, 215, 0, 0.2);
        }

        @keyframes finalReveal {
            0% { opacity: 0; transform: scale(0.5) rotate(-10deg); }
            60% { transform: scale(1.05) rotate(3deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        .final-message h2 {
            font-family: 'Great Vibes', cursive;
            font-size: 3.5rem;
            background: linear-gradient(45deg, var(--gold), #fff, var(--gold), #fff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: shimmer 2s infinite;
            margin-bottom: 35px;
        }

        .final-message p {
            font-size: 1.2rem;
            line-height: 2.3;
            color: #fff;
            white-space: pre-line;
        }

        .final-rose {
            font-size: 6rem;
            margin-top: 35px;
            animation: pulse 1.5s infinite, glowRose 2s infinite;
        }

        .signature {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            background: linear-gradient(45deg, var(--rose-light), var(--gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-top: 30px;
        }

        /* Confetti */
        .confetti {
            position: fixed;
            animation: confettiFall 4s linear forwards;
            z-index: 1000;
            pointer-events: none;
        }

        @keyframes confettiFall {
            0% { transform: translateY(-20px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .welcome-title {
                font-size: 2.8rem;
            }

            .welcome-rose {
                font-size: 7rem;
            }

            .headlines-title {
                font-size: 2.2rem;
            }

            .headline-card {
                padding: 25px 20px;
            }

            .game-question {
                font-size: 2.3rem;
            }

            .game-btn {
                padding: 18px 45px;
                font-size: 1.3rem;
            }

            .motivation-box, .final-message {
                padding: 35px 25px;
                margin: 0 15px;
            }

            .final-message h2 {
                font-size: 2.5rem;
            }

            .final-message p, .motivation-box p {
                font-size: 1.05rem;
            }

            .signature {
                font-size: 2.2rem;
            }

            .continue-btn {
                padding: 15px 45px;
                font-size: 1.2rem;
            }
        }

        @media (max-width: 400px) {
            .welcome-title {
                font-size: 2.2rem;
            }

            .welcome-rose {
                font-size: 5rem;
            }

            .game-question {
                font-size: 1.8rem;
            }

            .game-buttons {
                gap: 20px;
            }

            .game-btn {
                padding: 15px 35px;
                font-size: 1.1rem;
            }
        }

        /* Audio Button */
        .audio-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--rose-primary), var(--rose-dark));
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 100;
            box-shadow: 0 5px 25px rgba(233, 30, 99, 0.5);
            transition: all 0.3s;
        }

        .audio-btn:hover {
            transform: scale(1.1);
        }

        /* Special Effects */
        .sparkle {
            position: fixed;
            width: 10px;
            height: 10px;
            background: var(--gold);
            border-radius: 50%;
            pointer-events: none;
            animation: sparkleAnim 1s ease forwards;
            box-shadow: 0 0 10px var(--gold), 0 0 20px var(--gold);
        }

        @keyframes sparkleAnim {
            0% { transform: scale(0); opacity: 1; }
            100% { transform: scale(2); opacity: 0; }
        }
    </style>
</head>
<body>
    <!-- Floating Elements -->
    <div class="floating-elements" id="floatingElements"></div>

    <!-- Audio Button -->
    <button class="audio-btn" id="audioBtn" onclick="toggleMusic()">🎵</button>

    <!-- Screen 1: Welcome -->
    <div class="screen active" id="welcomeScreen">
        <div class="welcome-rose" onclick="goToHeadlines()">🌹</div>
        <h1 class="welcome-title">For You, My Fizu 🦋</h1>
        <p class="tap-hint">✨ Touch the rose to open your surprise 💝</p>
        <div class="loading-hearts">
            <span class="loading-heart">💕</span>
            <span class="loading-heart">🌹</span>
            <span class="loading-heart">💕</span>
        </div>
    </div>

    <!-- Screen 2: Headlines -->
    <div class="screen" id="headlinesScreen">
        <h2 class="headlines-title">🌹 Happy Rose Day Fizu 🦋</h2>
        <div class="headlines-grid">
            <div class="headline-card">
         
