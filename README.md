<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Komunitas ECOBISA - Tema Lingkungan</title>
    <style>
        /* Reset & Global */
        * {
            box-sizing: border-box;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom, #f9f8f2, #d9e6d9);
            color: #2e7d32;
            overflow-x: hidden;
            animation: fadeIn 1.8s ease forwards;
            line-height: 1.5;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Header */
        header {
            background: linear-gradient(45deg, #4caf50, #66bb6a);
            padding: 40px 20px 60px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        /* Animated floating circles in header */
        .circle {
            position: absolute;
            border-radius: 50%;
            background-color: rgba(76, 175, 80, 0.25);
            animation-name: floatUp;
            animation-iteration-count: infinite;
            animation-timing-function: ease-in-out;
        }
        @keyframes floatUp {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        .circle1 { width: 40px; height: 40px; top: 20px; left: 15%; animation-duration: 4s; }
        .circle2 { width: 25px; height: 25px; top: 50px; left: 75%; animation-duration: 5.5s; }
        .circle3 { width: 30px; height: 30px; top: 80px; left: 45%; animation-duration: 6.5s; }

        /* Logo */
        .logo {
            width: 170px;
            height: 170px;
            border-radius: 50%;
            background: white;
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
            padding: 15px;
            margin: 0 auto 15px;
            display: block;
            object-fit: contain;
            border: 3px solid #2e7d32;
        }
        h1 {
            font-weight: 700;
            font-size: 2.8rem;
            margin: 10px 0 8px;
        }
        .subtitle {
            font-size: 1.2rem;
            font-style: italic;
            margin: 0 0 30px;
        }
        nav {
            margin-top: 15px;
        }
        nav a {
            display: inline-block;
            margin: 0 18px;
            font-weight: 600;
            font-size: 1.1rem;
            color: white;
            text-decoration: none;
            position: relative;
            transition: color 0.35s;
        }
        nav a:hover {
            color: #c8e6c9;
        }

        /* Main content */
        main {
            max-width: 900px;
            margin: 40px auto 100px;
            padding: 0 20px;
        }
        section {
            margin-bottom: 50px;
            animation: fadeUp 1.4s ease forwards;
            opacity: 0;
        }
        @keyframes fadeUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
            from {
                opacity: 0;
                transform: translateY(10px);
            }
        }
        section h2 {
            border-left: 6px solid #4caf50;
            padding-left: 12px;
            color: #2e7d32;
            margin-bottom: 22px;
            font-size: 2rem;
        }
        p, ul {
            font-size: 1.1rem;
            color: #2e7d32;
        }
        ul {
            padding-left: 20px;
        }
        ul li {
            margin-bottom: 10px;
        }

        /* Struktur Organisasi Bagan */
        .org-chart {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .level {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        .box {
            position: relative;
            background-color: #4caf50;
            color: white;
            padding: 14px 22px;
            border-radius: 12px;
            font-weight: 600;
            box-shadow: 0 5px 12px rgba(46,125,50,0.3);
            min-width: 180px;
            text-align: center;
        }
        /* Connector lines from boxes */
        .box::after {
            content: '';
            position: absolute;
            top: 100%;
            left: 50%;
            width: 2px;
            height: 25px;
            background: #4caf50;
            transform: translateX(-50%);
        }
        .level:last-child .box::after {
            display: none;
        }
        /* Sub-level div */
        .sub-level {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
        }
        .sub-box {
            background-color: #66bb6a;
            padding: 11px 18px;
            min-width: 160px;
            border-radius: 10px;
            font-weight: 600;
            box-shadow: 0 3px 8px rgba(102,187,106,0.5);
            color: white;
            text-align: center;
        }

        /* Gallery */
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 22px;
        }
        .gallery img {
            width: 230px;
            height: 160px;
            border-radius: 15px;
            object-fit: cover;
            box-shadow: 0 6px 14px rgba(0,0,0,0.12);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }
        .gallery img:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 28px rgba(0,0,0,0.22);
        }

        /* Footer */
        footer {
            background-color: #2e7d32;
            color: #e1f5e1;
            text-align: center;
            padding: 15px 12px;
            position: fixed;
            width: 100%;
            bottom: 0;
            font-size: 0.95rem;
            user-select: none;
        }

        /* Leaf falling animation */
        .leaf {
            position: fixed;
            top: -50px;
            width: 25px;
            height: 25px;
            background: url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjUiIGhlaWdodD0iMjUiIHZpZXdCb3g9IjAgMCAyNSAyNSIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyLjUgMEMxNy40ODkgMCAyMiAxLjEzMyAyMiA1LjgxNUMyMiAxMC40OTEgMTYuMDM2IDEzLjQzNiAxMS44OTYgMTcuNjI4IEM3LjczOCAxMS40MzYgMy41IDIuMzc1IDYuMTM2IDAuMTg3MiBDMy40OTIgMi4xMSAzLjQ5MiA1LjMxNSA1LjU2MiA2LjM5MiIgZmlsbD0iIzJFN0QzMiIgLz4KPC9zdmc+') no-repeat center / contain;
            animation-name: fall;
            animation-timing-function: linear;
            animation-iteration-count: infinite;
        }
        @keyframes fall {
            0% {
                transform: translateY(-60px) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(110vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Responsive */
        @media (max-width: 650px) {
            h1 {
                font-size: 2rem;
            }
            section h2 {
                font-size: 1.6rem;
            }
            .box, .sub-box {
                min-width: 140px;
                font-size: 14px;
                padding: 10px 14px;
            }
            .gallery img {
                width: 140px;
                height: 100px;
            }
            nav a {
                display: inline-block;
                margin: 6px 10px;
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>

    <!-- Animated floating circles in header -->
    <div class="circle circle1"></div>
    <div class="circle circle2"></div>
    <div class="circle circle3"></div>

    <header>
        <img src="https://i.ibb.co/zRy3FrL/logoe.png" alt="Logo ECOBISA" class="logo" />
        <h1>ECOBISA (Belajar Inovatif, Sayangi Alam)</h1>
        <p class="subtitle">Komunitas Lingkungan untuk Edukasi, Kreativitas, dan Aksi Nyata</p>

        <nav>
            <a href="#about">Tentang Kami</a>
            <a href="#vision">Visi & Misi</a>
            <a href="#structure">Struktur Organisasi</a>
            <a href="#programs">Program Kerja</a>
            <a href="#contact">Kontak</a>
        </nav>
    </header>

    <main>
        <section id="about">
            <h2>Tentang Kami</h2>
            <p>ECOBISA adalah komunitas lingkungan yang berfokus pada edukasi, kreativitas, dan aksi nyata untuk menjaga kelestarian bumi. Komunitas ini aktif mengembangkan kegiatan pembelajaran berbasis lingkungan. Mulai dari ecoprinting, dan edukasi pemilahan sampah bagi kaum ibu rumah tangga.</p>
            <p>Sebagai ruang kolaborasi, ECOBISA mengajak masyarakat, pelajar, hingga relawan untuk bareng-bareng menciptakan perubahan positif melalui gerakan kreatif dan berkelanjutan. Komunitas ini menjadi contoh bagaimana warga negara dapat mengambil peran aktif dalam menjaga lingkungan sebagai bagian dari tanggung jawab sosialnya.</p>
        </section>

        <section id="vision">
            <h2>Visi & Misi</h2>
            <h3>Visi</h3>
            <ul>
                <li>Mewujudkan komunitas pembelajar yang inovatif, peduli lingkungan, dan mampu berkontribusi langsung dalam menciptakan masa depan yang berkelanjutan.</li>
            </ul>
            <h3>Misi</h3>
            <ul>
                <li>Mengembangkan program edukasi lingkungan yang kreatif, inovatif, dan kolaboratif.</li>
                <li>Mengajak masyarakat memahami pentingnya pemilahan sampah dan gaya hidup ramah lingkungan.</li>
                <li>Memberdayakan masyarakat, khususnya ibu rumah tangga, lewat pelatihan ecoprinting dan keterampilan ramah lingkungan lainnya.</li>
            </ul>
        </section>

        <section id="structure">
            <h2>Struktur 🌱ECOBISA🌿</h2>
            <div class="org-chart" aria-label="Struktur Organisasi ECOBISA">
                <div class="level" role="group">
                    <div class="box" role="figure" aria-label="Ketua Nisa">Ketua: Nisa</div>
                </div>
                <div class="level" role="group">
                    <div class="box" role="figure" aria-label="Wakil Ketua Kirana">Wakil Ketua: Kirana</div>
                    <div class="box" role="figure" aria-label="Sekretaris Bendahara Anindya">Sekretaris Bendahara: Anindya</div>
                </div>
                <div class="sub-level" role="group">
                    <div class="sub-box" role="figure" aria-label="Divisi Acara Sheyla, Salsa, Hafizah">Divisi Acara: Sheyla, Salsa, Hafizah</div>
                    <div class="sub-box" role="figure" aria-label="Divisi Humas & Kemitraan Ghefira, Navisa, Bernedetta">Divisi Humas & Kemitraan: Ghefira, Navisa, Bernedetta</div>
                    <div class="sub-box" role="figure" aria-label="Divisi Kreatif & Media Syifa, Zulfa">Divisi Kreatif & Media: Syifa, Zulfa</div>
                    <div class="sub-box" role="figure" aria-label="Divisi Logistik Ary, Adisty">Divisi Logistik: Ary, Adisty</div>
                </div>
            </div>
        </section>

        <section id="programs">
            <h2>Program Kerja Kami</h2>
            <ul>
                <li><strong>Ecoprinting:</strong> Pelatihan dan produksi barang ramah lingkungan seperti totebag dengan teknik printing berkelanjutan.</li>
                <li><strong>Edukasi Pemilahan Sampah:</strong> Workshop untuk masyarakat dan ibu rumah tangga tentang memilah sampah organik dan non-organik.</li>
            </ul>
        </section>

        <section id="contact">
            <h2>Kontak Kami</h2>
            <p>Email: <a href="mailto:ecobisa34@gmail.com">ecobisa34@gmail.com</a> | Telepon: <a href="tel:+6287821073655">087821073655</a></p>
            <p>Alamat: Bojongsoang, Bandung 2025</p>
            <p>Instagram: <a href="https://instagram.com/ecobisa.id" target="_blank" rel="noopener">@ecobisa.id</a></p>
        </section>
    </main>

    <footer>
        &copy; 2025 ECOBISA. Semua hak dilindungi. 🌍 #BelajarInovatifSayangiAlam
    </footer>

    <!-- Floating leaves animation -->
    <script>
        const leafSVG = `data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjUiIGhlaWdodD0iMjUiIHZpZXdCb3g9IjAgMCAyNSAyNSIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyLjUgMEMxNy40ODkgMCAyMiAxLjEzMyAyMiA1LjgxNUMyMiAxMC40OTEgMTYuMDM2IDEzLjQzNiAxMS44OTYgMTcuNjI4IEM3LjczOCAxMS40MzYgMy41IDIuMzc1IDYuMTM2IDAuMTg3MiBDMy40OTIgMi4xMSAzLjQ5MiA1LjMxNSA1LjU2MiA2LjM5MiIgZmlsbD0iIzJFN0QzMiIgLz4KPC9zdmc+`;
        function createLeaf() {
            const leaf = document.createElement('div');
            leaf.className = 'leaf';
            leaf.style.left = (Math.random() * 100) + 'vw';
            leaf.style.animationDuration = (Math.random() * 5 + 7) + 's';
            leaf.style.backgroundImage = `url(${leafSVG})`;
            leaf.style.top = '-40px';
            document.body.appendChild(leaf);
            setTimeout(() => leaf.remove(), 12000);
        }
        setInterval(createLeaf, 2000);
        // Create initial leaves
        for (let i = 0; i < 8; i++) createLeaf();
    </script>

</body>
</html>
