# mocka67.github.io

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Reading & Poster Assignment</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        poppins: ['Poppins', 'sans-serif'],
                    },
                    colors: {
                        glass: 'rgba(255, 255, 255, 0.75)',
                        glassDark: 'rgba(255, 255, 255, 0.9)',
                    }
                }
            }
        }
    </script>
    <style>
        /* Animasi Background Gradien */
        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .bg-animated {
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradientMove 15s ease infinite;
        }

        /* Gaya Glassmorphism */
        .glass-card {
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
        }

        /* Animasi Masuk (Fade in Up) */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
            animation: fadeInUp 0.8s ease-out forwards;
            opacity: 0;
        }
        .delay-100 { animation-delay: 0.1s; }
        .delay-200 { animation-delay: 0.2s; }
        .delay-300 { animation-delay: 0.3s; }
        .delay-400 { animation-delay: 0.4s; }

        /* Gaya Flashcard (Word Bank) */
        .flip-card {
            background-color: transparent;
            height: 120px;
            perspective: 1000px;
            cursor: pointer;
        }
        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.6s cubic-bezier(0.4, 0.2, 0.2, 1);
            transform-style: preserve-3d;
        }
        .flip-card.flipped .flip-card-inner {
            transform: rotateY(180deg);
        }
        .flip-card-front, .flip-card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }
        .flip-card-front {
            background: linear-gradient(135deg, #ffffff 0%, #f3f4f6 100%);
            color: #1e293b;
            border: 1px solid #e2e8f0;
        }
        .flip-card-back {
            background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
            color: white;
            transform: rotateY(180deg);
            font-size: 0.9rem;
        }

        /* Animasi Tombol Pulsing & Glowing */
        @keyframes pulseGlow {
            0% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.7); }
            70% { box-shadow: 0 0 0 15px rgba(16, 185, 129, 0); }
            100% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0); }
        }
        .btn-glow {
            animation: pulseGlow 2s infinite;
            transition: all 0.3s ease;
        }
        .btn-glow:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 10px 20px rgba(16, 185, 129, 0.4);
            animation: none;
        }
        
        /* Tipografi Teks Bacaan */
        .reading-content p {
            margin-bottom: 1.25rem;
            line-height: 1.8;
            color: #334155;
            font-size: 1.05rem;
        }
        .reading-content p:first-of-type::first-letter {
            font-size: 3rem;
            font-weight: bold;
            color: #2563eb;
            float: left;
            margin-right: 0.5rem;
            line-height: 1;
        }
    </style>
</head>

<body class="bg-animated font-poppins min-h-screen text-slate-800 p-4 md:p-8">

    <div class="max-w-4xl mx-auto space-y-6 md:space-y-8">
        
        <header class="glass-card rounded-2xl p-8 text-center animate-fade-in">
            <div class="inline-block bg-blue-100 text-blue-600 px-4 py-1 rounded-full text-sm font-semibold tracking-wide mb-4 shadow-sm">
                <i class="fas fa-book-open mr-2"></i>Tugas Literasi Digital
            </div>
            <h1 class="text-3xl md:text-5xl font-bold text-slate-800 mb-4 tracking-tight">
                Misi Membaca & <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-purple-600">Kreasi Poster</span>
            </h1>
            <p class="text-slate-600 text-lg md:text-xl max-w-2xl mx-auto">
                Eksplorasi wawasanmu melalui teks di bawah ini, perluas kosakatamu, dan tuangkan imajinasimu ke dalam desain visual.
            </p>
        </header>

        <main class="glass-card rounded-2xl p-6 md:p-10 animate-fade-in delay-100">
            <div class="flex items-center justify-between mb-6 border-b border-gray-200/50 pb-4">
                <h2 class="text-2xl font-bold flex items-center gap-3">
                    <i class="fas fa-align-left text-blue-500"></i> Bacaan Utama
                </h2>
                <span class="text-sm bg-white px-3 py-1 rounded-full text-slate-500 shadow-sm border border-slate-100">
                    <i class="far fa-clock mr-1"></i> Estimasi: 5 Menit
                </span>
            </div>
            
            <article class="reading-content bg-white/50 p-6 md:p-8 rounded-xl shadow-inner border border-white">
                <h3 class="text-2xl font-bold mb-4 text-slate-800">[Masukkan Judul Teks Anda Di Sini]</h3>
                
                <!-- Placeholder Teks -->
                <p>
                    Di sinilah Anda dapat menempelkan (paste) teks bacaan utama Anda. Antarmuka ini dirancang untuk memberikan kenyamanan membaca maksimal bagi siswa. Dengan menggunakan tipografi yang rapi dan jarak antar baris yang lega, mata tidak akan mudah lelah saat membaca melalui layar ponsel maupun komputer.
                </p>
                <p>
                    Anda bisa menambahkan beberapa paragraf di sini. Cerita fiksi, artikel ilmiah populer, atau teks sejarah bisa menjadi bahan yang menarik untuk dianalisis dan divisualisasikan kembali oleh siswa. Semakin menarik teksnya, semakin kreatif pula poster yang akan mereka hasilkan nantinya.
                </p>
                <p>
                    Jangan lupa untuk mencari kata-kata sulit dari teks yang Anda masukkan, dan tambahkan kata-kata tersebut ke dalam fitur "Word Bank" di bawah agar siswa bisa belajar kosakata baru secara interaktif!
                </p>
            </article>
        </main>

        <section class="glass-card rounded-2xl p-6 md:p-10 animate-fade-in delay-200">
            <div class="mb-6 text-center">
                <h2 class="text-2xl font-bold inline-flex items-center gap-3">
                    <i class="fas fa-brain text-purple-500"></i> Bank Kata Interaktif (Word Bank)
                </h2>
                <p class="text-slate-600 mt-2">Klik pada kartu untuk melihat definisi dari kosakata penting berikut!</p>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                <!-- Kartu 1 -->
                <div class="flip-card" onclick="this.classList.toggle('flipped')">
                    <div class="flip-card-inner">
                        <div class="flip-card-front text-lg font-semibold text-slate-700">
                            Eksplorasi
                        </div>
                        <div class="flip-card-back px-3">
                            Penjelajahan lapangan dengan tujuan memperoleh pengetahuan lebih banyak.
                        </div>
                    </div>
                </div>
                
                <!-- Kartu 2 -->
                <div class="flip-card" onclick="this.classList.toggle('flipped')">
                    <div class="flip-card-inner">
                        <div class="flip-card-front text-lg font-semibold text-slate-700">
                            Visualisasi
                        </div>
                        <div class="flip-card-back px-3">
                            Pengungkapan suatu gagasan atau perasaan dengan menggunakan bentuk gambar, tulisan, dll.
                        </div>
                    </div>
                </div>

                <!-- Kartu 3 -->
                <div class="flip-card" onclick="this.classList.toggle('flipped')">
                    <div class="flip-card-inner">
                        <div class="flip-card-front text-lg font-semibold text-slate-700">
                            Estetika
                        </div>
                        <div class="flip-card-back px-3">
                            Cabang filsafat yang menelaah dan membahas tentang seni dan keindahan.
                        </div>
                    </div>
                </div>

                <!-- Kartu 4 -->
                <div class="flip-card" onclick="this.classList.toggle('flipped')">
                    <div class="flip-card-inner">
                        <div class="flip-card-front text-lg font-semibold text-slate-700">
                            Komprehensif
                        </div>
                        <div class="flip-card-back px-3">
                            Bersifat mampu menangkap atau menerima dengan baik; luas dan lengkap.
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="glass-card rounded-2xl p-6 md:p-10 animate-fade-in delay-300 relative overflow-hidden">
            <!-- Aksen Dekoratif -->
            <div class="absolute -right-16 -top-16 w-32 h-32 bg-emerald-400 rounded-full mix-blend-multiply filter blur-2xl opacity-50"></div>
            
            <div class="md:flex gap-8 items-center relative z-10">
                <div class="flex-1 mb-6 md:mb-0">
                    <h2 class="text-2xl font-bold flex items-center gap-3 mb-4">
                        <i class="fas fa-palette text-emerald-500"></i> Tantangan Desain Poster
                    </h2>
                    <ul class="space-y-3 text-slate-700">
                        <li class="flex items-start gap-3">
                            <i class="fas fa-check-circle text-emerald-500 mt-1"></i>
                            <span>Buatlah poster menarik yang merangkum pesan atau ide pokok dari teks bacaan di atas.</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <i class="fas fa-check-circle text-emerald-500 mt-1"></i>
                            <span>Gunakan aplikasi desain seperti <strong>Canva, Photoshop,</strong> atau buat secara manual dan foto dengan jelas.</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <i class="fas fa-check-circle text-emerald-500 mt-1"></i>
                            <span>Simpan dalam format <strong>PDF, JPG, atau PNG</strong>.</span>
                        </li>
                    </ul>
                </div>
                
                <div class="flex-1 text-center bg-white/40 p-6 rounded-xl border border-white shadow-sm">
                    <h3 class="font-semibold text-lg mb-2 text-slate-800">Sudah Selesai?</h3>
                    <p class="text-sm text-slate-600 mb-5">Unggah karya terbaikmu ke folder Google Drive kelas melalui tombol di bawah ini.</p>
                    
                    <!-- TOMBOL GOOGLE DRIVE / GOOGLE FORM -->
                    <!-- Ganti '#' dengan Link Google Form Anda -->
                    <a href="#" target="_blank" class="btn-glow inline-flex items-center justify-center gap-2 w-full bg-gradient-to-r from-emerald-500 to-teal-500 text-white font-bold py-4 px-6 rounded-xl text-lg shadow-lg">
                        <i class="fab fa-google-drive text-xl"></i>
                        Kumpulkan ke Drive
                    </a>
                </div>
            </div>
        </section>

        <footer class="text-center text-white/80 text-sm py-4 animate-fade-in delay-400">
            <p>&copy; 2026 Interactive Learning Assignment.</p>
        </footer>

    </div>

</body>
</html>
