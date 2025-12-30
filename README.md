<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Año 2026 - By Bety🇺🇾</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0a1a2d, #1a0b2e, #002635);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: white;
            overflow-x: hidden;
            padding: 20px;
        }
        
        .container {
            text-align: center;
            max-width: 900px;
            width: 100%;
        }
        
        .header {
            margin-bottom: 40px;
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #ffd700, #ff6b6b, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.2);
        }
        
        .subtitle {
            font-size: 1.3rem;
            color: #a0a0ff;
            max-width: 600px;
            margin: 0 auto 30px;
            line-height: 1.6;
        }
        
        /* Área principal */
        .main-content {
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
            justify-content: center;
            align-items: flex-start;
            margin: 40px 0;
        }
        
        /* Caja de regalo */
        .gift-box-container {
            position: relative;
            width: 320px;
            height: 320px;
        }
        
        .gift-box {
            position: relative;
            width: 100%;
            height: 100%;
            cursor: pointer;
            transition: transform 0.5s ease;
        }
        
        .gift-box:hover {
            transform: scale(1.03);
        }
        
        .box-body {
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #d35400, #e67e22, #f39c12);
            border-radius: 15px;
            box-shadow: 
                inset 0 -10px 20px rgba(0, 0, 0, 0.4),
                0 15px 30px rgba(0, 0, 0, 0.5);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .box-body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent 30%, rgba(255, 255, 255, 0.2) 50%, transparent 70%);
            background-size: 200% 200%;
            animation: shine 3s infinite linear;
        }
        
        @keyframes shine {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
        }
        
        /* Decoración de la caja */
        .ribbon-vertical {
            position: absolute;
            width: 35px;
            height: 100%;
            background: linear-gradient(to right, #c0392b, #e74c3c, #c0392b);
            left: 50%;
            transform: translateX(-50%);
            border-radius: 5px;
            box-shadow: 0 0 15px rgba(231, 76, 60, 0.7);
        }
        
        .ribbon-horizontal {
            position: absolute;
            width: 100%;
            height: 35px;
            background: linear-gradient(to bottom, #c0392b, #e74c3c, #c0392b);
            top: 50%;
            transform: translateY(-50%);
            border-radius: 5px;
            box-shadow: 0 0 15px rgba(231, 76, 60, 0.7);
        }
        
        /* Lazo */
        .bow {
            position: absolute;
            top: -40px;
            left: 50%;
            transform: translateX(-50%);
            width: 120px;
            height: 90px;
            z-index: 10;
        }
        
        .bow-left, .bow-right {
            position: absolute;
            width: 60px;
            height: 60px;
            background: #c0392b;
            border-radius: 50%;
            top: 0;
        }
        
        .bow-left {
            left: 0;
            background: radial-gradient(circle at 30% 30%, #e74c3c, #c0392b);
        }
        
        .bow-right {
            right: 0;
            background: radial-gradient(circle at 70% 30%, #e74c3c, #c0392b);
        }
        
        .bow-center {
            position: absolute;
            width: 50px;
            height: 50px;
            background: #c0392b;
            border-radius: 50%;
            top: 15px;
            left: 50%;
            transform: translateX(-50%);
            background: radial-gradient(circle at center, #e74c3c, #c0392b);
            box-shadow: 0 0 20px rgba(231, 76, 60, 0.8);
        }
        
        /* Área del mensaje */
        .message-container {
            flex: 1;
            min-width: 300px;
            max-width: 500px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.8s ease;
            border: 3px solid #e74c3c;
        }
        
        .message-container.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .message-title {
            color: #e74c3c;
            font-size: 2.2rem;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .message-content {
            font-size: 1.4rem;
            color: #2c3e50;
            line-height: 1.7;
            text-align: center;
            margin-bottom: 25px;
        }
        
        .year-display {
            font-size: 4rem;
            font-weight: bold;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 20px 0;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
        }
        
        .wishes-list {
            list-style: none;
            margin: 20px 0;
            text-align: left;
        }
        
        .wishes-list li {
            margin: 12px 0;
            font-size: 1.2rem;
            color: #2c3e50;
            padding-left: 30px;
            position: relative;
        }
        
        .wishes-list li:before {
            content: "✨";
            position: absolute;
            left: 0;
            top: 0;
        }
        
        /* FIRMA - NUEVO ELEMENTO */
        .signature {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 2px solid #e74c3c;
            text-align: center;
        }
        
        .signature-text {
            font-size: 1.8rem;
            font-weight: bold;
            color: #2c3e50;
            background: linear-gradient(90deg, #0038a8, #ffffff, #fcd116);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            padding: 10px 20px;
            border-radius: 10px;
            display: inline-block;
            animation: signature-glow 3s infinite alternate;
        }
        
        @keyframes signature-glow {
            0% { text-shadow: 0 0 5px rgba(0, 56, 168, 0.5); }
            100% { text-shadow: 0 0 15px rgba(252, 209, 22, 0.7); }
        }
        
        /* Botones */
        .controls {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 30px;
            flex-wrap: wrap;
        }
        
        .control-btn {
            padding: 18px 35px;
            font-size: 1.3rem;
            background: linear-gradient(90deg, #4ecdc4, #45b7d1);
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .control-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 25px rgba(0, 0, 0, 0.3);
        }
        
        .control-btn:active {
            transform: translateY(-2px);
        }
        
        #openBtn {
            background: linear-gradient(90deg, #e74c3c, #c0392b);
        }
        
        #newMessageBtn {
            background: linear-gradient(90deg, #ffd700, #f39c12);
        }
        
        /* Confeti */
        .confetti {
            position: absolute;
            width: 12px;
            height: 12px;
            opacity: 0;
            pointer-events: none;
        }
        
        .confetti.active {
            animation: fall 5s linear forwards;
        }
        
        @keyframes fall {
            0% {
                transform: translateY(-100px) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(1000px) rotate(720deg);
                opacity: 0;
            }
        }
        
        /* Instrucción */
        .instruction {
            color: #ffd93d;
            font-size: 1.2rem;
            margin-top: 20px;
            animation: pulse 2s infinite;
            text-align: center;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; }
        }
        
        /* Mensaje de bienvenida */
        .welcome-message {
            max-width: 700px;
            margin: 40px auto 30px;
            padding: 25px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            border-left: 5px solid #4ecdc4;
        }
        
        .welcome-message p {
            font-size: 1.2rem;
            line-height: 1.7;
            margin-bottom: 15px;
        }
        
        /* Pie de página con firma */
        footer {
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            width: 100%;
            text-align: center;
        }
        
        .footer-signature {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(90deg, #0038a8, #ffffff, #fcd116);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            padding: 15px 30px;
            border-radius: 15px;
            display: inline-block;
            margin-bottom: 10px;
            animation: footer-signature 4s infinite alternate;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        @keyframes footer-signature {
            0% { 
                transform: scale(1);
                background: linear-gradient(90deg, #0038a8, #ffffff, #fcd116);
            }
            50% { 
                transform: scale(1.05);
                background: linear-gradient(90deg, #fcd116, #ffffff, #0038a8);
            }
            100% { 
                transform: scale(1);
                background: linear-gradient(90deg, #0038a8, #ffffff, #fcd116);
            }
        }
        
        .footer-text {
            color: #a0a0ff;
            font-size: 1rem;
            margin-top: 10px;
        }
        
        /* Efectos de brillo */
        .glow {
            position: absolute;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(78, 205, 196, 0.3), transparent 70%);
            border-radius: 50%;
            filter: blur(40px);
            z-index: -1;
            animation: glow-pulse 4s infinite alternate;
        }
        
        @keyframes glow-pulse {
            0% { opacity: 0.3; transform: scale(0.8); }
            100% { opacity: 0.7; transform: scale(1.2); }
        }
        
        /* Responsive */
        @media (max-width: 900px) {
            .main-content {
                flex-direction: column;
                align-items: center;
            }
            
            .message-container {
                max-width: 90%;
            }
        }
        
        @media (max-width: 768px) {
            h1 { font-size: 2.5rem; }
            .subtitle { font-size: 1.1rem; }
            .gift-box-container { transform: scale(0.9); }
            .message-title { font-size: 1.8rem; }
            .year-display { font-size: 3rem; }
            .message-content { font-size: 1.2rem; }
            .control-btn { padding: 15px 25px; font-size: 1.1rem; }
            .footer-signature { font-size: 1.6rem; padding: 12px 20px; }
            .signature-text { font-size: 1.5rem; }
        }
        
        @media (max-width: 480px) {
            h1 { font-size: 2rem; }
            .gift-box-container { transform: scale(0.8); }
            .message-container { padding: 20px; }
            .controls { flex-direction: column; align-items: center; }
            .control-btn { width: 100%; max-width: 250px; }
            .footer-signature { font-size: 1.4rem; padding: 10px 15px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Efecto de brillo -->
        <div class="glow" style="top: 10%; left: 10%;"></div>
        <div class="glow" style="bottom: 10%; right: 10%; background: radial-gradient(circle, rgba(255, 107, 107, 0.3), transparent 70%);"></div>
        
        <div class="header">
            <h1><i class="fas fa-star"></i> Feliz Año 2026 <i class="fas fa-star"></i></h1>
            <p class="subtitle">Que este nuevo año esté lleno de bendiciones, alegrías y momentos inolvidables. ¡Toca la caja para abrir tu regalo especial!</p>
        </div>
        
        <div class="main-content">
            <!-- Caja de regalo -->
            <div class="gift-box-container">
                <!-- Confeti -->
                <div id="confettiContainer"></div>
                
                <!-- Caja de regalo -->
                <div class="gift-box" id="giftBox">
                    <div class="box-body">
                        <!-- Decoración de la caja -->
                        <div class="ribbon-vertical"></div>
                        <div class="ribbon-horizontal"></div>
                        
                        <!-- Lazo -->
                        <div class="bow">
                            <div class="bow-left"></div>
                            <div class="bow-center"></div>
                            <div class="bow-right"></div>
                        </div>
                        
                        <!-- Mensaje dentro de la caja -->
                        <div style="position: relative; z-index: 5; color: white; text-align: center; padding: 20px;">
                            <h3 style="margin-bottom: 10px; font-size: 1.8rem;">🎁 ¡Tócame!</h3>
                            <p style="font-size: 1.3rem;">Haz clic o toca la caja para abrir tu mensaje especial</p>
                            <div style="margin-top: 20px; animation: bounce 2s infinite;">
                                <i class="fas fa-hand-point-up" style="font-size: 2.5rem;"></i>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Contenedor del mensaje -->
            <div class="message-container" id="messageContainer">
                <h2 class="message-title" id="messageTitle">
                    <i class="fas fa-heart" style="color:#e74c3c"></i> ¡Feliz Año 2026!
                </h2>
                
                <div class="message-content" id="messageContent">
                    Que este nuevo año te traiga salud, felicidad y éxito en todos tus proyectos. 
                    Que cada día esté lleno de momentos inolvidables y razones para sonreír.
                </div>
                
                <div class="year-display" id="yearDisplay">2026</div>
                
                <ul class="wishes-list" id="wishesList">
                    <li>Salud y energía renovada</li>
                    <li>Amor y momentos inolvidables</li>
                    <li>Éxito en todos tus proyectos</li>
                    <li>Nuevas oportunidades y crecimiento</li>
                    <li>Paz interior y bienestar</li>
                </ul>
                
                <div class="message-content">
                    <strong>¡Que todos tus sueños se hagan realidad!</strong>
                </div>
                
                <!-- FIRMA DENTRO DEL MENSAJE -->
                <div class="signature">
                    <div class="signature-text" id="signatureText">
                        By Bety🇺🇾
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Instrucción -->
        <p class="instruction">
            <i class="fas fa-hand-point-down"></i> ¡Toca la caja de regalo para abrir tu mensaje especial!
        </p>
        
        <!-- Controles -->
        <div class="controls">
            <button class="control-btn" id="openBtn">
                <i class="fas fa-gift"></i>
                <span id="btnText">Abrir Regalo</span>
            </button>
            <button class="control-btn" id="newMessageBtn">
                <i class="fas fa-sync-alt"></i>
                <span>Nuevo Mensaje</span>
            </button>
        </div>
        
        <!-- Mensaje de bienvenida -->
        <div class="welcome-message">
            <p>✨ <strong>Que el 2026 sea un año de crecimiento personal</strong>, donde cada día sea una nueva oportunidad para aprender, amar y vivir plenamente.</p>
            <p>🌟 <strong>Que encuentres paz interior</strong> y la fuerza para superar cualquier obstáculo que se presente en tu camino.</p>
            <p>💫 <strong>Que compartas risas y momentos especiales</strong> con las personas que más quieres, creando recuerdos que durarán para siempre.</p>
            <p>🎊 <strong>¡Feliz Año 2026!</strong> Que este año supere todas tus expectativas y te llene de bendiciones.</p>
        </div>
        
        <!-- PIE DE PÁGINA CON FIRMA -->
        <footer>
            <div class="footer-signature">
                By Bety🇺🇾
            </div>
            <p class="footer-text">Con cariño desde Uruguay By Bety 🇺🇾 | Diseño especial para el Año Nuevo 2026</p>
        </footer>
    </div>

    <script>
        // Elementos del DOM
        const giftBox = document.getElementById('giftBox');
        const openBtn = document.getElementById('openBtn');
        const btnText = document.getElementById('btnText');
        const messageContainer = document.getElementById('messageContainer');
        const messageTitle = document.getElementById('messageTitle');
        const messageContent = document.getElementById('messageContent');
        const wishesList = document.getElementById('wishesList');
        const yearDisplay = document.getElementById('yearDisplay');
        const newMessageBtn = document.getElementById('newMessageBtn');
        const signatureText = document.getElementById('signatureText');
        const confettiContainer = document.getElementById('confettiContainer');
        
        // Estado
        let isOpen = false;
        let messageCount = 0;
        
        // Mensajes de felicitación
        const messages = [
            {
                title: "¡Feliz Año 2026!",
                content: "Que este nuevo año te traiga salud, felicidad y éxito en todos tus proyectos. Que cada día esté lleno de momentos inolvidables y razones para sonreír.",
                wishes: [
                    "Salud y energía renovada",
                    "Amor y momentos inolvidables",
                    "Éxito en todos tus proyectos",
                    "Nuevas oportunidades y crecimiento",
                    "Paz interior y bienestar"
                ]
            },
            {
                title: "Bendiciones para el 2026",
                content: "Que el próximo año esté lleno de momentos inolvidables, crecimiento personal y mucha alegría compartida con tus seres queridos.",
                wishes: [
                    "Risas y alegría constante",
                    "Logros profesionales",
                    "Amistades verdaderas",
                    "Tiempo para lo que amas",
                    "Satisfacción personal"
                ]
            },
            {
                title: "Nuevos Comienzos",
                content: "El 2026 es una página en blanco. ¡Escribe una historia maravillosa! Llena cada día con amor, aprendizaje y experiencias significativas.",
                wishes: [
                    "Nuevas metas alcanzadas",
                    "Aprendizajes valiosos",
                    "Experiencias enriquecedoras",
                    "Crecimiento espiritual",
                    "Equilibrio en tu vida"
                ]
            },
            {
                title: "Éxito y Prosperidad",
                content: "Que el 2026 te traiga oportunidades increíbles, logros profesionales y la satisfacción de ver tus metas cumplidas una a una.",
                wishes: [
                    "Oportunidades únicas",
                    "Reconocimiento por tu trabajo",
                    "Estabilidad económica",
                    "Desarrollo profesional",
                    "Innovación en tus proyectos"
                ]
            },
            {
                title: "Amor y Felicidad",
                content: "Que este año encuentres amor en cada momento, paz en tu corazón y razones para sonreír cada día. ¡Feliz 2026!",
                wishes: [
                    "Amor verdadero",
                    "Tiempo en familia",
                    "Amigos para siempre",
                    "Razones para sonreír",
                    "Corazón en paz"
                ]
            }
        ];
        
        // Emojis para las listas
        const emojis = ["✨", "❤️", "🚀", "🌟", "🎯", "🤗", "💪", "🌈", "🎉", "💫"];
        
        // Función para crear confeti
        function createConfetti() {
            // Limpiar confeti anterior
            confettiContainer.innerHTML = '';
            
            // Colores del confeti (incluyendo colores de la bandera de Uruguay)
            const colors = ['#0038a8', '#ffffff', '#fcd116', '#ff6b6b', '#4ecdc4', '#45b7d1', '#ffd166', '#06d6a0'];
            
            // Crear 250 partículas de confeti
            for (let i = 0; i < 250; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                
                // Posición aleatoria
                confetti.style.left = `${Math.random() * 100}%`;
                
                // Color aleatorio
                const color = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.backgroundColor = color;
                
                // Tamaño aleatorio
                const size = Math.random() * 15 + 8;
                confetti.style.width = `${size}px`;
                confetti.style.height = `${size}px`;
                
                // Forma aleatoria
                const shapes = ['50%', '0', '30%'];
                confetti.style.borderRadius = shapes[Math.floor(Math.random() * shapes.length)];
                
                // Retardo de animación aleatorio
                confetti.style.animationDelay = `${Math.random() * 2}s`;
                
                confettiContainer.appendChild(confetti);
                
                // Activar la animación
                setTimeout(() => {
                    confetti.classList.add('active');
                }, 50);
            }
        }
        
        // Función para mostrar un mensaje aleatorio
        function showRandomMessage() {
            const randomIndex = Math.floor(Math.random() * messages.length);
            const message = messages[randomIndex];
            
            // Barajar emojis
            const shuffledEmojis = [...emojis].sort(() => Math.random() - 0.5);
            
            // Actualizar el mensaje
            messageTitle.innerHTML = `<i class="fas fa-heart" style="color:#e74c3c"></i> ${message.title}`;
            messageContent.textContent = message.content;
            
            // Actualizar la lista de deseos con emojis diferentes
            let wishesHTML = '';
            message.wishes.forEach((wish, index) => {
                const emoji = shuffledEmojis[index % shuffledEmojis.length];
                wishesHTML += `<li>${emoji} ${wish}</li>`;
            });
            wishesList.innerHTML = wishesHTML;
            
            // Contador de mensajes
            messageCount++;
            
            // Efecto de animación en el año
            yearDisplay.style.transform = 'scale(1.3)';
            setTimeout(() => {
                yearDisplay.style.transform = 'scale(1)';
            }, 300);
            
            // Efecto en la firma
            signatureText.style.transform = 'scale(1.2)';
            signatureText.style.background = 'linear-gradient(90deg, #fcd116, #ffffff, #0038a8)';
            setTimeout(() => {
                signatureText.style.transform = 'scale(1)';
                signatureText.style.background = 'linear-gradient(90deg, #0038a8, #ffffff, #fcd116)';
            }, 500);
        }
        
        // Función para abrir/cerrar el mensaje
        function toggleMessage() {
            isOpen = !isOpen;
            
            if (isOpen) {
                // Mostrar el mensaje
                messageContainer.classList.add('show');
                btnText.textContent = 'Cerrar Mensaje';
                openBtn.innerHTML = '<i class="fas fa-times"></i><span>Cerrar Mensaje</span>';
                
                // Crear confeti
                createConfetti();
                
                // Mostrar un mensaje aleatorio (solo la primera vez o aleatoriamente)
                if (messageCount === 0 || Math.random() > 0.3) {
                    showRandomMessage();
                }
                
                // Efecto de vibración en dispositivos móviles
                if (navigator.vibrate) {
                    navigator.vibrate([100, 50, 100]);
                }
                
                // Efecto visual en la caja
                giftBox.style.transform = 'scale(1.05)';
                giftBox.style.boxShadow = '0 0 30px rgba(231, 76, 60, 0.8)';
                
                // Cambiar el contenido de la caja
                const boxContent = giftBox.querySelector('.box-body div');
                boxContent.innerHTML = `
                    <h3 style="margin-bottom: 10px; font-size: 1.8rem;">🎁 ¡Abierto!</h3>
                    <p style="font-size: 1.3rem;">¡Tu mensaje especial ha sido revelado!</p>
                    <div style="margin-top: 20px;">
                        <i class="fas fa-check-circle" style="font-size: 2.5rem; color: #2ecc71;"></i>
                    </div>
                `;
                
                setTimeout(() => {
                    giftBox.style.transform = 'scale(1.03)';
                    giftBox.style.boxShadow = '';
                }, 500);
            } else {
                // Ocultar el mensaje
                messageContainer.classList.remove('show');
                btnText.textContent = 'Abrir Regalo';
                openBtn.innerHTML = '<i class="fas fa-gift"></i><span>Abrir Regalo</span>';
                
                // Restaurar el contenido original de la caja
                const boxContent = giftBox.querySelector('.box-body div');
                boxContent.innerHTML = `
                    <h3 style="margin-bottom: 10px; font-size: 1.8rem;">🎁 ¡Tócame!</h3>
                    <p style="font-size: 1.3rem;">Haz clic o toca la caja para abrir tu mensaje especial</p>
                    <div style="margin-top: 20px; animation: bounce 2s infinite;">
                        <i class="fas fa-hand-point-up" style="font-size: 2.5rem;"></i>
                    </div>
                `;
                
                // Efecto visual en la caja
                giftBox.style.transform = 'scale(1)';
            }
            
            // Efecto visual en el botón
            openBtn.style.transform = 'scale(0.95)';
            setTimeout(() => {
                openBtn.style.transform = '';
            }, 200);
        }
        
        // Función para animar el año
        function animateYear() {
            let year = 2025;
            const targetYear = 2026;
            
            const interval = setInterval(() => {
                yearDisplay.textContent = year;
                
                if (year === targetYear) {
                    clearInterval(interval);
                }
                
                year++;
            }, 150);
        }
        
        // Inicializar
        document.addEventListener('DOMContentLoaded', function() {
            // Configurar eventos
            openBtn.addEventListener('click', toggleMessage);
            newMessageBtn.addEventListener('click', showRandomMessage);
            
            // Permitir abrir con la tecla Espacio
            document.addEventListener('keydown', function(e) {
                if (e.code === 'Space' || e.code === 'Enter') {
                    toggleMessage();
                    e.preventDefault();
                }
            });
            
            // Evento para abrir al tocar la caja
            giftBox.addEventListener('click', function(e) {
                // Solo abrir si el clic fue directamente en la caja y no en un elemento hijo
                if (e.target === this || e.target.closest('.box-body')) {
                    toggleMessage();
                }
            });
            
            // Efecto de brillo intermitente en la caja
            setInterval(() => {
                if (!isOpen) {
                    giftBox.style.filter = 'brightness(1.2) drop-shadow(0 0 15px rgba(255, 215, 0, 0.7))';
                    setTimeout(() => {
                        giftBox.style.filter = 'brightness(1) drop-shadow(0 0 0 rgba(255, 215, 0, 0))';
                    }, 800);
                }
            }, 5000);
            
            // Efecto intermitente en la firma del pie de página
            setInterval(() => {
                const footerSig = document.querySelector('.footer-signature');
                if (footerSig) {
                    footerSig.style.transform = 'scale(1.1)';
                    setTimeout(() => {
                        footerSig.style.transform = 'scale(1)';
                    }, 300);
                }
            }, 4000);
            
            // Iniciar animación del año
            setTimeout(animateYear, 1000);
            
            // Mostrar el primer mensaje automáticamente después de 2 segundos
            setTimeout(() => {
                if (!isOpen) {
                    toggleMessage();
                }
            }, 2000);
            
            // Agregar animación de bounce para el icono de mano
            const style = document.createElement('style');
            style.textContent = `
                @keyframes bounce {
                    0%, 100% { transform: translateY(0); }
                    50% { transform: translateY(-10px); }
                }
            `;
            document.head.appendChild(style);
        });
    </script>
</body>
</html>
