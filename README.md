<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Portfólio de Fotos</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Meu Portfólio de Fotos</h1>
        <nav>
            <ul>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#galeria">Galeria</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>
    <section id="sobre">
        <h2>Sobre Mim</h2>
        <p>Olá! Eu sou um fotógrafo apaixonado por capturar momentos únicos. Confira minha galeria abaixo.</p>
    </section>
    <section id="galeria">
        <h2>Galeria de Fotos</h2>
        <div class="gallery">
            <div class="photo">
                <img src="https://source.unsplash.com/400x300/?nature" alt="Natureza">
                <p>Natureza</p>
            </div>
            <div class="photo">
                <img src="https://source.unsplash.com/400x300/?city" alt="Cidade">
                <p>Cidade</p>
            </div>
            <div class="photo">
                <img src="https://source.unsplash.com/400x300/?portrait" alt="Retrato">
                <p>Retrato</p>
            </div>
            <div class="photo">
                <img src="https://source.unsplash.com/400x300/?animals" alt="Animais">
                <p>Animais</p>
            </div>
            <div class="photo">
                <img src="https://source.unsplash.com/400x300/?travel" alt="Viagem">
                <p>Viagem</p>
            </div>
            <div class="photo">
                <img src="https://source.unsplash.com/400x300/?beach" alt="Praia">
                <p>Praia</p>
            </div>
        </div>
    </section>
    <section id="contato">
        <h2>Contato</h2>
        <form id="formContato">
            <input type="text" name="nome" placeholder="Seu nome" required>
            <input type="email" name="email" placeholder="Seu email" required>
            <textarea name="mensagem" placeholder="Sua mensagem" required></textarea>
            <button type="submit">Enviar</button>
        </form>
        <div id="msgEnviada" style="display:none;">Mensagem enviada! Obrigado pelo contato.</div>
    </section>
    <footer>
        <p>&copy; 2025 Meu Portfólio de Fotos</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
