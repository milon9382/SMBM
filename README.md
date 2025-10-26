<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Grocery Store</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      background-color: #f3f4f6;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #22c55e;
      color: white;
      text-align: center;
      padding: 15px 0;
      font-size: 22px;
      font-weight: bold;
    }
    .container {
      padding: 20px;
    }
    .input-group {
      margin-bottom: 15px;
    }
    input[type="text"], input[type="tel"] {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 10px;
      margin-top: 5px;
      font-size: 16px;
    }
    .menu {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }
    .item {
      background-color: white;
      border-radius: 12px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      padding: 10px;
      text-align: center;
    }
    .item h3 {
      margin: 10px 0 5px;
      font-size: 18px;
    }
    .item p {
      color: gray;
      font-size: 15px;
    }
    button {
      background-color: #16a34a;
      color: white;
      border: none;
      padding: 8px 12px;
      border-radius: 8px;
      cursor: pointer;
      margin-top: 5px;
    }
    button:hover {
      background-color: #15803d;
    }
  </style>
</head>
<body>
  <header>🛒 গোসারি ষ্টোর</header>

  <div class="container">
    <div class="input-group">
      <label>গ্রাহকের নাম:</label>
      <input type="text" id="customerName" placeholder="নাম লিখুন">
    </div>
    <div class="input-group">
      <label>মোবাইল নাম্বার:</label>
      <input type="tel" id="customerPhone" placeholder="মোবাইল নাম্বার লিখুন">
    </div>

    <h2>🧾 দোকানের মেনু</h2>
    <div class="menu" id="menuList"></div>
  </div>

  <script>
    const items = [
      { name: "চাল", price: 60 },
      { name: "আটা", price: 45 },
      { name: "তেল", price: 160 },
      { name: "চিনি", price: 55 },
      { name: "লবণ", price: 25 },
      { name: "ডাল", price: 90 },
      { name: "বিস্কুট", price: 20 },
      { name: "ডিম", price: 7 },
      { name: "চা", price: 150 },
      { name: "দুধ", price: 70 },
      { name: "সাবান", price: 35 },
      { name: "শ্যাম্পু", price: 95 }
    ];

    const menuList = document.getElementById("menuList");

    items.forEach(item => {
      const div = document.createElement("div");
      div.classList.add("item");
      div.innerHTML = `
        <h3>${item.name}</h3>
        <p>দাম: ${item.price} টাকা</p>
        <button onclick="addToCart('${item.name}', ${item.price})">🛍 কিনুন</button>
      `;
      menuList.appendChild(div);
    });

    function addToCart(name, price) {
      const customer = document.getElementById("customerName").value;
      const phone = document.getElementById("customerPhone").value;

      if (!customer || !phone) {
        alert("দয়া করে গ্রাহকের নাম ও মোবাইল নাম্বার লিখুন!");
        return;
      }

      alert(`${customer} (${phone}) — আপনি ${name} ${price} টাকায় কিনেছেন ✅`);
    }
  </script>
</body>
</html>
