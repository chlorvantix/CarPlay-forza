<!DOCTYPE html>
<html>
<head>
  <title>Token-Free Dashboard</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      font-family: monospace;
      background: #000;
      color: #0f0;
    }
    #map {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 120px;
    }
    #music-controls {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      height: 120px;
      background: #111;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 15px;
      padding: 0 20px;
    }
    button {
      padding: 15px 25px;
      font-size: 20px;
      background: #222;
      border: none;
      color: #0f0;
      border-radius: 10px;
      cursor: pointer;
    }
    #track-info {
      font-size: 18px;
      flex-grow: 1;
      padding-left: 20px;
    }
  </style>
</head>
<body>
  <div id="map"></div>
  <div id="music-controls">
    <button id="play">▶️ Play</button>
    <button id="pause">⏸ Pause</button>
    <div id="track-info">No track playing</div>
  </div>

  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
  <script>
    const map = L.map('map').fitWorld();

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    map.locate({setView: true, maxZoom: 16, watch: true});

    // music controls
    const playBtn = document.getElementById('play');
    const pauseBtn = document.getElementById('pause');
    const trackInfo = document.getElementById('track-info');

    playBtn.onclick = () => {
      trackInfo.textContent = 'Playing: Your Favorite Track';
    };

    pauseBtn.onclick = () => {
      trackInfo.textContent = 'Paused';
    };
  </script>
</body>
</html>
