<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Earnings Wealth Power (EWP)</title>
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
            font-family: 'Arial', sans-serif;
        }

        body {
            background: var(--dark);
            color: var(--text);
            line-height: 1.6;
        }

        /* Шапка */
        header {
            padding: 1rem 2rem;
            background: rgba(15, 15, 26, 0.95);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            position: relative;
        }

        .header-center {
            display: flex;
            align-items: center;
            gap: 1rem;
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
        }

        .logo {
            width: 60px;
            height: 60px;
            transition: transform 0.3s;
        }

        .logo:hover {
            transform: rotate(-5deg);
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
            transition: transform 0.3s;
        }

        .telegram-link:hover {
            transform: scale(1.05);
        }

        /* Основной контент */
        main {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Секция преимуществ */
        .benefits {
            margin: 4rem 0;
            padding: 2rem 0;
        }

        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .benefit-card {
            padding: 2rem;
            background: rgba(255,255,255,0.05);
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s;
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
            margin: 2rem 0;
        }

        .roadmap-item {
            padding: 1.5rem;
            margin: 1.5rem 0;
            background: rgba(255,255,255,0.05);
            border-radius: 15px;
            border-left: 4px solid var(--primary);
            position: relative;
            transition: transform 0.3s;
        }

        .roadmap-item:hover {
            transform: translateX(10px);
        }

        .status {
            position: absolute;
            top: -10px;
            right: -10px;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        .completed .status {
            background: #00C853;
        }

        .progress .status {
            background: var(--primary);
        }

        .planned .status {
            background: #FFD600;
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            header {
                justify-content: center;
                gap: 1rem;
                padding: 1rem;
            }
            
            .header-center {
                position: static;
                transform: none;
                order: 1;
                width: 100%;
                justify-content: center;
            }
            
            .telegram-link {
                order: 2;
            }

            .roadmap-item {
                padding: 1rem;
                margin: 1rem 0;
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
            <img src="logo.png" alt="EWP Logo" class="logo">
            <h1>Earnings Wealth Power</h1>
        </div>
        
        <a href="https://t.me/EWP_official_chanel" class="telegram-link" target="_blank">
            <i class="fab fa-telegram"></i>
            Наш Telegram
        </a>
    </header>

    <main>
        <section class="benefits">
            <h2>Преимущества токена EWP</h2>
            <div class="benefits-grid">
                <div class="benefit-card">
                    <i class="fas fa-rocket benefit-icon"></i>
                    <h3>Высокая скорость</h3>
                    <p>Транзакции в сети TON обрабатываются за секунды</p>
                </div>
                
                <div class="benefit-card">
                    <i class="fas fa-coins benefit-icon"></i>
                    <h3>Низкие комиссии</h3>
                    <p>Минимальные сборы за переводы и операции</p>
                </div>

                <div class="benefit-card">
                    <i class="fas fa-shield-alt benefit-icon"></i>
                    <h3>Безопасность</h3>
                    <p>Аудированный контракт и децентрализация</p>
                </div>

                <div class="benefit-card">
                    <i class="fas fa-gamepad benefit-icon"></i>
                    <h3>Геймификация</h3>
                    <p>Зарабатывайте токены через игровые механики</p>
                </div>
            </div>
        </section>

        <section class="roadmap">
            <h2>Дорожная карта проекта</h2>
            
            <ul class="roadmap-list">
                <li class="roadmap-item completed">
                    <div class="status">✅ Завершено</div>
                    <h3>Q3 2024: Запуск токена</h3>
                    <ul>
                        <li>Создание токена EWP в сети TON</li>
                        <li>Проведение аудита контракта</li>
                        <li>Формирование первоначального сообщества</li>
                    </ul>
                </li>

                <li class="roadmap-item progress">
                    <div class="status">🚀 В процессе</div>
                    <h3>Q4 2024: Развитие экосистемы</h3>
                    <ul>
                        <li>Запуск игрового модуля</li>
                        <li>Интеграция с DEX-платформами</li>
                        <li>Разработка мобильного приложения</li>
                    </ul>
                </li>

                <li class="roadmap-item planned">
                    <div class="status">🔮 Планируется</div>
                    <h3>2025: Глобальное расширение</h3>
                    <ul>
                        <li>Листинг на топовых CEX-биржах</li>
                        <li>Запуск NFT-маркетплейса</li>
                        <li>Внедрение физических криптоматов</li>
                    </ul>
                </li>
            </ul>
        </section>
    </main>
</body>
</html>
