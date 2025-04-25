<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Treasure Digging Simulator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        #treasureIsland {
            background-image: url('https://www.istockphoto.com/vi/anh/c%E1%BA%ADn-c%E1%BA%A3nh-m%C3%B4-h%C3%ACnh-c%C3%A1t-c%E1%BB%A7a-m%C3%B9a-h%C3%A8-gm678719470-125832651');
            background-size: cover;
            height: 400px;
            width: 100%;
            text-align: center;
            color: white;
            padding-top: 50px;
        }
        #shop {
            padding: 20px;
            background-color: #f4f4f4;
            margin-top: 20px;
        }
        .item {
            display: inline-block;
            width: 150px;
            text-align: center;
            margin: 10px;
        }
        .item img {
            width: 100px;
            height: 100px;
        }
    </style>
</head>
<body>

    <div id="treasureIsland">
        <h1>Treasure Island</h1>
        <p>Click to start digging for treasure!</p>
    </div>

    <div id="shop">
        <h2>Item Shop</h2>
        <div class="item">
            <img src="https://www.istockphoto.com/vi/anh/c%E1%BA%ADn-c%E1%BA%A3nh-m%C3%B4-h%C3%ACnh-c%C3%A1t-c%E1%BB%A7a-m%C3%B9a-h%C3%A8-gm678719470-125832651" alt="Golden Shovel">
            <p>Golden Shovel (20 💎)</p>
            <button onclick="buyItem('goldenShovel')">Buy</button>
        </div>
        <div class="item">
            <img src="https://bizweb.dktcdn.net/100/119/315/products/pixelcut-export-58-cc24b29a-58a0-4aa1-b484-4551e3c48afb.jpg?v=1736392501217" alt="Drill">
            <p>Drill (50 💎)</p>
            <button onclick="buyItem('drill')">Buy</button>
        </div>
    </div>

    <script>
        let diamonds = 0;
        let currentItem = "Wooden Shovel";
        let digs = 15;

        function buyItem(item) {
            if (item === 'goldenShovel' && diamonds >= 20) {
                diamonds -= 20;
                currentItem = "Golden Shovel";
                digs = 10;
                alert("You bought a Golden Shovel!");
            } else if (item === 'drill' && diamonds >= 50) {
                diamonds -= 50;
                currentItem = "Drill";
                digs = 5;
                alert("You bought a Drill!");
            } else {
                alert("You don't have enough diamonds!");
            }
            updateUI();
        }

        function updateUI() {
            document.getElementById('diamondCount').innerText = `Diamonds: ${diamonds}`;
            document.getElementById('currentItem').innerText = `Current Item: ${currentItem}`;
        }

        function digTreasure() {
            if (digs > 0) {
                digs--;
                const earnedDiamonds = Math.floor(Math.random() * 10) + 1;
                diamonds += earnedDiamonds;
                alert(`You earned ${earnedDiamonds} diamonds!`);
                updateUI();
            } else {
                alert("You need to buy a better tool to dig!");
            }
        }
    </script>

    <div>
        <p id="diamondCount">Diamonds: 0</p>
        <p id="currentItem">Current Item: Wooden Shovel</p>
        <button onclick="digTreasure()">Dig</button>
    </div>

</body>
</html>
