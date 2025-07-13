carplay_dashboard.html
<!DOCTYPE html>
<html>
<head>
  <title>Token-Free Dashboard</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    body, html { margin: 0; padding: 0; height: 100%; font-family: monospace; background: #000; color: #0f0; }
    #map { position: absolute; top: 0; left: 0; right: 0; bottom: 120px; }
    #music-controls { position: absolute; bottom: 0; left: 0; right: 0; height: 120px; background: #111; display: flex; align-items: center; justify-content: center; gap: 15px; }
    button { padding: 15px 25px; font-size: 20px; background: #222; border: none; color: #0f0; border-radius: 10px; cursor: pointer; }
    #track-info { font-size: 18px; flex-grow: 1; padding-left: 20px; }
  </style>
</head>
<body>
