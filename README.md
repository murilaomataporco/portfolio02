<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfólio de Fotos</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f6f6f6;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 900px;
            margin: 40px auto;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 24px rgba(0,0,0,0.09);
            padding: 32px;
        }
        h1 {
            margin-bottom: 16px;
            color: #333;
        }
        form {
            margin-bottom: 24px;
            display: flex;
            gap: 12px;
        }
        input[type="file"] {
            flex: 1;
        }
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 18px;
        }
        .photo-card {
            background: #f5f5f5;
            border-radius: 8px;
            overflow: hidden;
            position: relative;
        }
        .photo-card img {
            width: 100%;
            display: block;
            object-fit: cover;
            height: 180px;
        }
        .remove-btn {
            position: absolute;
            top: 8px;
            right: 8px;
            background: #e74c3c;
            color: #fff;
            border: none;
            border-radius: 50%;
            width: 28px;
            height: 28px;
            cursor: pointer;
            font-size: 16px;
        }
        @media (max-width: 500px) {
            .container {
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Meu Portfólio de Fotos</h1>
        <form id="uploadForm">
            <input type="file" id="photoInput" accept="image/*" multiple>
            <button type="submit">Adicionar Fotos</button>
        </form>
        <div class="gallery" id="gallery"></div>
    </div>

    <script>
        // Carregar fotos do localStorage ao iniciar
        function loadPhotos() {
            const saved = localStorage.getItem('portfolio_photos');
            return saved ? JSON.parse(saved) : [];
        }

        // Salvar fotos no localStorage
        function savePhotos(photos) {
            localStorage.setItem('portfolio_photos', JSON.stringify(photos));
        }

        // Renderizar galeria de fotos
        function renderGallery() {
            const gallery = document.getElementById('gallery');
            gallery.innerHTML = '';
            const photos = loadPhotos();
            photos.forEach((photo, idx) => {
                const card = document.createElement('div');
                card.className = 'photo-card';

                const img = document.createElement('img');
                img.src = photo;
                img.alt = `Foto ${idx+1}`;

                const removeBtn = document.createElement('button');
                removeBtn.textContent = '×';
                removeBtn.className = 'remove-btn';
                removeBtn.onclick = () => removePhoto(idx);

                card.appendChild(img);
                card.appendChild(removeBtn);
                gallery.appendChild(card);
            });
        }

        // Remover foto
        function removePhoto(index) {
            let photos = loadPhotos();
            photos.splice(index, 1);
            savePhotos(photos);
            renderGallery();
        }

        // Adicionar fotos
        document.getElementById('uploadForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const input = document.getElementById('photoInput');
            const files = Array.from(input.files);
            if (files.length === 0) return;

            let photos = loadPhotos();
            let pending = files.length;

            files.forEach(file => {
                const reader = new FileReader();
                reader.onload = function(ev) {
                    photos.push(ev.target.result);
                    pending--;
                    if (pending === 0) {
                        savePhotos(photos);
                        renderGallery();
                        input.value = "";
                    }
                };
                reader.readAsDataURL(file);
            });
        });

        // Inicializar
        renderGallery();
    </script>
</body>
</html>
