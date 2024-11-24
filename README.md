# IM-FLOWERS
buques de flor
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IM Flouwers</title>
    <link rel="stylesheet" href="style.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #fdf5f5; /* Bege claro */
            color: #5a2a2a; /* Tom de rosa escuro para contraste */
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #f7e6e6; /* Rosa claro */
            padding: 20px;
            text-align: center;
            border-bottom: 2px solid #d8bebe;
        }

        header h1 {
            color: #5a2a2a;
        }

        main {
            padding: 20px;
        }

        section {
            margin-bottom: 30px;
            padding: 20px;
            background-color: #fffafa;
            border: 1px solid #f3dcdc;
            border-radius: 8px;
            box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
        }

        section h2 {
            color: #8b3a3a;
        }

        section h3 {
            color: #b35c5c;
        }

        .bouquet {
            margin-left: 20px;
        }

        form {
            display: flex;
            flex-direction: column;
        }

        form label, form input, form select, form button {
            margin-bottom: 15px;
            font-size: 1em;
        }

        form button {
            background-color: #e8b4b8;
            border: none;
            padding: 10px;
            border-radius: 5px;
            color: white;
            cursor: pointer;
        }

        form button:hover {
            background-color: #d79aa1;
        }

        .chocolate-img {
            max-width: 100%;
            height: auto;
            display: block;
            margin: 10px auto;
        }

        footer {
            text-align: center;
            padding: 10px;
            background-color: #f7e6e6;
            border-top: 2px solid #d8bebe;
        }

        footer p {
            margin: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>IM Flouwers</h1>
        <p>Crie, escolha e encomende o buquê perfeito para qualquer ocasião!</p>
    </header>

    <main>
        <!-- Catálogo de Produtos -->
        <section id="catalog">
            <h2>Nosso Catálogo</h2>

            <!-- Buquês de Rosas de Cetim -->
            <h3>Buquês de Rosas de Cetim</h3>
            <div class="bouquet">
                <p><strong>Tamanho P:</strong> 20 rosas - R$ 85,00</p>
                <p><strong>Tamanho M:</strong> 30 rosas - R$ 120,00</p>
                <p><strong>Tamanho G:</strong> 50 rosas - R$ 150,00</p>
            </div>

            <!-- Buquês de Borboletas -->
            <h3>Buquês de Borboletas</h3>
            <div class="bouquet">
                <p><strong>Tamanho P:</strong> 20 borboletas - R$ 80,00</p>
                <p><strong>Tamanho M:</strong> 30 borboletas - R$ 100,00</p>
                <p><strong>Tamanho G:</strong> 50 borboletas - R$ 120,00</p>
            </div>

            <!-- Rosas Unitárias -->
            <h3>Rosas Unitárias</h3>
            <div class="bouquet">
                <p>Preço por unidade: R$ 5,60</p>
            </div>

            <!-- Buquês Personalizados -->
            <h3>Buquês Personalizados</h3>
            <div class="bouquet">
                <p>Crie um buquê único para você ou para quem você ama!</p>
                <p>Adicione chocolates por apenas R$ 22,00.</p>
                <img src="https://via.placeholder.com/150" alt="Chocolates" class="chocolate-img">
            </div>
        </section>

        <!-- Formulário de Encomenda -->
        <section id="order">
            <h2>Faça sua Encomenda</h2>
            <form id="orderForm">
                <label for="bouquetType">Tipo de Buquê:</label>
                <select id="bouquetType" name="bouquetType">
                    <option value="cetim">Buquê de Rosas de Cetim</option>
                    <option value="borboletas">Buquê de Borboletas</option>
                    <option value="unitario">Rosas Unitárias</option>
                    <option value="personalizado">Buquê Personalizado</option>
                </select>

                <label for="size">Tamanho:</label>
                <select id="size" name="size">
                    <option value="p">P - 20 unidades</option>
                    <option value="m">M - 30 unidades</option>
                    <option value="g">G - 50 unidades</option>
                </select>

                <label for="addChocolate">Adicionar Chocolates:</label>
                <input type="checkbox" id="addChocolate" name="addChocolate" value="22">

                <label for="quantity">Quantidade:</label>
                <input type="number" id="quantity" name="quantity" min="1" value="1">

                <p id="totalPrice">Total: R$ 0,00</p>

                <button type="button" onclick="calculateAndSendOrder()">Enviar Pedido</button>
            </form>
            <div id="deliveryInfo">
                <p><strong>Informações de Entrega:</strong></p>
                <p>Se a opção for entrega, haverá uma taxa de envio.</p>
                <p>Entre em contato pelo Instagram <a href="https://www.instagram.com/rosas_da_isa" target="_blank">@rosas_da_isa</a> para detalhes.</p>
                <p>Ou retire no local: SJC, Rua Olinda 1035, Parque Industrial.</p>
                <p><strong>Pagamento:</strong></p>
                <p>Chave PIX: <strong>(12) 98707-8810</strong></p>
                <p>Qualquer dúvida, entre em contato pelo Instagram <a href="https://www.instagram.com/rosas_da_isa" target="_blank">@rosas_da_isa</a> ou WhatsApp: <a href="https://wa.me/5512987078810" target="_blank">(12) 98707-8810</a>.</p>
            </div>
        </section>
    </main>

    <footer>
        <p>© 2024 - IM Flouwers. Todos os direitos reservados.</p>
    </footer>

    <script>
        const prices = {
            cetim: { p: 85, m: 120, g: 150 },
            borboletas: { p: 80, m: 100, g: 120 },
            unitario: { unit: 5.6 },
            chocolate: 22
        };

        function calculateTotal() {
            const bouquetType = document.getElementById('bouquetType').value;
            const size = document.getElementById('size').value;
            const quantity = parseInt(document.getElementById('quantity').value, 10);
            const addChocolate = document.getElementById('addChocolate').checked;

            let basePrice = 0;

            if (bouquetType === 'unitario') {
                basePrice = prices.unitario.unit;
            } else {
                basePrice = prices[bouquetType][size];
            }

            let total = basePrice * quantity;

            if (addChocolate) {
                total += prices.chocolate * quantity;
            }
            document.getElementById('totalPrice').textContent = `Total: R$ ${total.toFixed(2)}`;
        }

        function calculateAndSendOrder() {
            calculateTotal();

            // Aqui você pode adicionar a lógica para enviar o pedido, por exemplo, usando uma API ou apenas mostrando um alerta.
            alert('Pedido enviado com sucesso! Aguardando confirmação.');
            
        }
    </script>
</body>
</html>
