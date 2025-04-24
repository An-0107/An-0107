<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Vio Shop - Robux Uy Tín</title>
  <style>
    body {
      background: #111;
      color: white;
      font-family: Arial;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #f39c12;
    }
    .menu {
      margin: 20px 0;
    }
    .menu button {
      background: red;
      color: white;
      padding: 10px 20px;
      border: none;
      margin: 10px;
      font-size: 18px;
      cursor: pointer;
    }
    .section {
      display: none;
      margin-top: 30px;
    }
    input[type="text"], input[type="number"] {
      padding: 10px;
      width: 80%;
      margin: 10px 0;
    }
    .result {
      margin-top: 20px;
      font-size: 18px;
      color: #0f0;
    }
  </style>
</head>
<body>

  <h1>Shop Robux Uy Tín 120h</h1>

  <div class="menu">
    <button onclick="showSection('robux')">Robux</button>
    <button onclick="showSection('napthe')">Nạp Thẻ</button>
    <button onclick="showSection('caythue')">Cày Thuê</button>
  </div>

  <!-- Nạp thẻ -->
  <div id="napthe" class="section">
    <h2>Nạp Thẻ</h2>
    <input type="number" id="giatri" placeholder="Giá trị thẻ (VD: 10000)">
    <input type="text" id="mathe" placeholder="Mã số thẻ">
    <input type="text" id="seri" placeholder="Số Seri">
    <br>
    <button onclick="hoanTatNapThe()">Hoàn Tất</button>
    <div id="kqnap" class="result"></div>
  </div>

  <!-- Robux -->
  <div id="robux" class="section">
    <h2>Mua Robux</h2>
    <div id="tien" style="margin-bottom: 10px;">Số tiền: 0đ</div>
    <div id="robuxnhan">Số Robux: 0</div>
    <br>
    <input type="text" id="taikhoanrb" placeholder="Nhập tài khoản Roblox">
    <br>
    <button onclick="muaRobux()">Avatar</button>
    <div id="kqrobux" class="result"></div>
  </div>

  <!-- Cày thuê -->
  <div id="caythue" class="section">
    <h2>Cày Thuê</h2>
    <input type="text" placeholder="Nhập yêu cầu cần cày thuê">
    <input type="text" placeholder="Tài khoản Roblox">
    <input type="text" placeholder="Mật khẩu Roblox">
    <br>
    <div class="result">Yêu cầu của bạn đã được ghi nhận!</div>
  </div>

  <script>
    let soTienNap = 0;

    function showSection(id) {
      document.querySelectorAll('.section').forEach(el => el.style.display = 'none');
      document.getElementById(id).style.display = 'block';
    }

    function hoanTatNapThe() {
      const giatri = parseInt(document.getElementById("giatri").value);
      const mathe = document.getElementById("mathe").value;
      const seri = document.getElementById("seri").value;

      if (giatri > 0 && mathe && seri) {
        soTienNap = giatri;
        document.getElementById("kqnap").innerText = "Nạp thẻ thành công!";
        document.getElementById("tien").innerText = "Số tiền: " + soTienNap + "đ";
        document.getElementById("robuxnhan").innerText = "Số Robux: " + Math.floor(soTienNap / 10000 * 80);
      } else {
        document.getElementById("kqnap").innerText = "Vui lòng nhập đầy đủ!";
      }
    }

    function muaRobux() {
      const tk = document.getElementById("taikhoanrb").value;
      if (tk) {
        if (soTienNap >= 10000) {
          document.getElementById("kqrobux").innerText = "Tài khoản " + tk + " đã mua thành công!";
        } else {
          document.getElementById("kqrobux").innerText = "Tài khoản chưa có tiền!";
        }
      } else {
        document.getElementById("kqrobux").innerText = "Vui lòng nhập tài khoản Roblox!";
      }
    }
  </script>

</body>
</html>
