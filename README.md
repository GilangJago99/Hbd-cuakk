# Hbd-cuakk
Hbd
<!DOCTYPE html>
<html lang="id">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Selamat Ulang Tahun, Faris!</title>
 <style>
 body {
 font-family: 'Arial', sans-serif;
 background: linear-gradient(to right, #ffcccc, #ccffff); / Gradien warna pastel /
 display: flex;
 justify-content: center;
 align-items: center;
 min-height: 100vh;
 margin: 0;
 text-align: center;
 overflow: hidden; / Agar confetti tidak keluar dari layar /
 }
 .container {
 background-color: rgba(255, 255, 255, 0.8); / Latar belakang sedikit transparan /
 padding: 40px;
 border-radius: 15px;
 box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
 max-width: 600px;
 position: relative; / Penting untuk confetti /
 z-index: 1; / Agar konten muncul di atas confetti /
 }
 h1 {
 color: #e91e63; / Warna pink cerah /
 font-size: 3em;
 margin-bottom: 20px;
 animation: pulse 2s infinite; / Animasi berdenyut /
 }
 p {
 color: #333;
 font-size: 1.2em;
 line-height: 1.6;
 margin-bottom: 30px;
 }
 .button {
 background-color: #4CAF50; / Warna hijau cerah /
 color: white;
 padding: 15px 30px;
 text-decoration: none;
 border-radius: 8px;
 font-size: 1.1em;
 transition: background-color 0.3s ease;
 border: none;
 cursor: pointer;
 }
 .button:hover {
 background-color: #45a049; / Warna hijau lebih gelap saat hover /
 }

 / Styling untuk Confetti /
 .confetti {
 position: absolute;
 width: 10px;
 height: 10px;
 background-color: #fce38e; / Kuning cerah /
 top: -10px;
 opacity: 0;
 animation: confetti-fall 5s linear infinite, confetti-scatter 5s linear infinite;
 }
 .confetti:nth-child(odd) {
 background-color: #a8e063; / Hijau muda /
 animation-delay: 0.5s, 0.5s;
 }
 .confetti:nth-child(even) {
 background-color: #f7b733; / Oranye /
 animation-delay: 0s, 0s;
 }

 @keyframes pulse {
 0% { transform: scale(1); }
 50% { transform: scale(1.05); }
 100% { transform: scale(1); }
 }

 @keyframes confetti-fall {
 to {
 transform: translateY(100vh);
 opacity: 1;
 }
 }

 @keyframes confetti-scatter {
 from {
 transform: translateX(0);
 }
 to {
 transform: translateX(calc(100vw  var(--scatter-x, 1))); / Menggunakan variabel CSS /
 }
 }
 </style>
</head>
<body>
 <div class="confetti-container"></div> <!-- Wadah untuk confetti -->

 <div class="container">
 <h1>Selamat Ulang Tahun, Faris!</h1>
 <p>
 Halo Faris Adi Sasono! Selamat merayakan hari kelahiranmu yang istimewa ini. Semoga setiap langkahmu dipenuhi kebahagiaan, kesuksesan, dan cinta. Nikmati setiap momen di usiamu yang baru ini ya! 🎉
 </p>
 <button class="button" onclick="alert('Terima kasih sudah mengirim ucapan!')">Kirim Pesan</button>
 </div>

 <script>
 const confettiContainer = document.querySelector('.confetti-container');
 const colors = ['#fce38e', '#a8e063', '#f7b733', '#e91e63', '#3498db']; // Warna confetti

 function createConfetti() {
 const confetti = document.createElement('div');
 confetti.classList.add('confetti');

 // Acak warna
 confetti.style.backgroundColor = colors[Math.floor(Math.random()  colors.length)];

 // Acak posisi awal horizontal
 const scatterX = (Math.random() - 0.5)  2; // Nilai antara -1 dan 1
 confetti.style.setProperty('--scatter-x', scatterX);

 // Acak posisi awal vertikal (agar tidak semua muncul di atas)
 confetti.style.top = Math.random()  window.innerHeight + 'px';
 confetti.style.left = Math.random()  window.innerWidth + 'px';

 // Acak ukuran
 const size = Math.random()  10 + 5; // Ukuran antara 5px dan 15px
 confetti.style.width = size + 'px';
 confetti.style.height = size + 'px';

 confettiContainer.appendChild(confetti);

 // Hapus confetti setelah animasi selesai
 confetti.addEventListener('animationend', () => {
 confetti.remove();
 });
 }

 // Buat confetti secara berkala
 setInterval(createConfetti, 200); // Buat confetti setiap 200ms

 // Tambahkan beberapa confetti saat halaman pertama kali dimuat
 for (let i = 0; i < 100; i++) {
 setTimeout(createConfetti, i  50); // Delay sedikit agar confetti muncul bertahap
 }
 </script>
</body>
</html>
