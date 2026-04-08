<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pizzaria Bella Italia</title>
    <style>
        :root {
            --primary: #e74c3c;
            --dark: #1a1a1a;
            --light: #f4f4f4;
            --gold: #f1c40f;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--dark);
            color: var(--light);
            margin: 0;
            padding: 0;
        }

        header {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://unsplash.com');
            background-size: cover;
            background-position: center;
            text-align: center;
            padding: 60px 20px;
            border-bottom: 4px solid var(--primary);
        }

        h1 { margin: 0; font-size: 3rem; color: var(--primary); text-transform: uppercase; }
        p.subtitle { font-style: italic; color: var(--gold); }

        .container {
            max-width: 900px;
            margin: 20px auto;
            padding: 20px;
        }

        .section-title {
            border-bottom: 2px solid var(--primary);
            padding-bottom: 10px;
            margin-top: 40px;
            color: var(--primary);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .pizza-item {
            background: #262626;
            padding: 15px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: transform 0.3s;
        }

        .pizza-item:hover {
            transform: scale(1.02);
            background: #333;
        }

        .pizza-info h3 { margin: 0 0 5px 0; color: var(--light); }
        .pizza-info p { margin: 0; font-size: 0.9rem; color: #aaa; }

        .price {
            font-weight: bold;
            color: var(--gold);
            font-size: 1.2rem;
            white-space: nowrap;
            margin-left: 15px;
        }

        footer {
            text-align: center;
            padding: 40px;
            font-size: 0.8rem;
            color: #666;
        }

        .badge {
            background: var(--primary);
            color: white;
            font-size: 0.7rem;
            padding: 2px 6px;
            border-radius: 4px;
            margin-left: 5px;
            vertical-align: middle;
        }
    </style>
</head>
<body>

    <header>
        <h1>Bella Itália</h1>
        <p class="subtitle">A verdadeira pizza artesanal no forno a lenha</p>
    </header>

    <div class="container">
        <!-- Pizzas Tradicionais -->
        <h2 class="section-title">Pizzas Tradicionais</h2>
        <div class="menu-grid">
            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Marguerita <span class="badge">Venda +</span></h3>
                    <p>Molho de tomate, muçarela, manjericão fresco e azeite.</p>
                </div>
                <div class="price">R$ 45,90</div>
            </div>

            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Calabresa</h3>
                    <p>Molho de tomate, muçarela, calabresa fatiada e cebola.</p>
                </div>
                <div class="price">R$ 42,90</div>
            </div>

            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Portuguesa</h3>
                    <p>Presunto, ovos, cebola, ervilha e cobertura de muçarela.</p>
                </div>
                <div class="price">R$ 48,90</div>
            </div>
        </div>

        <!-- Pizzas Especiais -->
        <h2 class="section-title">Pizzas Especiais</h2>
        <div class="menu-grid">
            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Quatro Queijos</h3>
                    <p>Muçarela, provolone, parmesão e gorgonzola cremoso.</p>
                </div>
                <div class="price">R$ 52,90</div>
            </div>

            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Trufas Negras</h3>
                    <p>Mix de cogumelos, muçarela de búfala e óleo de trufa.</p>
                </div>
                <div class="price">R$ 65,00</div>
            </div>
        </div>

        <!-- Bebidas -->
        <h2 class="section-title">Bebidas</h2>
        <div class="menu-grid">
            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Refrigerante Lata</h3>
                    <p>350ml (Coca-Cola, Guaraná, Soda)</p>
                </div>
                <div class="price">R$ 6,00</div>
            </div>

            <div class="pizza-item">
                <div class="pizza-info">
                    <h3>Cerveja Artesanal</h3>
                    <p>IPA ou Lager local (500ml)</p>
                </div>
                <div class="price">R$ 18,00</div>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2023 Pizzaria Bella Itália - Aberto de Terça a Domingo, das 18h às 23h</p>
        <p>Rua das Pizzas, 123 - Centro</p>
    </footer>

</body>
</html>
