<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>WA Blast Pro - Kirim WA Tanpa Save Nomor</title>
  <style>
    body {font-family: Arial; background: #0f172a; color: white; text-align: center; padding: 50px;}
    h1 {color: #00ff88;}
    textarea, input {width: 80%; padding: 15px; margin: 10px; border-radius: 10px;}
    button {background: #00ff88; color: black; padding: 15px 30px; font-size: 18px; border: none; border-radius: 10px; cursor: pointer;}
    button:hover {background: #00cc66;}
    #status {margin-top: 20px; font-weight: bold;}
  </style>
</head>
<body>
  <h1>🚀 WA BLAST PRO v2</h1>
  <p>Mau kirim ratusan WA sekaligus tanpa save nomor?</p>
  
  <textarea id="numbers" placeholder="Masukkan nomor WA (satu baris satu nomor, contoh: 081234567890)" rows="8"></textarea><br>
  <textarea id="message" placeholder="Tuliskan pesan kamu di sini..." rows="5"></textarea><br>
  
  <button onclick="startBlast()">💥 MULAI BLAST SEKARANG</button>
  <div id="status"></div>

  <script>
    function startBlast() {
      const numbers = document.getElementById("numbers").value.trim().split("\n");
      const message = encodeURIComponent(document.getElementById("message").value);
      const status = document.getElementById("status");
      
      if (!message || numbers.length === 0 || numbers[0] === "") {
        status.innerHTML = "Isi nomor dan pesan dulu bro!";
        return;
      }

      status.innerHTML = "Sedang kirim... Tunggu bentar ya 🔥";
      let sent = 0;

      numbers.forEach((num, i) => {
        setTimeout(() => {
          const cleanNum = num.trim().replace(/[^0-9]/g, "");
          if (cleanNum.length >= 10) {
            window.open(`https://wa.me/${cleanNum}?text=${message}`, "_blank");
            sent++;
            status.innerHTML = `Terkirim: ${sent} / ${numbers.length} nomor`;
          }
        }, i * 2000); // delay 2 detik biar ga kena blokir WA
      });
    }
  </script>
</body>
</html>{
  "version": 2,
  "builds": [
    {
      "src": "*.html",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    { "src": "/(.*)", "dest": "/index.html" }
  ]
}// license.js – sistem license super simple
const VALID_LICENSES = [
  "WA-PRO-2025-001", 
  "WA-PRO-2025-002", 
  "WA-PRO-2025-003",
  // 
];

const urlParams = new URLSearchParams(window.location.search);
const key = urlParams.get('key');

if (!key || !VALID_LICENSES.includes(key.toUpperCase())) {
  document.body.innerHTML = `
    <div style="padding:50px; text-align:center; font-family:Arial; color:#ff0066;">
      <h1>❌ LICENSE TIDAK VALID</h1>
      <p>Hubungi penjual untuk mendapatkan license resmi</p>
      <p>WA: 0812-9843-5726 </p>
    </div>`;
  throw new Error("License invalid");
}<head>
  ...
  <script src="license.js"></script>   <!-- TAMBAHIN BARIS INI -->
</head>
