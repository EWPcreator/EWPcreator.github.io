<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EWP - Earnings Wealth Power</title>
    <script src="https://unpkg.com/@tonconnect/ui@latest/dist/tonconnect-ui.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6c5ce7;
            --accent: #fdcb6e;
            --dark: #0F0F1A;
            --text: #FFFFFF;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }

        body {
            background: var(--dark);
            color: var(--text);
            line-height: 1.6;
            min-height: 100vh;
        }

        /* Шапка */
        header {
            padding: 1rem 2rem;
            background: rgba(15, 15, 26, 0.95);
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        .header-center {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo {
            width: 70px;
            height: 70px;
            transition: transform 0.3s;
        }

        .logo:hover {
            transform: rotate(-5deg) scale(1.1);
        }

        .auth-section {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .telegram-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1.5rem;
            background: #0088cc;
            color: white;
            border-radius: 25px;
            text-decoration: none;
            transition: all 0.3s;
        }

        .telegram-link:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 15px rgba(0,136,204,0.3);
        }

        .donate-btn {
            padding: 12px 24px;
            background: var(--accent);
            color: var(--dark);
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s;
            display: none;
            align-items: center;
            gap: 0.5rem;
            font-weight: 600;
        }

        .donate-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 15px rgba(253,203,110,0.3);
        }

        /* Основной контент */
        main {
            max-width: 1200px;
            margin: 100px auto 2rem;
            padding: 2rem;
        }

        /* Секция преимуществ */
        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 4rem 0;
        }

        .benefit-card {
            padding: 2rem;
            background: linear-gradient(145deg, rgba(108,92,231,0.1), rgba(255,255,255,0.05));
            border-radius: 20px;
            text-align: center;
            transition: transform 0.3s;
            backdrop-filter: blur(5px);
        }

        .benefit-card:hover {
            transform: translateY(-5px);
        }

        .benefit-icon {
            font-size: 2.5rem;
            color: var(--accent);
            margin-bottom: 1rem;
        }

        /* Дорожная карта */
        .roadmap-list {
            list-style: none;
            padding: 0;
            margin: 4rem 0;
        }

        .roadmap-item {
            padding: 2rem;
            margin: 2rem 0;
            background: linear-gradient(145deg, rgba(108,92,231,0.1), rgba(255,255,255,0.05));
            border-radius: 20px;
            border-left: 4px solid var(--primary);
            position: relative;
            transition: transform 0.3s;
            backdrop-filter: blur(5px);
            opacity: 0;
            transform: translateY(20px);
        }

        .roadmap-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .status {
            position: absolute;
            top: -15px;
            right: -15px;
            padding: 8px 20px;
            border-radius: 25px;
            font-weight: 600;
            backdrop-filter: blur(10px);
        }

        .completed .status {
            background: rgba(0,200,83,0.2);
            color: #00C853;
        }

        .progress .status {
            background: rgba(108,92,231,0.2);
            color: var(--primary);
        }

        .planned .status {
            background: rgba(255,214,0,0.2);
            color: #FFD600;
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            header {
                padding: 1rem;
                flex-direction: column;
                gap: 1rem;
                position: static;
            }

            main {
                margin-top: 20px;
                padding: 1rem;
            }

            .roadmap-item {
                padding: 1.5rem;
                margin: 1.5rem 0;
            }

            .benefits-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-center">
            <img src="https://ewpcreator.github.io/Logo.png" alt="EWP" class="logo">
            <h1>Earnings Wealth Power</h1>
        </div>
        
        <div class="auth-section">
            <div id="connect-button"></div>
            <button class="donate-btn" id="donateButton">
                <i class="fas fa-donate"></i> Поддержать
            </button>
            <a href="https://t.me/EWP_official_chanel" class="telegram-link" target="_blank">
                <i class="fab fa-telegram"></i>
                Наш Telegram
            </a>
        </div>
    </header>

    <main>
        <section class="benefits">
            <h2>Преимущества EWP</h2>
            <div class="benefits-grid">
                <div class="benefit-card">
                    <i class="fas fa-bolt benefit-icon"></i>
                    <h3>Скорость</h3>
                    <p>Транзакции за 2-3 секунды через сеть TON</p>
                </div>
                
                <div class="benefit-card">
                    <i class="fas fa-lock benefit-icon"></i>
                    <h3>Безопасность</h3>
                    <p>Аудированные контракты и децентрализация</p>
                </div>

                <div class="benefit-card">
                    <i class="fas fa-gamepad benefit-icon"></i>
                    <h3>Геймификация</h3>
                    <p>Зарабатывайте токены через игры в Telegram</p>
                </div>
            </div>
        </section>

        <section class="roadmap">
            <h2>Дорожная карта</h2>
            <ul class="roadmap-list">
                <li class="roadmap-item completed visible">
                    <div class="status">✅ Завершено</div>
                    <h3>Q1 2025: Старт проекта</h3>
                    <ul>
                        <li>Запуск токена EWP</li>
                       
                    </ul>
                </li>

                <li class="roadmap-item progress">
                    <div class="status">🚀 В процессе</div>
                    <h3>2025: Развитие</h3>
                    <ul>
                         <li>Аудит контракта</li>
                        <li>Первые 10,000 держателей</li>
                        <li>Запуск игры-кликера</li>
                        <li>Airdrop</li>
                    </ul>
                </li>

                <li class="roadmap-item planned">
                    <div class="status">🔮 2025</div>
                    <h3>Глобальная экспансия</h3>
                    <ul>
                        <li>Листинг на DEX- CEX-биржах</li>
                        <li>NFT коллекция</li>
                        <li>Криптообменник </li>
                        <li>Криптоматы EWP</li>
                    </ul>
                </li>
            </ul>
        </section>
    </main>

    <script>
        // Инициализация TON Connect
        const tonConnectUI = new TON_CONNECT_UI.TonConnectUI({
            manifestUrl: 'https://ewp-project.com/tonconnect-manifest.json',
            buttonRootId: 'connect-button',
            uiPreferences: {
                theme: 'DARK',
                borderRadius: 'LARGE'
            }
        });

        // Обработчик подключения кошелька
        tonConnectUI.onStatusChange(wallet => {
            const donateBtn = document.getElementById('donateButton');
            donateBtn.style.display = wallet ? 'flex' : 'none';
        });

        // Обработчик доната
        document.getElementById('donateButton').addEventListener('click', async () => {
            const transaction = {
                messages: [{
                    address: 'UQBhuXd2u0-Sxd01Lwo1cc5q3lTy_c25CDu2MTP-Gq71wyPq',
                    amount: '1000000000' // 1 TON
                }],
                validUntil: Date.now() + 300000
            };

            try {
                await tonConnectUI.sendTransaction(transaction);
                alert('Спасибо за поддержку! Ваш вклад помогает развитию проекта 🚀');
            } catch (error) {
                console.error('Ошибка:', error);
                alert('Ошибка транзакции. Пожалуйста, попробуйте снова.');
            }
        });

        // Анимация дорожной карты
        const observer = new IntersectionObserver(entries => {
            entries.forEach(entry => {
                if(entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.roadmap-item').forEach(item => {
            observer.observe(item);
        });
    </script>
</body>
</html>
