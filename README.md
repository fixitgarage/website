<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perbaikan Rem - Website Jasa Service Kendaraan</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(120deg, #fbc2eb, #a6c0fe);
            color: #333;
        }
        header {
            text-align: center;
            background-color: #9c27b0;
            color: white;
            padding: 20px 0;
            font-size: 24px;
            font-weight: bold;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        .container {
            padding: 20px;
            text-align: center;
        }
        .service-options {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
            flex-wrap: wrap; /* Tambahkan ini agar responsif */
        }
        .service-item {
            cursor: pointer;
            text-align: center;
            width: 200px;
            background-color: white;
            border: 2px solid #ddd;
            border-radius: 10px;
            padding: 15px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .service-item:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
            border-color: #9c27b0;
        }
        .service-item img {
            width: 100%;
            border-radius: 10px;
            height: auto;
            object-fit: cover;
        }
        #formContainer {
            display: none;
            margin-top: 30px;
        }
        form {
            background-color: white;
            padding: 25px;
            border: 2px solid #ddd;
            border-radius: 10px;
            width: 90%;
            max-width: 450px;
            margin: 0 auto;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
            text-align: left; /* Agar label dan input tidak center */
        }
        form h2 {
            color: #9c27b0;
            font-size: 22px;
            margin-bottom: 20px;
            text-align: center; /* Judul form tetap center */
        }
        form label {
            font-weight: bold;
            margin-bottom: 5px;
            display: block;
            color: #555;
        }
        form input, form select, form button {
            width: 100%;
            padding: 15px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 6px;
            box-sizing: border-box;
            font-size: 14px;
        }
        form input:focus, form select:focus {
            border-color: #9c27b0;
            box-shadow: 0 0 8px rgba(156, 39, 176, 0.5);
            outline: none;
        }
        form button {
            background-color: #9c27b0;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        form button:hover {
            background-color: #8e24aa;
            transform: scale(1.05);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
        }
        .note {
            font-size: 12px;
            color: #888;
            margin-top: 10px;
            text-align: center; /* Note tetap center */
        }
        a.back-link {
            display: block;
            margin-top: 20px;
            color: #9c27b0;
            text-decoration: none;
            text-align: center;
        }
        a.back-link:hover {
            text-decoration: underline;
        }
        .icon {
            font-size: 50px;
            color: #9c27b0;
            margin-bottom: 10px;
        }
    </style>
    <script>
        function pilihRemOption(option) {
            document.getElementById('formContainer').style.display = 'block';
            // PENTING: Gunakan 'selectedLayanan' untuk nama input yang akan dikirim
            document.getElementById('selectedLayanan').value = option;
            // remOption input hidden ini tidak perlu
            // document.getElementById('remOption').value = option;
        }
    </script>
</head>
<body>
    <header>
        <h1>Perbaikan Rem</h1>
    </header>
    <div class="container">
        <p>Pilih jenis perbaikan rem yang sesuai dengan kebutuhan kendaraan Anda.</p>

        <h2><i class="icon">🛠️</i> Pilih Layanan Perbaikan Rem:</h2>
        <div class="service-options">
            <div class="service-item" onclick="pilihRemOption('Perbaikan Rem Ringan')">
                <img src="https://www.shinearmor.com/cdn/shop/articles/A_brake_cleaner_solvent_1200x1200.png?v=1695655684" alt="Perbaikan Rem Ringan">
                <h3>Perbaikan Rem Ringan</h3>
            </div>
            <div class="service-item" onclick="pilihRemOption('Perbaikan Rem Sedang')">
                <img src="https://img.freepik.com/premium-photo/car-brake-repair-installation-new-brake-disc_254309-2019.jpg" alt="Perbaikan Rem Sedang">
                <h3>Perbaikan Rem Sedang</h3>
            </div>
            <div class="service-item" onclick="pilihRemOption('Perbaikan Rem Berat')">
                <img src="https://th.bing.com/th/id/OIP.IbDe9FwQXolMVJv4BMpT3gHaEK?rs=1&pid=ImgDetMain" alt="Perbaikan Rem Berat">
                <h3>Perbaikan Rem Berat</h3>
            </div>
        </div>

        <div id="formContainer">
            <form action="Struk Pembayaran.php" method="post">
                <h2><i class="icon">📄</i> Form Pengisian dan Pembayaran</h2>
                <label for="selectedLayanan">Layanan Terpilih:</label>
                <input type="text" id="selectedLayanan" name="selectedLayanan" readonly>
                <label for="nama">Nama:</label>
                <input type="text" id="nama" name="nama" placeholder="Masukkan nama Anda" required>

                <label for="alamat">Alamat:</label>
                <input type="text" id="alamat" name="alamat" placeholder="Masukkan alamat Anda" required>

                <label for="telephone">Nomor Telepon:</label>
                <input type="tel" id="telephone" name="telephone" placeholder="Masukkan nomor telepon Anda" required>

                <label for="email">Alamat Email:</label>
                <input type="email" id="email" name="email" placeholder="Masukkan email Anda" required>

                <label for="metodePembayaran">Metode Pembayaran:</label>
                <select id="metodePembayaran" name="metodePembayaran" required>
                    <option value="" disabled selected>Pilih metode pembayaran</option>
                    <option value="Kartu Kredit">Kartu Kredit</option>
                    <option value="Debit">Debit</option>
                    <option value="QRIS">QRIS</option>
                    <option value="Cash">Cash</option>
                </select>

                <button type="submit"><i class="icon">💳</i> Bayar</button>
                <div class="note">Pastikan semua data sudah benar sebelum mengirim.</div>
            </form>
        </div>
        <a href="index.php" class="back-
