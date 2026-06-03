
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>MBG Kitchen Story - Chef Masak & Jualan Online/Offline</title>
    <style>
        * {
            user-select: none;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #1f4f2d, #0a2f1a);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', 'Poppins', 'Fredoka One', cursive, sans-serif;
            margin: 0;
            padding: 20px;
        }

        /* GAME WRAPPER */
        .game-wrapper {
            max-width: 1400px;
            width: 100%;
            background: #fef0cf;
            border-radius: 80px 80px 70px 70px;
            box-shadow: 0 30px 35px rgba(0, 0, 0, 0.5);
            overflow: hidden;
            transition: all 0.2s;
            border-bottom: 8px solid #f4b642;
        }

        /* Header */
        .game-header {
            background: #2d2b26;
            padding: 12px 30px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 15px;
            border-bottom: 4px solid #ffb347;
        }

        .points-area {
            background: #fae67a;
            padding: 6px 25px;
            border-radius: 50px;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.6rem;
            box-shadow: inset 0 -2px 0 #c49a3a, 0 6px 12px black;
        }

        .points-area span:first-child {
            font-size: 1.3rem;
        }

        .point-number {
            font-size: 2.1rem;
            font-weight: 800;
            color: #dd6b20;
            text-shadow: 0 2px 0 #fff0b5;
        }

        .chef-title {
            background: #533e28;
            padding: 6px 20px;
            border-radius: 40px;
            color: #ffdfaa;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .reset-btn {
            background: #c2571a;
            border: none;
            color: white;
            font-weight: bold;
            padding: 6px 20px;
            border-radius: 40px;
            cursor: pointer;
            transition: 0.1s;
            font-size: 1rem;
            box-shadow: 0 3px 0 #6e2c00;
        }

        .reset-btn:active {
            transform: translateY(2px);
            box-shadow: 0 1px 0 #6e2c00;
        }

        /* MAIN CONTENT: chef + dapur + jualan */
        .main-dashboard {
            display: flex;
            flex-wrap: wrap;
            padding: 25px 25px;
            gap: 25px;
        }

        /* CHEF & KITCHEN SECTION (kiri) */
        .chef-kitchen {
            flex: 2;
            min-width: 280px;
            background: #fff6e6;
            border-radius: 60px;
            padding: 18px;
            box-shadow: inset 0 0 0 2px white, 0 10px 18px rgba(0,0,0,0.1);
        }

        .chef-card {
            display: flex;
            align-items: center;
            gap: 18px;
            background: #f9e2b7;
            border-radius: 70px;
            padding: 12px 20px;
            margin-bottom: 20px;
            box-shadow: 0 6px 0 #cb9c62;
        }

        .chef-avatar {
            font-size: 4.2rem;
            background: #ffd966;
            border-radius: 100px;
            padding: 6px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.2);
            transition: transform 0.1s ease;
        }

        .chef-talk {
            background: white;
            padding: 6px 18px;
            border-radius: 40px;
            font-weight: bold;
            color: #b45f2b;
            font-size: 0.9rem;
            max-width: 180px;
        }

        .menu-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            justify-content: center;
            margin: 20px 0;
        }

        .food-btn {
            background: white;
            width: 115px;
            border-radius: 50px;
            text-align: center;
            padding: 12px 4px;
            cursor: pointer;
            transition: 0.07s linear;
            box-shadow: 0 8px 0 #b88242;
            border: 1px solid #ffda9e;
        }

        .food-btn:active {
            transform: translateY(4px);
            box-shadow: 0 3px 0 #b88242;
        }

        .food-icon {
            font-size: 3rem;
        }

        .food-name {
            font-weight: bold;
            font-size: 1rem;
        }

        .price-tag {
            background: #ffd58c;
            border-radius: 30px;
            padding: 2px 8px;
            font-size: 0.7rem;
            font-weight: bold;
            display: inline-block;
            margin-top: 5px;
        }

        .cook-animation {
            background: #ebd5b3;
            border-radius: 60px;
            padding: 12px;
            text-align: center;
            font-weight: bold;
            margin-top: 12px;
            transition: 0.2s;
        }

        .inventory-status {
            background: #c7924b;
            color: white;
            padding: 10px;
            border-radius: 40px;
            margin-top: 15px;
            font-size: 0.8rem;
            text-align: center;
            font-weight: bold;
        }

        /* SALES AREA (kanan) OFFLINE + ONLINE */
        .sales-hub {
            flex: 3;
            min-width: 320px;
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .offline-box, .online-box {
            background: #fffaec;
            border-radius: 50px;
            padding: 18px 20px;
            box-shadow: 0 10px 0 #ba8b4a;
        }

        .section-header {
            font-size: 1.5rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 12px;
            border-left: 10px solid #f99b2e;
            padding-left: 18px;
            margin-bottom: 16px;
        }

        .customer-row {
            background: #ffffffdb;
            border-radius: 50px;
            margin-bottom: 12px;
            padding: 12px 18px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            backdrop-filter: blur(2px);
            box-shadow: 0 2px 6px rgba(0,0,0,0.05);
        }

        .cust-info {
            display: flex;
            gap: 10px;
            align-items: center;
            font-weight: bold;
        }

        .order-badge {
            background: #fce2b4;
            padding: 4px 14px;
            border-radius: 30px;
            font-size: 0.8rem;
        }

        .serve-action {
            background: #498c5f;
            border: none;
            color: white;
            font-weight: bold;
            padding: 6px 20px;
            border-radius: 40px;
            cursor: pointer;
            transition: 0.05s linear;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        .serve-action:active {
            transform: scale(0.96);
        }

        .online-item {
            background: #ffefcf;
            border-radius: 60px;
            padding: 12px 18px;
            margin-bottom: 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        footer {
            background: #e3caa3;
            text-align: center;
            padding: 10px;
            font-weight: bold;
            color: #6a3e1a;
            font-size: 0.75rem;
        }

        button:disabled {
            opacity: 0.5;
            transform: none;
        }

        @media (max-width: 800px) {
            .food-btn { width: 90px; }
            .chef-avatar { font-size: 3rem; }
        }
    </style>
</head>
<body>
<div class="game-wrapper">
    <div class="game-header">
        <div class="points-area">
            <span>🍲 MBG POINTS</span>
            <span class="point-number" id="pointValue">0</span>
        </div>
        <div class="chef-title">
            👨‍🍳 HEAD CHEF : BAGAS 🧑‍🍳
        </div>
        <button class="reset-btn" id="resetGameBtn">🔄 RESET DAPUR</button>
    </div>

    <div class="main-dashboard">
        <!-- AREA CHEF + DAPUR + MASAK -->
        <div class="chef-kitchen">
            <div class="chef-card">
                <div class="chef-avatar" id="chefEmoji">👨‍🍳🔪</div>
                <div class="chef-talk" id="chefSays">Halo! Klik menu untuk masak! 🍳</div>
            </div>
            <div class="menu-grid" id="menuContainer"></div>
            <div class="cook-animation" id="cookMessage">
                🔥 Klik salah satu menu di atas, Chef akan masak! 🔥
            </div>
            <div class="inventory-status" id="stockInfo">
                📦 Stok siap jual: -
            </div>
        </div>

        <!-- SALES HUB: offline + online -->
        <div class="sales-hub">
            <!-- OFFLINE CUSTOMERS -->
            <div class="offline-box">
                <div class="section-header">
                    🧑‍🤝‍🧑 PELANGGAN OFFLINE 👩‍🤝‍👨
                    <span style="font-size:0.7rem;">(+10 poin)</span>
                </div>
                <div id="offlineList"></div>
                <div style="font-size:0.7rem; margin-top: 8px; text-align:center;">✨ Setiap layanan offline +10 poin ✨</div>
            </div>
            <!-- ONLINE ORDERS -->
            <div class="online-box">
                <div class="section-header">
                    📱 PESANAN ONLINE 🌐
                    <span style="font-size:0.7rem;">(+15~18 poin)</span>
                </div>
                <div id="onlineList"></div>
                <div style="font-size:0.7rem; margin-top: 8px; text-align:center;">🚚 Online memberi keuntungan lebih besar! 🚀</div>
            </div>
        </div>
    </div>
    <footer>
        🧑‍🍳 CARA MAIN: Chef (klik makanan) memasak ➕ stok ➡ layani pembeli offline/online ➡ kumpulkan poin! ⭐
    </footer>
</div>

<script>
    // ---------- DATA MASAKAN (MENU) ----------
    const MENU = [
        { id: "nasgor", name: "Nasi Goreng", emoji: "🍚🔥", basePoints: 10, onlinePoints: 16 },
        { id: "miegor", name: "Mie Goreng", emoji: "🍜✨", basePoints: 10, onlinePoints: 15 },
        { id: "ayamkremes", name: "Ayam Kremes", emoji: "🍗💥", basePoints: 12, onlinePoints: 18 },
        { id: "sateayam", name: "Sate Ayam", emoji: "🍢🥜", basePoints: 12, onlinePoints: 18 },
        { id: "esjeruk", name: "Es Jeruk", emoji: "🍊🧊", basePoints: 6, onlinePoints: 12 },
        { id: "brownis", name: "Brownis", emoji: "🍫🍰", basePoints: 8, onlinePoints: 14 }
    ];

    // State Game
    let mbgPoints = 150;       // poin awal
    let inventory = {};        // stok makanan berdasarkan id
    let offlineCustomers = [];  // array pelanggan offline
    let onlineOrders = [];      // array pesanan online

    // Inisialisasi stok 0
    function initStock() {
        MENU.forEach(item => { inventory[item.id] = 0; });
    }

    // Generate pelanggan offline (random)
    function generateOfflineCustomer() {
        const randomMenu = MENU[Math.floor(Math.random() * MENU.length)];
        return {
            id: "off_" + Date.now() + "_" + Math.random(),
            foodId: randomMenu.id,
            foodName: randomMenu.name,
            emoji: randomMenu.emoji,
            reward: randomMenu.basePoints
        };
    }

    // Generate pesanan online (random)
    function generateOnlineOrder() {
        const randomMenu = MENU[Math.floor(Math.random() * MENU.length)];
        return {
            id: "on_" + Date.now() + "_" + Math.random(),
            foodId: randomMenu.id,
            foodName: randomMenu.name,
            emoji: randomMenu.emoji,
            reward: randomMenu.onlinePoints
        };
    }

    // Fungsi memasak (dipanggil saat klik menu, chef masak)
    function cookByChef(foodId, foodName, foodEmoji) {
        if (!inventory.hasOwnProperty(foodId)) return;
        // masak +1 stok
        inventory[foodId] += 1;
        
        // animasi chef & pesan
        const chefAvatar = document.getElementById("chefEmoji");
        const chefTalk = document.getElementById("chefSays");
        const cookMsgDiv = document.getElementById("cookMessage");
        
        chefAvatar.style.transform = "scale(1.1)";
        setTimeout(() => { if(chefAvatar) chefAvatar.style.transform = ""; }, 200);
        chefTalk.innerHTML = `🍳 SEDANG MASAK ${foodName} 🍳`;
        cookMsgDiv.innerHTML = `👨‍🍳 Chef Bagas berhasil memasak 1 porsi ${foodEmoji} ${foodName}! +1 stok! 🎉`;
        
        setTimeout(() => {
            if(chefTalk) chefTalk.innerHTML = "Apa yang ingin dimasak, Bos? 👨‍🍳";
            if(cookMsgDiv) cookMsgDiv.innerHTML = "🔥 Klik menu, Chef akan masak dengan penuh cinta 🔥";
        }, 2000);
        
        updateUI();
        // tambahkan efek suara visual tip
        showFloatingMsg(`+1 ${foodName} siap jual!`, "#3c9e5f");
    }

    // LAYANI OFFLINE
    function serveOffline(customer, index) {
        const needed = customer.foodId;
        if (inventory[needed] > 0) {
            inventory[needed] -= 1;
            mbgPoints += customer.reward;
            offlineCustomers.splice(index, 1);
            showFloatingMsg(`+${customer.reward} poin (Offline)`, "#e67e22");
            // Jika antrian kosong, spawn pelanggan baru dengan delay
            setTimeout(() => {
                if (offlineCustomers.length < 3) {
                    offlineCustomers.push(generateOfflineCustomer());
                    updateUI();
                }
            }, 400);
            updateUI();
        } else {
            showFloatingMsg(`Stok ${customer.foodName} habis! Masak dulu, Chef!`, "#c0392b");
        }
    }

    // LAYANI ONLINE
    function serveOnline(order, index) {
        const needed = order.foodId;
        if (inventory[needed] > 0) {
            inventory[needed] -= 1;
            mbgPoints += order.reward;
            onlineOrders.splice(index, 1);
            showFloatingMsg(`📱 +${order.reward} poin (Online Delivery)`, "#2c7da0");
            setTimeout(() => {
                if (onlineOrders.length < 2) {
                    onlineOrders.push(generateOnlineOrder());
                    updateUI();
                }
            }, 500);
            updateUI();
        } else {
            showFloatingMsg(`⚠️ Stok ${order.foodName} online habis, masak dulu!`, "#b33b2c");
        }
    }

    // Spawn antrian awal
    function initGameWorld() {
        initStock();
        mbgPoints = 140;
        offlineCustomers = [];
        onlineOrders = [];
        // spawn 3 offline dan 2 online
        for(let i=0; i<3; i++) offlineCustomers.push(generateOfflineCustomer());
        for(let i=0; i<2; i++) onlineOrders.push(generateOnlineOrder());
        // bonus stok awal supaya tidak frustasi
        inventory["nasgor"] = 2;
        inventory["miegor"] = 2;
        inventory["esjeruk"] = 1;
        updateUI();
    }

    // Reset game
    function resetFullGame() {
        initStock();
        mbgPoints = 150;
        offlineCustomers = [];
        onlineOrders = [];
        for(let i=0; i<3; i++) offlineCustomers.push(generateOfflineCustomer());
        for(let i=0; i<2; i++) onlineOrders.push(generateOnlineOrder());
        inventory["nasgor"] = 2;
        inventory["miegor"] = 2;
        inventory["esjeruk"] = 1;
        updateUI();
        document.getElementById("chefSays").innerHTML = "Warung direset! Yuk masak lagi! 👨‍🍳";
        showFloatingMsg("✨ SEMANGAT BARU, JUALAN LAGI! ✨", "#f1c40f");
    }

    // Update seluruh tampilan UI (poin, stok, pelanggan, online, dll)
    function updateUI() {
        document.getElementById("pointValue").innerText = Math.floor(mbgPoints);
        
        // update inventory tampilan
        const stockEntries = Object.entries(inventory).map(([id, qty]) => {
            const menuItem = MENU.find(m => m.id === id);
            return `${menuItem?.emoji || id} ${menuItem?.name || id}: ${qty}`;
        }).join("   ");
        document.getElementById("stockInfo").innerHTML = `🍱 STOK: ${stockEntries || "Kosong, segera masak!"}`;
        
        // render semua menu masakan (dapur)
        const menuContainer = document.getElementById("menuContainer");
        menuContainer.innerHTML = "";
        MENU.forEach(menu => {
            const btn = document.createElement("div");
            btn.className = "food-btn";
            btn.setAttribute("data-id", menu.id);
            btn.innerHTML = `
                <div class="food-icon">${menu.emoji}</div>
                <div class="food-name">${menu.name}</div>
                <div class="price-tag">💰 jual: ${menu.basePoints}/${menu.onlinePoints}</div>
            `;
            btn.addEventListener("click", (e) => {
                e.stopPropagation();
                cookByChef(menu.id, menu.name, menu.emoji);
            });
            menuContainer.appendChild(btn);
        });
        
        // Render OFFLINE CUSTOMERS
        const offlineDiv = document.getElementById("offlineList");
        if (offlineCustomers.length === 0) {
            offlineDiv.innerHTML = `<div style="padding:20px; text-align:center;">🤷‍♂️ Antrian kosong, coba tunggu sebentar... 🤷‍♀️</div>`;
            // auto spawn kalau benar2 kosong
            if(offlineCustomers.length === 0) offlineCustomers.push(generateOfflineCustomer());
        } else {
            offlineDiv.innerHTML = "";
            offlineCustomers.forEach((cust, idx) => {
                const row = document.createElement("div");
                row.className = "customer-row";
                row.innerHTML = `
                    <div class="cust-info">
                        <span style="font-size:1.7rem;">${cust.emoji}</span>
                        <span>🧑‍🍳 Pesan: <strong>${cust.foodName}</strong></span>
                        <span class="order-badge">🏆 +${cust.reward} poin</span>
                    </div>
                    <button class="serve-action" data-offline-index="${idx}">🍽️ Layani Offline</button>
                `;
                offlineDiv.appendChild(row);
            });
            // attach event listeners
            document.querySelectorAll('[data-offline-index]').forEach(btn => {
                btn.removeEventListener('click', handleOfflineServe);
                btn.addEventListener('click', handleOfflineServe);
            });
        }
        
        // Render ONLINE ORDERS
        const onlineDiv = document.getElementById("onlineList");
        if (onlineOrders.length === 0) {
            onlineDiv.innerHTML = `<div style="padding:20px; text-align:center;">📭 Belum ada pesanan online, cek koneksi🍔</div>`;
            if(onlineOrders.length === 0) onlineOrders.push(generateOnlineOrder());
        } else {
            onlineDiv.innerHTML = "";
            onlineOrders.forEach((order, idx) => {
                const orderElement = document.createElement("div");
                orderElement.className = "online-item";
                orderElement.innerHTML = `
                    <div>
                        <span style="font-size:1.5rem;">${order.emoji}</span>
                        <strong> ${order.foodName}</strong>  |  💎 +${order.reward} poin
                    </div>
                    <button class="serve-action" data-online-index="${idx}">📦 Kirim Online</button>
                `;
                onlineDiv.appendChild(orderElement);
            });
            document.querySelectorAll('[data-online-index]').forEach(btn => {
                btn.removeEventListener('click', handleOnlineServe);
                btn.addEventListener('click', handleOnlineServe);
            });
        }
        
        // Spawner otomatis tambahan jika antrian sepi (biar rame)
        if (offlineCustomers.length < 2 && Math.random() < 0.4) offlineCustomers.push(generateOfflineCustomer());
        if (onlineOrders.length < 1 && Math.random() < 0.4) onlineOrders.push(generateOnlineOrder());
    }
    
    // Handler offline
    function handleOfflineServe(e) {
        const btn = e.currentTarget;
        const idxAttr = btn.getAttribute('data-offline-index');
        if(idxAttr !== null) {
            const idx = parseInt(idxAttr);
            if(!isNaN(idx) && offlineCustomers[idx]) {
                serveOffline(offlineCustomers[idx], idx);
            }
        }
    }
    
    // Handler online
    function handleOnlineServe(e) {
        const btn = e.currentTarget;
        const idxAttr = btn.getAttribute('data-online-index');
        if(idxAttr !== null) {
            const idx = parseInt(idxAttr);
            if(!isNaN(idx) && onlineOrders[idx]) {
                serveOnline(onlineOrders[idx], idx);
            }
        }
    }
    
    // floating message notifikasi
    function showFloatingMsg(msg, color = "#f39c12") {
        let toast = document.getElementById("floatingToast");
        if(!toast) {
            const div = document.createElement("div");
            div.id = "floatingToast";
            div.style.position = "fixed";
            div.style.bottom = "30px";
            div.style.left = "50%";
            div.style.transform = "translateX(-50%)";
            div.style.backgroundColor = "#1e2a1f";
            div.style.color = "white";
            div.style.padding = "12px 28px";
            div.style.borderRadius = "50px";
            div.style.fontWeight = "bold";
            div.style.zIndex = "9999";
            div.style.fontFamily = "inherit";
            div.style.boxShadow = "0 4px 20px black";
            div.style.borderLeft = `6px solid ${color}`;
            div.style.pointerEvents = "none";
            document.body.appendChild(div);
            toast = div;
        }
        toast.style.borderLeftColor = color;
        toast.innerHTML = msg;
        toast.style.opacity = "1";
        clearTimeout(window.toastTimer);
        window.toastTimer = setTimeout(() => {
            if(toast) toast.style.opacity = "0";
        }, 1700);
    }
    
    // Periodic spawner alami agar game hidup
    let periodicSpawn;
    function startAutoSpawn() {
        if(periodicSpawn) clearInterval(periodicSpawn);
        periodicSpawn = setInterval(() => {
            if(document.getElementById("pointValue")) {
                if(offlineCustomers.length < 4) {
                    offlineCustomers.push(generateOfflineCustomer());
                    updateUI();
                }
                if(onlineOrders.length < 3) {
                    onlineOrders.push(generateOnlineOrder());
                    updateUI();
                }
            }
        }, 7000);
    }
    
    // Reset button event
    document.getElementById("resetGameBtn").addEventListener("click", () => {
        resetFullGame();
    });
    
    // Inisiasi awal
    initGameWorld();
    startAutoSpawn();
    // Extra menjaga UI agar selalu terupdate ketika tidak ada interaksi
    setInterval(() => {
        if(offlineCustomers.length === 0) offlineCustomers.push(generateOfflineCustomer());
        if(onlineOrders.length === 0) onlineOrders.push(generateOnlineOrder());
        updateUI();
    }, 6000);
    
    // trigger pertama update
    window.addEventListener("load", () => {
        updateUI();
        // Efek chef menyapa
        setTimeout(() => {
            const chefTalkDiv = document.getElementById("chefSays");
            if(chefTalkDiv) chefTalkDiv.innerHTML = "Ayo masak, banyak pembeli nunggu! 🍲";
        }, 800);
    });
</script>
</body>
</html>
```
