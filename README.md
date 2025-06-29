<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Meu Portfólio de Fotos</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background-color: #f5f5f5;
      color: #333;
    }

    header {
      background-color: #222;
      color: white;
      text-align: center;
      padding: 2rem 1rem;
    }

    header h1 {
      font-size: 2.5rem;
    }

    header p {
      font-size: 1.2rem;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1rem;
      padding: 2rem;
    }

    .photo img {
      width: 100%;
      height: auto;
      border-radius: 8px;
      transition: transform 0.3s ease;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      opacity: 0;
    }

    .photo img:hover {
      transform: scale(1.05);
    }

    footer {
      background-color: #222;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Meu Portfólio</h1>
    <p>Fotos capturadas por mim</p>
  </header>

  <main class="gallery">
    <div class="photo"><img src="https://source.unsplash.com/random/300x200?sig=1" alt="Foto 1"></div>
    <div class="photo"><img src="https://source.unsplash.com/random/300x200?sig=2" alt="Foto 2"></div>
    <div class="photo"><img src="https://source.unsplash.com/random/300x200?sig=3" alt="Foto 3"></div>
    <div class="photo"><img src="https://source.unsplash.com/random/300x200?sig=4" alt="Foto 4"></div>
    <div class="photo"><img src="https://source.unsplash.com/random/300x200?sig=5" alt="Foto 5"></div>
    <div class="photo"><img src="https://source.unsplash.com/random/300x200?sig=6" alt="Foto 6"></div>
  </main>

  <footer>
    <p>&copy; 2025 - Seu Nome</p>
  </footer>

  <script>
    document.addEventListener("DOMContentLoaded", () => {
      const images = document.querySelectorAll(".photo img");
      images.forEach((img, index) => {
        setTimeout(() => {
          img.style.transition = "opacity 1s ease";
          img.style.opacity = 1;
        }, 200 * index);
      });
    });
  </script>
</body>
</html>
