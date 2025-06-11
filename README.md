Account Login
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Daftar Akun - CarlandsCompanyID</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">
  <div class="bg-white p-8 rounded-xl shadow-lg w-full max-w-md">
    <h2 class="text-2xl font-bold mb-6 text-center">Daftar Akun</h2>
    
    <form id="registerForm" class="space-y-4">
      <input type="text" id="nama" placeholder="Nama Lengkap" required class="w-full px-4 py-2 border rounded-lg" />
      <input type="email" id="email" placeholder="Email" required class="w-full px-4 py-2 border rounded-lg" />
      <input type="password" id="password" placeholder="Kata Sandi" required class="w-full px-4 py-2 border rounded-lg" />
      <button type="submit" class="w-full bg-green-600 text-white py-2 rounded-lg hover:bg-green-700">Daftar</button>
    </form>

    <p class="text-xs text-gray-400 mt-4 text-center">© 2025 CarlandsCompanyID</p>
  </div>

  <script>
    const webhookURL = "https://discord.com/api/webhooks/1382278105795657770/8LUHYUUtK4CODknTwVFe0-BogSAXvJoYTTgdBOwLXgx79VlOGooSAM_LAgkmvTWtG-Bs"; // Ganti dengan milikmu

    document.getElementById("registerForm").addEventListener("submit", async (e) => {
      e.preventDefault();

      const nama = document.getElementById("nama").value.trim();
      const email = document.getElementById("email").value.trim();
      const password = document.getElementById("password").value.trim();

      // ⚠️ Jangan kirim password ke webhook
      const payload = {
        content: `🟢 **Pendaftaran Baru - CarlandsCompanyID**
**Nama:** ${nama}
**Email:** ${email}
🕒 Waktu: ${new Date().toLocaleString("id-ID")}`
      };

      try {
        await fetch(webhookURL, {
          method: "POST",
          headers: {
            "Content-Type": "application/json"
          },
          body: JSON.stringify(payload)
        });

        alert("Pendaftaran berhasil! Kami akan menghubungi Anda.");
        document.getElementById("registerForm").reset();
      } catch (err) {
        alert("Gagal mengirim ke Discord.");
        console.error(err);
      }
    });
  </script>
</body>
</html>
