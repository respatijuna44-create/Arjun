<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, shrink-to-fit=no">
  <title>Arjuna • Keuangan Jajan</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #1e2b1f 0%, #2c3a2b 100%);
      font-family: 'Segoe UI', 'Poppins', system-ui, -apple-system, sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 1.2rem;
      margin: 0;
    }

    .app-container {
      width: 100%;
      max-width: 480px;
      background: rgba(255, 248, 235, 0.95);
      backdrop-filter: blur(12px);
      background: #fef9e7;
      border-radius: 2.8rem;
      box-shadow: 0 30px 45px rgba(0, 0, 0, 0.35), 0 10px 20px rgba(0, 0, 0, 0.3);
      padding: 1.8rem 1.5rem 2.2rem;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      border: 2px solid #d4a373;
    }

    /* Header */
    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: #3f2e1d;
      margin: -0.4rem -0.2rem 0.2rem;
      padding: 0.9rem 1.5rem;
      border-radius: 3rem;
      color: #f9e0ae;
      box-shadow: 0 8px 0 #241a0f;
      border-bottom: 2px solid #c49a6c;
    }

    .logo-area {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .arjuna-icon {
      background: #d4a373;
      color: #2d2412;
      font-size: 1.8rem;
      font-weight: 800;
      width: 2.8rem;
      height: 2.8rem;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      box-shadow: 0 4px 0 #6b4f32;
      text-transform: uppercase;
    }

    .app-title {
      font-size: 1.9rem;
      font-weight: 700;
      letter-spacing: 1px;
      color: #f3d59c;
      text-shadow: 2px 2px 0 #3a2c1b;
      line-height: 1.2;
    }

    .date-badge {
      background: #f3d59c;
      color: #3f2e1d;
      font-weight: 700;
      padding: 0.5rem 1rem;
      border-radius: 2rem;
      font-size: 0.85rem;
      box-shadow: inset 0 1px 4px rgba(0,0,0,0.2);
    }

    /* total card */
    .total-card {
      background: #2d2412;
      border-radius: 2rem;
      padding: 1.2rem 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: #ffe6b3;
      box-shadow: 0 10px 0 #1a140a;
      margin-top: 0.3rem;
      border: 2px solid #c49a6c;
    }

    .total-label {
      font-size: 1.2rem;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .total-price {
      font-size: 2.2rem;
      font-weight: 800;
      background: #ffecbc;
      color: #2d2412;
      padding: 0.3rem 1.5rem;
      border-radius: 2.5rem;
      box-shadow: inset 0 2px 6px rgba(0,0,0,0.3);
    }

    /* Menu grid */
    .menu-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      justify-content: center;
      margin: 0.2rem 0 0.5rem;
    }

    .menu-item {
      flex: 1 1 calc(50% - 0.8rem);
      min-width: 130px;
      background: #fff6e5;
      border-radius: 2rem;
      padding: 1.2rem 0.5rem 1rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.4rem;
      box-shadow: 0 8px 0 #b4925a, 0 6px 12px rgba(0,0,0,0.2);
      transition: all 0.05s ease;
      cursor: pointer;
      border: 2px solid #d4a373;
      background: #faf3e0;
      user-select: none;
      -webkit-tap-highlight-color: transparent;
    }

    .menu-item:active {
      transform: translateY(4px);
      box-shadow: 0 4px 0 #7b5e3b, 0 6px 10px rgba(0,0,0,0.2);
      background: #f3e5ca;
    }

    .emoji-food {
      font-size: 2.8rem;
      filter: drop-shadow(2px 4px 4px rgba(0,0,0,0.4));
      margin-bottom: 0.1rem;
    }

    .menu-name {
      font-weight: 700;
      font-size: 1.2rem;
      color: #4a3922;
      background: #eedbbc;
      padding: 0.2rem 1.2rem;
      border-radius: 2rem;
      letter-spacing: 0.5px;
    }

    .menu-price {
      font-weight: 800;
      font-size: 1.1rem;
      color: #2d2412;
      background: #ffe3a5;
      padding: 0.2rem 1rem;
      border-radius: 1.5rem;
      margin-top: 0.2rem;
    }

    /* daftar pesanan */
    .order-section {
      background: #f5e7d3;
      border-radius: 2rem;
      padding: 1rem 1.2rem;
      border: 2px dashed #b28b5b;
      max-height: 150px;
      overflow-y: auto;
      box-shadow: inset 0 0 6px rgba(0,0,0,0.1);
    }

    .order-list {
      list-style: none;
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      align-items: center;
    }

    .order-item {
      background: #ffffffd6;
      padding: 0.4rem 0.9rem;
      border-radius: 2rem;
      font-weight: 600;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      gap: 0.3rem;
      box-shadow: 0 2px 4px rgba(0,0,0,0.2);
      color: #3a2c1b;
      backdrop-filter: blur(4px);
    }

    .remove-order {
      background: #c44f4f;
      color: white;
      border: none;
      border-radius: 50%;
      width: 1.2rem;
      height: 1.2rem;
      font-weight: bold;
      font-size: 0.7rem;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      margin-left: 0.2rem;
      box-shadow: 0 2px 0 #6e2c2c;
      transition: 0.1s ease;
    }

    .remove-order:active {
      transform: scale(0.9);
      background: #a13d3d;
    }

    .empty-order {
      color: #8b7355;
      font-style: italic;
      font-weight: 500;
      padding: 0.3rem;
    }

    .reset-btn {
      background: #d4a373;
      border: none;
      color: #2d2412;
      font-weight: 800;
      font-size: 1rem;
      padding: 0.8rem 1.8rem;
      border-radius: 2.5rem;
      letter-spacing: 0.8px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.3rem;
      margin-top: 0.2rem;
      box-shadow: 0 6px 0 #7b5e3b;
      cursor: pointer;
      transition: 0.06s ease;
      border: 2px solid #b28b5b;
      background: #e7b87a;
      text-transform: uppercase;
      width: fit-content;
      align-self: center;
      padding-left: 2rem;
      padding-right: 2rem;
    }

    .reset-btn:active {
      transform: translateY(3px);
      box-shadow: 0 3px 0 #5a432a;
    }

    .footer-note {
      text-align: center;
      color: #5e4a31;
      font-weight: 600;
      font-size: 0.8rem;
      margin-top: -0.2rem;
    }
  </style>
</head>
<body>
  <div class="app-container">
    <!-- HEADER -->
    <div class="header">
      <div class="logo-area">
        <span class="arjuna-icon">A</span>
        <span class="app-title">Arjuna</span>
      </div>
      <div class="date-badge" id="liveDate"></div>
    </div>

    <!-- TOTAL -->
    <div class="total-card">
      <span class="total-label">💰 Total Jajan</span>
      <span class="total-price" id="totalDisplay">Rp0</span>
    </div>

    <!-- MENU GRID (bisa diklik) -->
    <div class="menu-grid" id="menuContainer">
      <!-- data menu akan dirender lewat javascript biar dinamis -->
    </div>

    <!-- DAFTAR PESANAN AKTIF -->
    <div class="order-section">
      <ul class="order-list" id="orderList">
        <li class="empty-order">🛒 Belum ada pesanan</li>
      </ul>
    </div>

    <!-- RESET BUTTON -->
    <button class="reset-btn" id="resetButton">
      <span>🗑️</span> Reset Semua
    </button>
    <div class="footer-note">Ketuk menu untuk tambah · klik ❌ untuk hapus</div>
  </div>

  <script>
    (function() {
      // --- DATA MENU ARJUNA ---
      const menuItems = [
        { id: 'cilok', name: 'Cilok', emoji: '🍡', price: 2000 },
        { id: 'bakso', name: 'Bakso', emoji: '🍲', price: 5000 },
        { id: 'sosis', name: 'Sosis', emoji: '🌭', price: 4000 },
        { id: 'esteh', name: 'Es Teh', emoji: '🧊🍵', price: 3000 }
      ];

      // State pesanan: array of objects { id, name, emoji, price, orderId unik }
      let orders = [];

      // DOM elements
      const menuContainer = document.getElementById('menuContainer');
      const orderListEl = document.getElementById('orderList');
      const totalDisplay = document.getElementById('totalDisplay');
      const resetBtn = document.getElementById('resetButton');
      const liveDateEl = document.getElementById('liveDate');

      // --- Fungsi format Rupiah ---
      function formatRupiah(angka) {
        return 'Rp' + angka.toLocaleString('id-ID');
      }

      // --- Hitung total ---
      function calculateTotal() {
        return orders.reduce((sum, item) => sum + item.price, 0);
      }

      // --- Update tampilan total & list pesanan ---
      function renderOrders() {
        // Update total
        const total = calculateTotal();
        totalDisplay.textContent = formatRupiah(total);

        // Render list pesanan
        orderListEl.innerHTML = '';

        if (orders.length === 0) {
          orderListEl.innerHTML = '<li class="empty-order">🛒 Belum ada pesanan</li>';
          return;
        }

        orders.forEach((order, index) => {
          const li = document.createElement('li');
          li.className = 'order-item';
          // Tampilkan emoji + nama + harga
          li.innerHTML = `
            <span>${order.emoji} ${order.name}</span>
            <span style="font-weight:700; margin-left:0.2rem;">${formatRupiah(order.price)}</span>
            <button class="remove-order" data-index="${index}" aria-label="Hapus pesanan">✕</button>
          `;
          orderListEl.appendChild(li);
        });

        // Tambahkan event listener untuk setiap tombol hapus (setelah render)
        document.querySelectorAll('.remove-order').forEach(btn => {
          btn.addEventListener('click', function(e) {
            e.stopPropagation(); // hindari event lain
            const index = parseInt(this.getAttribute('data-index'), 10);
            if (!isNaN(index) && index >= 0 && index < orders.length) {
              // Hapus pesanan berdasarkan index
              orders.splice(index, 1);
              renderOrders(); // render ulang
            }
          });
        });
      }

      // --- Tambah pesanan berdasarkan menu id ---
      function addOrder(menuId) {
        const menu = menuItems.find(m => m.id === menuId);
        if (!menu) return;

        // Buat objek pesanan baru (setiap klik menambah item baru)
        const newOrder = {
          id: menu.id,
          name: menu.name,
          emoji: menu.emoji,
          price: menu.price,
          orderId: Date.now() + Math.random() // unik
        };
        orders.push(newOrder);
        renderOrders();
      }

      // --- Reset semua pesanan ---
      function resetAllOrders() {
        if (orders.length === 0) return;
        orders = [];
        renderOrders();
      }

      // --- Render menu grid (dengan klik) ---
      function renderMenu() {
        menuContainer.innerHTML = '';
        menuItems.forEach(menu => {
          const card = document.createElement('div');
          card.className = 'menu-item';
          card.setAttribute('data-menu-id', menu.id);
          card.innerHTML = `
            <span class="emoji-food">${menu.emoji}</span>
            <span class="menu-name">${menu.name}</span>
            <span class="menu-price">${formatRupiah(menu.price)}</span>
          `;
          
          // Event klik untuk menambah pesanan
          card.addEventListener('click', function(e) {
            const menuId = this.getAttribute('data-menu-id');
            if (menuId) {
              addOrder(menuId);
            }
          });

          menuContainer.appendChild(card);
        });
      }

      // --- Tampilkan tanggal hari ini (estetik) ---
      function setCurrentDate() {
        const today = new Date();
        const options = { day: 'numeric', month: 'short', year: 'numeric' };
        liveDateEl.textContent = today.toLocaleDateString('id-ID', options);
      }

      // --- Event listener tombol reset ---
      resetBtn.addEventListener('click', resetAllOrders);

      // --- Inisialisasi aplikasi ---
      function init() {
        setCurrentDate();
        renderMenu();
        // pastikan orders kosong saat mulai
        orders = [];
        renderOrders();
      }

      // Jalankan
      init();
    })();
  </script>
</body>
</html>
