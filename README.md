# EasyShop-
EasyShop Indonesia adalah platform digital berbasis hyperlocal yang membantu masyarakat memenuhi kebutuhan sehari-hari mulai dari sembako, kebersihan, hingga kuliner lokal secara cepat dan praktis, sekaligus mendukung UMKM di Kota Malang
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EasyShop - Warung Digital Indonesia</title>
<script src="https://cdn.tailwindcss.com"></script>

<!-- Favicon -->
<link rel="icon" href="logo.png">

</head>

<body class="bg-gray-50 font-sans">

<!-- NAVBAR -->
<nav class="bg-white shadow p-4 flex justify-between items-center">

    <div class="flex items-center gap-3">
        <img src="logo.png" class="w-12 h-12 rounded-full">
        <div>
            <h1 class="font-bold text-xl text-green-700">EasyShop</h1>
            <p class="text-xs text-gray-500">Semua kebutuhan dalam satu klik</p>
        </div>
    </div>

    <div class="hidden md:flex gap-6">
        <a href="#produk">Produk</a>
        <a href="#visi">Visi Misi</a>
        <a href="#tim">Tim</a>
    </div>

</nav>

<!-- HERO -->
<section class="text-center py-16 bg-green-100">
    <h2 class="text-4xl font-bold mb-4">Belanja Sekali, Semua Beres</h2>
    <p class="mb-6 text-gray-600">
        Sembako, makanan, kebutuhan rumah tangga langsung dalam 1 pesanan tanpa ribet.
    </p>
    <button onclick="scrollToProduk()" class="bg-green-600 text-white px-6 py-3 rounded shadow">
        Mulai Belanja
    </button>
</section>

<!-- PRODUK -->
<section id="produk" class="p-8">
    <h2 class="text-2xl font-bold mb-6 text-center">Kategori Produk</h2>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">

        <div class="card">Sembako<br>Rp5.000+</div>
        <div class="card">Kebutuhan Dapur<br>Rp3.000+</div>
        <div class="card">Kamar Mandi<br>Rp7.000+</div>
        <div class="card">Laundry<br>Rp8.000+</div>
        <div class="card">Fast Food<br>Rp10.000+</div>
        <div class="card">Frozen Food<br>Rp12.000+</div>
        <div class="card">Minuman<br>Rp2.000+</div>
        <div class="card">Snack & Jajanan<br>Rp1.000+</div>

    </div>
</section>

<!-- VISI MISI -->
<section id="visi" class="bg-white p-8">
    <h2 class="text-2xl font-bold mb-4">Visi & Misi</h2>

    <p class="mb-4">
        <b>Visi:</b><br>
        Menjadi platform warung digital nomor 1 di Indonesia yang memudahkan masyarakat dalam memenuhi kebutuhan sehari-hari.
    </p>

    <ul class="list-disc ml-6">
        <li>Menyediakan semua kebutuhan dalam satu aplikasi</li>
        <li>Memberikan harga ramah di kantong tanpa merusak pasar</li>
        <li>Mendukung UMKM lokal</li>
        <li>Layanan cepat, aman, dan terpercaya</li>
    </ul>
</section>

<!-- ALAMAT -->
<section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Lokasi</h2>
    <p>Kota Malang, Jawa Timur</p>
</section>

<!-- TIM -->
<section id="tim" class="bg-green-100 p-8">
    <h2 class="text-2xl font-bold mb-6 text-center">Tim EasyShop</h2>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-4 text-center">

        <div class="team">Adinda<br><span>Hacker (Tech)</span></div>
        <div class="team">Dymi<br><span>Hipster (Design)</span></div>
        <div class="team">Firya<br><span>Product Manager</span></div>
        <div class="team">Vicky<br><span>Hustle (Marketing)</span></div>

    </div>
</section>

<!-- FOOTER -->
<footer class="bg-gray-800 text-white p-6 text-center">
    <p>© 2026 EasyShop Indonesia</p>
    <p>WhatsApp: 085138596479</p>
</footer>

<!-- CHATBOX -->
<div class="fixed bottom-5 right-5">

    <button onclick="toggleChat()" 
    class="bg-green-600 text-white px-4 py-2 rounded-full shadow">
    Chat 24/7
    </button>

    <div id="chat" class="hidden bg-white w-64 h-80 mt-2 p-3 rounded shadow">

        <h3 class="font-bold mb-2">Customer Service</h3>

        <div id="messages" class="h-40 overflow-y-auto border p-2 text-sm mb-2"></div>

        <input id="msg" type="text" placeholder="Ketik pesan..."
        class="border w-full p-1">

        <button onclick="sendMsg()" 
        class="bg-green-600 text-white w-full mt-2 p-1">
        Kirim
        </button>

        <a href="https://wa.me/6285138596479" target="_blank"
        class="block text-center bg-green-500 text-white mt-2 p-1 rounded">
        WhatsApp Admin
        </a>

    </div>

</div>

<!-- STYLE -->
<style>
.card {
    background: white;
    padding: 20px;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    cursor: pointer;
    transition: 0.3s;
}
.card:hover {
    transform: scale(1.05);
}

.team {
    background: white;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.team span {
    font-size: 12px;
    color: gray;
}
</style>

<!-- SCRIPT -->
<script>

function scrollToProduk(){
    document.getElementById("produk").scrollIntoView({behavior:"smooth"});
}

function toggleChat(){
    document.getElementById("chat").classList.toggle("hidden");
}

function sendMsg(){
    let input = document.getElementById("msg");
    let val = input.value;

    if(val === "") return;

    let box = document.getElementById("messages");

    box.innerHTML += `<div><b>Kamu:</b> ${val}</div>`;
    box.innerHTML += `<div><b>Admin:</b> Terima kasih, kami siap membantu 😊</div>`;

    input.value = "";
    box.scrollTop = box.scrollHeight;
}

</script>

</body>
</html>
