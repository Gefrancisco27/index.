<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

       
         <link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
        <script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>

    <style>
      body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            background-color: #f4f4f4;
        }
        .container {
            padding: 20px;
            max-width: 800px;
            margin: auto;
            background-color: #fff;
            border-radius: 12px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .header {
            position: relative;
            color: white;
        }
        .header img {
            width: 100%;
            height: 350px;
            object-fit: cover;
            border-radius: 12px;
        }
        .header .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            border-radius: 12px;
        }
        .header .text-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            width: 80%;
        }
        .header .text-container h1 {
            font-size: 24px;
            margin-bottom: 10px;
            color: white;
        }
        .header .text-container p {
            font-size: 16px;
            margin-bottom: 5px;
            color: white;
        }
        .logo-menu {
            position: absolute;
            top: 20px;
            left: 20px;
            display: flex;
            align-items: center;
        }
        .logo-menu img {
            width: 100px;
            height: auto;
            margin-right: 350px;
        }
        .logo-menu nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            display: flex;
        }
        .logo-menu nav ul li {
            display: inline;
            margin-right: 20px;
        }
        .logo-menu nav ul li a {
            color: white;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
        }
        .logo-menu nav ul li a:hover {
            text-decoration: underline;
        }
        #map {
        width: 600px;
        height: 400px;
        padding: 0%;
        margin: auto;
        margin-top: 20px;
        margin-bottom: auto;
        }
    </style>
</head>
<body>
  <div class="container">
    <div class="header">
        <img src="persebaran 1.jpg" alt="Background">
        <div class="overlay"></div>
        <div class="text-container">
            <h1>"Jelajahi Surga Pesisir Gorontalo"</h1>
            <p>"Jelajahi keajaiban alam yang memikat di tepian pantai Gorontalo</p>
            <p>Temukan Keajaiban Laut Gorontalo Destinasi Perjalananmu Menuju Ketenangan dan Kebahagiaan."</p>
        </div>
        <!-- Tambahkan bagian berikut untuk logo dan menu -->
        <div class="logo-menu">
            <img src="persebaran_logo.png" alt="Logo">
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Data Tempat Wisata</a></li>
                    <li><a href="#">About Us</a></li>
                </ul>
            </nav>
        </div>
    </div>
    <div>
        <div id='map'></div>
    </div>
    <script>
        var locations = [
            ["Pantai Botubarani", 0.482392,123.086187],
            ["Dulanga Beach", 0.495204,123.029069],
            ["Kurenai Beach Resort", 0.478513,123.089957],
            ["Pantai Biluhu Timur", 0.494818,122.975445],
            ["Pantai Kaisomaru", 0.487026,123.083305 ],
            ["Taman Wisata Tangga 2000", 0.506978,123.057687],
            ["Pantai Tanjung Kramat", 0.495676,123.044350],
            ["Pantai Botutonuo", 0.447024,123.125889],
            ["Wisata Tamendao Beach",0.447116391894112, 123.12593647116424],
            ["Pantai Boalemo Indah Gorontalo", 0.4761501241665532, 122.20095781674819],
            ["Pantai Leato Selatan", 0.49183834588612113, 123.07838614232848],
            ["Tilalohe Beach Resort", 0.48879108914795616, 122.9421400846569],
            ["Wisata Pantai Tanjung Biluhu", 0.4914883633825588, 122.95645484602916],
            ["Pantai Lopo",0.4966607907099961, 123.01807275767152],
            ["Taman Laut Olele", 0.41177320689895003, 123.15273848650729],
            ["Pantai Ratu", 0.5055784620652486, 122.41262712883578],
            ["Pantai Pasir Putih", 0.48862514639401444, 123.08232241534307],
            ["Pantai Oluhuta",0.4191507705644298, 123.1451728820355],
            ["Pantai Tanjung Tihu", 0.36796674331754986, 123.21664008203555],
            ["Exotic Beach", 0.46750641527513426, 123.10718379062824],
            ["Pantai Germanium Bulawa",0.33835370183826236, 123.25101821087152],
];

var map = L.map('map').setView([0.5427653579481185, 123.05466008541104], 8);
mapLink =
  '<a href="http://openstreetmap.org">OpenStreetMap</a>';
L.tileLayer(
  'http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; ' + mapLink + ' Contributors',
    maxZoom: 18,
  }).addTo(map);

for (var i = 0; i < locations.length; i++) {
  marker = new L.marker([locations[i][1], locations[i][2]])
    .bindPopup(locations[i][0])
    .addTo(map);
}
    </script>
</body>
</html>
