<div id="gallery-app">
  <div class="counter" id="counter">1 / 9</div>
  
  <div class="viewer">
    <img id="main-photo" src="https://i.ibb.co" />
  </div>

  <div class="controls">
    <button onclick="prevPhoto()">⬅️ Назад</button>
    <button onclick="nextPhoto()">Вперед ➡️</button>
  </div>
</div>

<script>
  const photos = [
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co",
    "https://i.ibb.co"
  ];
  
  let currentIndex = 0;
  const imgElement = document.getElementById('main-photo');
  const counterElement = document.getElementById('counter');

  function updateGallery() {
    imgElement.src = photos[currentIndex];
    counterElement.innerText = (currentIndex + 1) + " / " + photos.length;
  }

  function nextPhoto() {
    currentIndex = (currentIndex + 1) % photos.length;
    updateGallery();
  }

  function prevPhoto() {
    currentIndex = (currentIndex - 1 + photos.length) % photos.length;
    updateGallery();
  }
</script>

<style>
  body { background: #000; color: #fff; font-family: sans-serif; margin: 0; display: flex; align-items: center; justify-content: center; height: 100vh; overflow: hidden; }
  #gallery-app { text-align: center; width: 100%; }
  .viewer { height: 70vh; display: flex; align-items: center; justify-content: center; margin: 10px 0; }
  img { max-width: 100%; max-height: 100%; border-radius: 8px; transition: 0.3s; }
  .counter { font-size: 18px; margin-bottom: 10px; color: #aaa; }
  .controls { display: flex; justify-content: center; gap: 20px; }
  button { background: #333; color: white; border: none; padding: 15px 25px; border-radius: 10px; font-size: 16px; cursor: pointer; }
  button:active { background: #555; }
</style>
