# Terraflux
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TerraFlux | Opening Soon</title>
    <style>
        /* Style Global */
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #fcfcfc; /* Fond clair uni */
            color: #1a1a1a;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }

        /* Conteneur Central */
        .main-container {
            text-align: center;
            z-index: 1;
        }

        /* Logo */
        .logo {
            width: 280px; /* Taille du logo */
            margin-bottom: 40px;
            display: block;
            margin-left: auto;
            margin-right: auto;
        }

        /* Texte Principal */
        h1 {
            font-size: 3rem;
            font-weight: 800;
            letter-spacing: 5px;
            margin: 10px 0;
            color: #1a1a1a;
        }

        p {
            font-size: 1.2rem;
            color: #666;
            letter-spacing: 2px;
            margin-bottom: 50px;
        }

        /* Compte à rebours */
        #countdown {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 20px;
        }

        .countdown-item {
            display: flex;
            flex-direction: column;
        }

        .number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #2ecc71; /* Vert TerraFlux */
        }

        .label {
            font-size: 0.8rem;
            text-transform: uppercase;
            color: #999;
        }

        /* Bas de page (Noms) */
        .footer-names {
            position: absolute;
            bottom: 30px;
            right: 40px;
            text-align: right;
            font-size: 0.9rem;
            line-height: 1.6;
            color: #888;
            border-right: 3px solid #2ecc71;
            padding-right: 15px;
        }

        /* Décoration subtile */
        .bg-accent {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, #2ecc71, #27ae60);
        }
    </style>
</head>
<body>

    <div class="bg-accent"></div>

    <div class="main-container">
        <img src="image_ae113a.png" alt="TerraFlux Logo" class="logo">
        
        <h1>OPENING SOON</h1>
        <p>STAY TUNED</p>

        <div id="countdown">
            <div class="countdown-item">
                <span class="number" id="days">00</span>
                <span class="label">Jours</span>
            </div>
            <div class="countdown-item">
                <span class="number" id="hours">00</span>
                <span class="label">Heures</span>
            </div>
            <div class="countdown-item">
                <span class="number" id="minutes">00</span>
                <span class="label">Min</span>
            </div>
            <div class="countdown-item">
                <span class="number" id="seconds">00</span>
                <span class="label">Sec</span>
            </div>
        </div>
    </div>

    <div class="footer-names">
        Milo Candilon<br>
        Nelson Saint Gabriel<br>
        Xavier Garrigue<br>
        Marin Hainglaise
    </div>

    <script>
        // Configuration du compte à rebours (45 jours à partir de maintenant)
        const targetDate = new Date();
        targetDate.setDate(targetDate.getDate() + 45);

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = targetDate - now;

            const d = Math.floor(distance / (1000 * 60 * 60 * 24));
            const h = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const m = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const s = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerHTML = d.toString().padStart(2, '0');
            document.getElementById("hours").innerHTML = h.toString().padStart(2, '0');
            document.getElementById("minutes").innerHTML = m.toString().padStart(2, '0');
            document.getElementById("seconds").innerHTML = s.toString().padStart(2, '0');

            if (distance < 0) {
                clearInterval(interval);
                document.getElementById("countdown").innerHTML = "WELCOME TO TERRAFLUX";
            }
        }

        const interval = setInterval(updateCountdown, 1000);
        updateCountdown();
    </script>
</body>
</html>
