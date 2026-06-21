
```html
<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Undangan Tasyakuran Sunatan - Deva Nur Fajrian Almusfi</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Cinzel+Decorative:wght@700&family=Cinzel:wght@600;700;900&family=Great+Vibes&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <!-- Tailwind Custom Configuration -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            brand: {
              navy: '#1E3A5F',      /* Navy biru dongker mewah */
              gold: '#D4AF37',      /* Emas berkilau */
              goldlight: '#F4E8C1', /* Emas lembut */
              accent: '#2B547E',    /* Biru penengah */
              cream: '#FCF9F2',     /* Latar krem lembut */
              darkcream: '#F4EFE0'  /* Krem hangat */
            }
          },
          fontFamily: {
            serif: ['Cinzel', 'Georgia', 'serif'],
            cursive: ['Great Vibes', 'cursive'],
            sans: ['Plus Jakarta Sans', 'sans-serif'],
            arabic: ['Amiri', 'serif'],
            cinzeldec: ['Cinzel Decorative', 'serif']
          }
        }
      }
    }
  </script>

  <style>
    /* Pola Latar Belakang Klasik */
    .bg-pattern {
      background-image: radial-gradient(circle at 1px 1px, #e8dfc7 1px, transparent 0);
      background-size: 24px 24px;
    }
    
    /* Bingkai Lengkung Kubah */
    .dome-frame {
      border-radius: 50% 50% 0 0 / 25% 25% 0 0;
    }

    /* Animasi Mengambang Lembut */
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    .animate-float {
      animation: float 4s ease-in-out infinite;
    }

    /* Efek Muncul Perlahan saat Gulir Layar */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.8s ease;
    }
    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body class="bg-brand-cream text-slate-800 font-sans overflow-x-hidden">

  <!-- ==================== AUDIO LATAR BELAKANG ISLAMI ==================== -->
  <audio id="bg-music" loop>
    <!-- Musik instrumen Timur Tengah/Nasyid rebana syahdu -->
    <source src="https://assets.mixkit.co/music/preview/mixkit-spirit-of-the-east-1376.mp3" type="audio/mpeg">
  </audio>

  <!-- TOMBOL KONTROL AUDIO MELAYANG -->
  <button id="music-btn" class="fixed bottom-6 right-6 z-50 bg-brand-navy text-brand-gold p-3 rounded-full shadow-2xl border border-brand-gold/30 flex items-center justify-center hidden transition-all hover:scale-110 active:scale-95">
    <i data-lucide="music-4" class="w-6 h-6 animate-spin" style="animation-duration: 8s;"></i>
  </button>

  <!-- ==================== AMPLOP PEMBUKA INTERAKTIF ==================== -->
  <div id="envelope-screen" class="fixed inset-0 z-50 flex flex-col items-center justify-center bg-brand-cream overflow-hidden">
    <!-- Bingkai Ornamen Emas Sudut -->
    <div class="absolute top-4 left-4 w-16 h-16 border-t-2 border-l-2 border-brand-gold rounded-tl-xl opacity-60"></div>
    <div class="absolute top-4 right-4 w-16 h-16 border-t-2 border-r-2 border-brand-gold rounded-tr-xl opacity-60"></div>
    <div class="absolute bottom-4 left-4 w-16 h-16 border-b-2 border-l-2 border-brand-gold rounded-bl-xl opacity-60"></div>
    <div class="absolute bottom-4 right-4 w-16 h-16 border-b-2 border-r-2 border-brand-gold rounded-br-xl opacity-60"></div>

    <div class="text-center px-4 max-w-lg z-10">
      <!-- Kaligrafi Basmalah -->
      <p class="font-arabic text-brand-navy text-2xl mb-2 opacity-80">بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ</p>
      
      <p class="text-brand-accent tracking-widest text-xs uppercase font-semibold mb-4">Undangan Tasyakuran Sunatan</p>
      
      <!-- Pembatas Ornamen -->
      <div class="flex items-center justify-center gap-2 mb-6">
        <div class="h-[1px] w-12 bg-brand-gold"></div>
        <i data-lucide="star" class="w-4 h-4 fill-brand-gold text-brand-gold"></i>
        <div class="h-[1px] w-12 bg-brand-gold"></div>
      </div>

      <h1 class="font-serif text-3xl md:text-4xl font-bold text-brand-navy mb-2">Deva Nur Fajrian Almusfi</h1>
      <p class="text-slate-500 italic text-sm mb-12">Kepada Bapak/Ibu/Saudara/i yang terhormat:</p>

      <!-- Kartu Penerima Undangan -->
      <div class="bg-white p-6 md:p-8 rounded-2xl shadow-xl border border-brand-goldlight max-w-sm mx-auto mb-8 relative">
        <div class="absolute -top-3 left-1/2 -translate-x-1/2 bg-brand-gold text-white text-[10px] uppercase tracking-widest px-4 py-1 rounded-full font-bold">
          Tamu Istimewa
        </div>
        <h3 id="guest-name" class="font-serif text-xl font-bold text-brand-navy min-h-[1.5rem] break-words">Nama Tamu Undangan</h3>
        <p class="text-xs text-slate-400 mt-2">di tempat</p>
      </div>

      <button id="open-btn" class="bg-brand-navy hover:bg-brand-accent text-white font-semibold px-8 py-3.5 rounded-full border border-brand-gold shadow-lg flex items-center gap-2 mx-auto transition-all transform hover:scale-105 active:scale-95">
        <i data-lucide="mail-open" class="w-5 h-5 text-brand-gold"></i>
        <span>Buka Undangan</span>
      </button>
    </div>

    <!-- Hiasan Awan Bawah -->
    <div class="absolute bottom-0 w-full opacity-30 flex justify-between pointer-events-none">
      <svg class="w-1/2 h-20 fill-white" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,100 C20,80 40,80 60,100 Z" /></svg>
      <svg class="w-1/2 h-20 fill-white" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M40,100 C60,80 80,80 100,100 Z" /></svg>
    </div>
  </div>


  <!-- ==================== ISI UTAMA WEBSITE (REVEAL) ==================== -->
  <div id="main-content" class="hidden relative opacity-0 transition-opacity duration-1000">

    <!-- Ornamen Bintang Gantung Samar di Latar Belakang -->
    <div class="absolute top-0 inset-x-0 h-96 overflow-hidden pointer-events-none z-0">
      <div class="absolute top-10 left-10 text-brand-gold/40 animate-pulse"><i data-lucide="star" class="w-6 h-6 fill-brand-gold/20"></i></div>
      <div class="absolute top-24 right-12 text-brand-gold/40 animate-pulse" style="animation-delay: 1.5s;"><i data-lucide="star" class="w-8 h-8 fill-brand-gold/20"></i></div>
    </div>

    <!-- ==================== HERO SECTION ==================== -->
    <section class="min-h-screen flex flex-col justify-between items-center px-4 py-12 relative bg-pattern">
      <!-- Bingkai Lengkung Kubah Masjid -->
      <div class="absolute inset-4 border border-brand-gold/30 rounded-3xl pointer-events-none dome-frame flex flex-col items-center pt-8">
        <!-- Lentera Kiri -->
        <div class="absolute -top-4 left-6 md:left-12 flex flex-col items-center">
          <div class="w-[2px] h-20 bg-brand-gold"></div>
          <div class="bg-brand-navy text-brand-gold p-2 rounded-full shadow-lg border border-brand-gold/30 animate-float">
            <svg class="w-5 h-5 fill-brand-gold" viewBox="0 0 24 24"><path d="M12,2A3,3 0 0,0 9,5V6H7A2,2 0 0,0 5,8V15A2,2 0 0,0 7,17H9V19A3,3 0 0,0 12,22A3,3 0 0,0 15,19V17H17A2,2 0 0,0 19,15V8A2,2 0 0,0 17,6H15V5A3,3 0 0,0 12,2M12,4A1,1 0 0,1 13,5V6H11V5A1,1 0 0,1 12,4M12,18A1,1 0 0,1 11,17V15H13V17A1,1 0 0,1 12,18Z"/></svg>
          </div>
        </div>
        <!-- Lentera Kanan -->
        <div class="absolute -top-4 right-6 md:right-12 flex flex-col items-center">
          <div class="w-[2px] h-20 bg-brand-gold"></div>
          <div class="bg-brand-navy text-brand-gold p-2 rounded-full shadow-lg border border-brand-gold/30 animate-float" style="animation-delay: 1s">
            <svg class="w-5 h-5 fill-brand-gold" viewBox="0 0 24 24"><path d="M12,2A3,3 0 0,0 9,5V6H7A2,2 0 0,0 5,8V15A2,2 0 0,0 7,17H9V19A3,3 0 0,0 12,22A3,3 0 0,0 15,19V17H17A2,2 0 0,0 19,15V8A2,2 0 0,0 17,6H15V5A3,3 0 0,0 12,2M12,4A1,1 0 0,1 13,5V6H11V5A1,1 0 0,1 12,4M12,18A1,1 0 0,1 11,17V15H13V17A1,1 0 0,1 12,18Z"/></svg>
          </div>
        </div>
      </div>

      <!-- Basmalah & Salam Pembuka -->
      <div class="text-center z-10 mt-12">
        <p class="font-arabic text-brand-navy text-3xl md:text-4xl tracking-wide mb-3">بِسْمِ اللَّهِ الرَّحْمENِ الرَّحِيمِ</p>
        <p class="text-brand-accent tracking-[0.2em] text-xs uppercase font-bold">ASSALAMUALAIKUM WARAHMATULLAHI WABARAKATUH</p>
      </div>

      <!-- Informasi Utama & Foto Ananda -->
      <div class="text-center max-w-xl px-4 z-10 my-auto flex flex-col items-center">
        <p class="text-slate-600 text-sm md:text-base px-6 mb-6 leading-relaxed">
          Dengan memohon rahmat dan ridho Allah SWT, kami mengundang Bapak/Ibu/Saudara/i untuk berkenan hadir dalam acara tasyakuran khitanan putra kami:
        </p>

        <!-- Judul Sunatan -->
        <span class="text-brand-gold font-bold text-xs uppercase tracking-[0.3em] mb-1">TASYAKURAN</span>
        <h2 class="font-serif text-5xl md:text-6xl font-bold text-brand-navy mb-2 relative">
          Sunatan
          <span class="absolute -right-6 -top-3 text-brand-gold text-lg"><i data-lucide="sparkles" class="w-5 h-5 fill-brand-gold"></i></span>
        </h2>
        
        <!-- Pita Keterangan -->
        <div class="bg-brand-navy text-brand-goldlight text-xs font-semibold px-6 py-2 rounded-md shadow-md border-x-2 border-brand-gold mb-10 tracking-widest uppercase">
          Ananda Tercinta
        </div>

        <!-- BINGKAI FOTO PROFIL ANANDA DEVA (Menggunakan berkas asli 21828.jpg) -->
        <div class="relative w-64 h-64 md:w-72 md:h-72 mb-8">
          <!-- Lingkaran Luar Berputar -->
          <div class="absolute inset-0 rounded-full border-4 border-dashed border-brand-gold/40 animate-spin" style="animation-duration: 25s;"></div>
          <!-- Lingkaran Dalam Emas -->
          <div class="absolute inset-2 rounded-full border-2 border-brand-gold"></div>
          <!-- Wadah Foto Profil Bulat -->
          <div class="absolute inset-4 rounded-full overflow-hidden bg-slate-100 border-4 border-white shadow-2xl flex items-center justify-center">
            <!-- Menampilkan foto tampan ananda dari file yang diunggah -->
            <img 
              id="deva-img"
              src="21828.jpg" 
              alt="Ananda Deva Nur Fajrian Almusfi" 
              class="w-full h-full object-cover object-[center_28%] scale-110"
              onerror="handleImageError(this)"
            >
            <!-- FALLBACK PREMIUM ELEGAN (Menggantikan gambar wanita secara permanen jika gambar lokal tidak termuat) -->
            <div id="deva-fallback" class="hidden absolute inset-0 bg-gradient-to-b from-brand-navy to-brand-accent flex flex-col items-center justify-center text-white p-4 text-center">
              <div class="bg-brand-navy/60 text-brand-gold p-4 rounded-full border border-brand-gold/40 mb-3 animate-pulse">
                <i data-lucide="user" class="w-14 h-14"></i>
              </div>
              <span class="text-xs font-bold tracking-widest text-brand-goldlight uppercase">Deva Nur Fajrian</span>
              <p class="text-[9px] text-slate-300 mt-1 uppercase tracking-wider font-semibold">Tasyakuran Khitan</p>
            </div>
          </div>
        </div>

        <!-- Nama Lengkap Ananda Deva -->
        <div class="relative px-8 py-4 bg-brand-goldlight/20 border border-brand-gold/50 rounded-2xl max-w-md shadow-sm">
          <div class="absolute -top-3 left-6 px-3 bg-brand-cream text-xs font-semibold text-brand-accent tracking-wider uppercase">Putra Tercinta</div>
          <h3 class="font-cursive text-4xl text-brand-navy font-bold leading-tight">Deva Nur Fajrian Almusfi</h3>
        </div>
      </div>

      <!-- Petunjuk Geser -->
      <div class="text-center z-10 pb-4">
        <p class="text-slate-400 text-xs tracking-widest uppercase mb-1">Scroll Kebawah</p>
        <i data-lucide="chevron-down" class="w-5 h-5 text-brand-gold mx-auto animate-bounce"></i>
      </div>
    </section>


    <!-- ==================== DOA & DETAIL ORANG TUA ==================== -->
    <section class="py-20 px-6 bg-brand-darkcream text-center relative overflow-hidden">
      <div class="absolute top-0 left-0 w-32 h-32 opacity-10 pointer-events-none">
        <svg viewBox="0 0 100 100" class="fill-brand-navy"><path d="M0,0 L100,0 L0,100 Z" /></svg>
      </div>

      <div class="max-w-2xl mx-auto reveal">
        <i data-lucide="quote" class="w-10 h-10 text-brand-gold/60 mx-auto mb-6 transform rotate-180"></i>
        
        <p class="text-brand-navy font-arabic text-xl md:text-2xl mb-4 leading-relaxed font-bold">
          "Semoga setelah di khitan, Ananda menjadi anak yang sholeh, berbakti kepada orang tua, berguna bagi agama, nusa dan bangsa. Aamiin."
        </p>
        
        <div class="h-[2px] w-24 bg-brand-gold mx-auto my-6"></div>

        <!-- Kartu Identitas Orang Tua Sesuai Gambar (Tanpa kata Ayah dan Ibu di nama) -->
        <div class="bg-white p-6 md:p-8 rounded-2xl shadow-xl border border-brand-goldlight max-w-md mx-auto relative mt-10">
          <div class="absolute -top-5 left-1/2 -translate-x-1/2 bg-brand-navy text-brand-gold text-xs uppercase tracking-widest px-6 py-2.5 rounded-full font-bold shadow-md flex items-center gap-2">
            <i data-lucide="users" class="w-4 h-4"></i>
            <span>Putra Dari</span>
          </div>

          <div class="mt-4 space-y-4">
            <div>
              <p class="text-xs text-slate-400 uppercase tracking-wider">Ayahanda</p>
              <h4 class="font-serif text-lg font-bold text-brand-navy">Musriadi bin Mahizan</h4>
            </div>
            
            <div class="flex items-center justify-center gap-2 text-brand-gold text-sm font-semibold">
              <div class="h-[1px] w-10 bg-brand-gold/30"></div>
              <span>&</span>
              <div class="h-[1px] w-10 bg-brand-gold/30"></div>
            </div>

            <div>
              <p class="text-xs text-slate-400 uppercase tracking-wider">Ibunda</p>
              <h4 class="font-serif text-lg font-bold text-brand-navy">Siti Rofingah</h4>
            </div>
          </div>
        </div>
      </div>
    </section>


    <!-- ==================== HITUNG MUNDUR (COUNTDOWN) ==================== -->
    <section class="py-16 px-6 bg-brand-navy text-white text-center relative">
      <!-- Pola Halus Latar Belakang -->
      <div class="absolute inset-0 opacity-10 bg-pattern pointer-events-none"></div>

      <div class="max-w-4xl mx-auto relative z-10 reveal">
        <p class="text-brand-gold font-semibold uppercase tracking-widest text-xs mb-2">Menuju Hari Bahagia</p>
        <h3 class="font-serif text-2xl md:text-3xl font-bold mb-8">Hitung Mundur Acara</h3>

        <!-- Kotak Waktu Dinamis -->
        <div class="grid grid-cols-4 gap-3 md:gap-6 max-w-lg mx-auto mb-8">
          <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/10 flex flex-col items-center">
            <span id="days" class="text-2xl md:text-4xl font-bold text-brand-gold">00</span>
            <span class="text-[10px] md:text-xs uppercase tracking-wider text-slate-300 mt-1">Hari</span>
          </div>
          <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/10 flex flex-col items-center">
            <span id="hours" class="text-2xl md:text-4xl font-bold text-brand-gold">00</span>
            <span class="text-[10px] md:text-xs uppercase tracking-wider text-slate-300 mt-1">Jam</span>
          </div>
          <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/10 flex flex-col items-center">
            <span id="minutes" class="text-2xl md:text-4xl font-bold text-brand-gold">00</span>
            <span class="text-[10px] md:text-xs uppercase tracking-wider text-slate-300 mt-1">Menit</span>
          </div>
          <div class="bg-white/10 backdrop-blur-sm p-4 rounded-xl border border-white/15 flex flex-col items-center">
            <span id="seconds" class="text-2xl md:text-4xl font-bold text-brand-gold">00</span>
            <span class="text-[10px] md:text-xs uppercase tracking-wider text-slate-300 mt-1">Detik</span>
          </div>
        </div>

        <p class="text-xs text-brand-goldlight/70 italic">"Ya Allah, muliakanlah kehidupan anak kami dengan kebaikan dan ketakwaan."</p>
      </div>
    </section>


    <!-- ==================== WAKTU & TEMPAT (LOKASI PETA) ==================== -->
    <section class="py-20 px-6 bg-brand-cream relative">
      <div class="max-w-4xl mx-auto">
        <div class="text-center mb-16 reveal">
          <span class="text-brand-gold font-semibold uppercase tracking-widest text-xs">Waktu & Tempat</span>
          <h2 class="font-serif text-3xl md:text-4xl font-bold text-brand-navy mt-2">Detail Acara</h2>
          <div class="h-[1px] w-24 bg-brand-gold mx-auto mt-4"></div>
        </div>

        <!-- Detail Grid Acara -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-12 reveal">
          
          <!-- HARI / TANGGAL -->
          <div class="bg-white p-8 rounded-2xl shadow-lg border border-brand-goldlight flex flex-col items-center text-center group hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2">
            <div class="bg-brand-goldlight/30 text-brand-navy p-4 rounded-full mb-6 group-hover:bg-brand-navy group-hover:text-white transition-all duration-300">
              <i data-lucide="calendar" class="w-8 h-8"></i>
            </div>
            <h4 class="font-serif text-lg font-bold text-brand-navy mb-2">Hari & Tanggal</h4>
            <p class="text-slate-600 font-semibold mb-1">Minggu</p>
            <p class="text-brand-gold font-bold text-xl">5 Juli 2026</p>
          </div>

          <!-- WAKTU -->
          <div class="bg-white p-8 rounded-2xl shadow-lg border border-brand-goldlight flex flex-col items-center text-center group hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2">
            <div class="bg-brand-goldlight/30 text-brand-navy p-4 rounded-full mb-6 group-hover:bg-brand-navy group-hover:text-white transition-all duration-300">
              <i data-lucide="clock" class="w-8 h-8"></i>
            </div>
            <h4 class="font-serif text-lg font-bold text-brand-navy mb-2">Waktu Acara</h4>
            <p class="text-slate-600 font-semibold mb-1">Pukul 09.00 WIB</p>
            <p class="text-brand-gold font-bold text-lg">s.d Selesai</p>
          </div>

          <!-- TEMPAT -->
          <div class="bg-white p-8 rounded-2xl shadow-lg border border-brand-goldlight flex flex-col items-center text-center group hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2">
            <div class="bg-brand-goldlight/30 text-brand-navy p-4 rounded-full mb-6 group-hover:bg-brand-navy group-hover:text-white transition-all duration-300">
              <i data-lucide="map-pin" class="w-8 h-8"></i>
            </div>
            <h4 class="font-serif text-lg font-bold text-brand-navy mb-2">Tempat Lokasi</h4>
            <p class="text-slate-600 text-sm leading-relaxed mb-1">
              Jalan Cempaka Baru II No.51A, RT.1/RW.5, Jaticempaka, Pondok Gede, Kota Bekasi
            </p>
            <p class="text-brand-gold font-bold text-xs">Jawa Barat 17411</p>
          </div>

        </div>

        <!-- Google Maps Frame Integrasi -->
        <div class="bg-white p-4 rounded-2xl shadow-xl border border-brand-goldlight reveal">
          <div class="w-full h-80 rounded-xl overflow-hidden relative shadow-inner">
            <iframe 
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3966.123420803525!2d106.92484667364654!3d-6.247466561171881!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e698ccd7b2a5eb5%3A0xe2da4cf525b6a78c!2sJl.%20Cempaka%20Baru%20II%2C%20Jaticempaka%2C%20Kec.%20Pondokgede%2C%20Kota%20Bks%2C%20Jawa%20Barat%2017411!5e0!3m2!1sid!2sid!4v1700000000000!5m2!1sid!2sid" 
              class="w-full h-full border-0" 
              allowfullscreen="" 
              loading="lazy" 
              referrerpolicy="no-referrer-when-downgrade">
            </iframe>
          </div>
          
          <div class="p-6 text-center">
            <p class="text-sm text-slate-500 mb-4">Temukan rute tercepat dan akurat menuju lokasi tasyakuran menggunakan Google Maps.</p>
            <a 
              href="https://maps.google.com/?q=Jalan+Cempaka+Baru+II+No.51A,+Jaticempaka,+Pondok+Gede" 
              target="_blank" 
              class="inline-flex items-center gap-2 bg-brand-navy hover:bg-brand-accent text-white font-semibold px-6 py-3 rounded-full shadow-lg border border-brand-gold transition-all duration-300"
            >
              <i data-lucide="navigation" class="w-5 h-5 text-brand-gold"></i>
              <span>Buka Petunjuk Navigasi</span>
            </a>
          </div>
        </div>
      </div>
    </section>


    <!-- ==================== KONFIRMASI KEHADIRAN (RSVP) ==================== -->
    <section class="py-20 px-6 bg-brand-darkcream relative">
      <div class="max-w-2xl mx-auto">
        <div class="text-center mb-12 reveal">
          <span class="text-brand-gold font-semibold uppercase tracking-widest text-xs">Reservasi Digital</span>
          <h2 class="font-serif text-3xl md:text-4xl font-bold text-brand-navy mt-2">Konfirmasi Kehadiran</h2>
          <div class="h-[1px] w-24 bg-brand-gold mx-auto mt-4"></div>
          <p class="text-slate-500 text-sm mt-4">Mohon konfirmasikan kehadiran Anda demi kenyamanan bersama.</p>
        </div>

        <form id="rsvp-form" class="bg-white p-8 rounded-2xl shadow-xl border border-brand-goldlight space-y-6 reveal">
          <div>
            <label for="rsvp-name" class="block text-xs font-bold text-brand-navy uppercase tracking-wider mb-2">Nama Lengkap</label>
            <div class="relative">
              <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none text-slate-400">
                <i data-lucide="user" class="w-5 h-5"></i>
              </div>
              <input 
                type="text" 
                id="rsvp-name" 
                required 
                placeholder="Masukkan nama Anda..." 
                class="block w-full pl-10 pr-4 py-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all text-sm"
              >
            </div>
          </div>

          <div>
            <label class="block text-xs font-bold text-brand-navy uppercase tracking-wider mb-2">Konfirmasi Kehadiran</label>
            <div class="grid grid-cols-2 gap-4">
              <label class="flex items-center justify-center gap-2 p-3 border border-slate-200 rounded-xl cursor-pointer hover:bg-brand-goldlight/10 transition-all">
                <input type="radio" name="attendance" value="hadir" required class="text-brand-gold focus:ring-brand-gold">
                <span class="text-sm font-semibold text-slate-700">Ya, Saya Hadir</span>
              </label>
              <label class="flex items-center justify-center gap-2 p-3 border border-slate-200 rounded-xl cursor-pointer hover:bg-brand-goldlight/10 transition-all">
                <input type="radio" name="attendance" value="absen" required class="text-brand-gold focus:ring-brand-gold">
                <span class="text-sm font-semibold text-slate-700">Maaf, Berhalangan</span>
              </label>
            </div>
          </div>

          <div>
            <label for="rsvp-guests" class="block text-xs font-bold text-brand-navy uppercase tracking-wider mb-2">Jumlah Orang</label>
            <div class="relative">
              <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none text-slate-400">
                <i data-lucide="users" class="w-5 h-5"></i>
              </div>
              <select 
                id="rsvp-guests" 
                class="block w-full pl-10 pr-4 py-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all text-sm appearance-none"
              >
                <option value="1">1 Orang</option>
                <option value="2">2 Orang</option>
                <option value="3">3 Orang</option>
                <option value="4">4 Orang</option>
                <option value="5">Lebih dari 4 Orang</option>
              </select>
            </div>
          </div>

          <button 
            type="submit" 
            class="w-full bg-brand-navy hover:bg-brand-accent text-white font-bold py-4 rounded-xl border border-brand-gold shadow-lg flex items-center justify-center gap-2 transition-all"
          >
            <i data-lucide="send" class="w-5 h-5 text-brand-gold"></i>
            <span>Kirim Konfirmasi</span>
          </button>
        </form>

        <!-- Notifikasi RSVP -->
        <div id="rsvp-status-card" class="mt-4 p-4 rounded-xl bg-green-50 text-green-800 border border-green-200 hidden flex items-center gap-2">
          <i data-lucide="check-circle-2" class="w-5 h-5 text-green-600"></i>
          <span class="text-sm font-semibold">Konfirmasi Anda telah berhasil direkam! Terima kasih.</span>
        </div>
      </div>
    </section>


    <!-- ==================== GUESTBOOK (UCAPAN & DOA RESTU) ==================== -->
    <section class="py-20 px-6 bg-brand-cream relative">
      <div class="max-w-2xl mx-auto">
        <div class="text-center mb-12 reveal">
          <span class="text-brand-gold font-semibold uppercase tracking-widest text-xs">Pesan Keikhlasan</span>
          <h2 class="font-serif text-3xl md:text-4xl font-bold text-brand-navy mt-2">Ucapan & Doa Restu</h2>
          <div class="h-[1px] w-24 bg-brand-gold mx-auto mt-4"></div>
          <p class="text-slate-500 text-sm mt-4">Kirimkan bait doa dan ucapan selamat untuk ananda Deva.</p>
        </div>

        <!-- Form Tambah Buku Tamu -->
        <form id="comment-form" class="bg-white p-6 rounded-2xl shadow-xl border border-brand-goldlight space-y-4 mb-10 reveal">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div>
              <input 
                type="text" 
                id="comment-author" 
                required 
                placeholder="Nama Pengirim" 
                class="block w-full px-4 py-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all text-sm"
              >
            </div>
            <div>
              <input 
                type="text" 
                id="comment-relation" 
                placeholder="Hubungan (cth: Kerabat, Tetangga)" 
                class="block w-full px-4 py-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all text-sm"
              >
            </div>
          </div>
          <div>
            <textarea 
              id="comment-text" 
              rows="4" 
              required 
              placeholder="Tulis ucapan selamat & doa restu di sini..." 
              class="block w-full px-4 py-3 border border-slate-200 rounded-xl focus:ring-2 focus:ring-brand-gold focus:border-transparent outline-none transition-all text-sm"
            ></textarea>
          </div>
          <button 
            type="submit" 
            class="bg-brand-navy hover:bg-brand-accent text-white font-semibold px-6 py-3 rounded-xl border border-brand-gold shadow-md flex items-center gap-2 ml-auto transition-all"
          >
            <i data-lucide="message-square" class="w-4 h-4 text-brand-gold"></i>
            <span>Kirim Ucapan</span>
          </button>
        </form>

        <!-- Daftar Doa yang Tertampil -->
        <div class="space-y-4 max-h-[450px] overflow-y-auto pr-2 reveal" id="comments-container">
          <!-- Ucapan Pembuka 1 -->
          <div class="bg-white p-5 rounded-2xl shadow-sm border border-brand-goldlight/30">
            <div class="flex items-center justify-between mb-2">
              <h5 class="font-serif font-bold text-brand-navy text-sm">H. Ahmad subagjo</h5>
              <span class="text-[10px] bg-brand-goldlight/50 text-brand-navy font-semibold px-2 py-0.5 rounded-full">Tetangga</span>
            </div>
            <p class="text-slate-600 text-sm italic leading-relaxed">
              "Selamat atas khitanan ananda Deva Nur Fajrian Almusfi. Semoga kelak tumbuh menjadi anak yang shaleh, taat beragama, berbakti kepada ayah-bunda, serta menjadi penerus generasi muslim yang gemilang."
            </p>
          </div>

          <!-- Ucapan Pembuka 2 -->
          <div class="bg-white p-5 rounded-2xl shadow-sm border border-brand-goldlight/30">
            <div class="flex items-center justify-between mb-2">
              <h5 class="font-serif font-bold text-brand-navy text-sm">Zulkifli & Keluarga</h5>
              <span class="text-[10px] bg-brand-goldlight/50 text-brand-navy font-semibold px-2 py-0.5 rounded-full">Kerabat</span>
            </div>
            <p class="text-slate-600 text-sm italic leading-relaxed">
              "Barakallahu fiikum untuk Musriadi dan Siti Rofingah. Semoga ananda lekas sembuh, senantiasa dilindungi Allah SWT, dan dimudahkan segala ikhtiarnya dalam mendidik Deva."
            </p>
          </div>
        </div>
      </div>
    </section>


    <!-- ==================== HORMAT KAMI & SALAM PENUTUP ==================== -->
    <section class="py-16 px-6 bg-brand-darkcream text-center relative">
      <div class="max-w-4xl mx-auto reveal">
        <h3 class="font-serif text-2xl font-bold text-brand-navy mb-12">Hormat Kami</h3>
        
        <div class="flex flex-col items-center gap-4">
          <!-- Ikon Kubah Masjid -->
          <div class="text-brand-gold mb-4 animate-float">
            <svg class="w-16 h-16 fill-brand-gold" viewBox="0 0 24 24">
              <path d="M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M12,4A2,2 0 0,1 14,6C14,7.1 13.1,8 12,8A2,2 0 0,1 10,6C10,4.9 10.9,4 12,4M12,18A6,6 0 0,1 6,12C6,10.1 7.2,8.5 9,7.8C9.5,8.9 10.7,9.6 12,9.6C13.3,9.6 14.5,8.9 15,7.8C16.8,8.5 18,10.1 18,12A6,6 0 0,1 12,18Z"/>
            </svg>
          </div>

          <p class="text-slate-600 text-sm max-w-xl leading-relaxed">
            "Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir dan memberikan doa restu kepada Ananda."
          </p>

          <div class="my-6">
            <p class="text-xs uppercase tracking-widest text-slate-400 mb-2">Wassalamualaikum Warahmatullahi Wabarakatuh</p>
            <div class="h-[1px] w-48 bg-brand-gold mx-auto"></div>
          </div>

          <!-- Keterangan Keluarga Pengundang -->
          <p class="text-xs text-slate-500 uppercase tracking-widest">Keluarga Besar</p>
          <h4 class="font-serif text-xl font-bold text-brand-navy">Musriadi & Siti Rofingah</h4>
        </div>
      </div>
    </section>


    <!-- ==================== KAKI HALAMAN (FOOTER) ==================== -->
    <footer class="py-8 bg-brand-navy text-white text-center text-xs relative">
      <div class="absolute inset-0 opacity-5 bg-pattern pointer-events-none"></div>
      <div class="relative z-10 space-y-2">
        <p class="text-brand-goldlight font-semibold">Deva Nur Fajrian Almusfi &copy; 2026</p>
        <p class="text-slate-400">Dibuat dengan segenap cinta & keikhlasan</p>
      </div>
    </footer>

  </div>

  <!-- ==================== LOGIKA OPERASIONAL JAVASCRIPT ==================== -->
  <script>
    // Ambil semua ikon Lucide
    lucide.createIcons();

    // Fungsi penanganan error pemuatan gambar lokal
    function handleImageError(imgElement) {
      imgElement.style.display = 'none';
      document.getElementById('deva-fallback').classList.remove('hidden');
    }

    // Membaca Parameter Query URL kustomisasi nama tamu (Contoh: link.com/?to=Bapak+Joko)
    function getQueryParam(name) {
      const urlParams = new URLSearchParams(window.location.search);
      return urlParams.get(name);
    }

    const guestNameParam = getQueryParam('to');
    if (guestNameParam) {
      document.getElementById('guest-name').innerText = decodeURIComponent(guestNameParam);
    }

    // Navigasi Pembukaan Amplop & Pemutaran Musik Otomatis
    const envelopeScreen = document.getElementById('envelope-screen');
    const mainContent = document.getElementById('main-content');
    const openBtn = document.getElementById('open-btn');
    const bgMusic = document.getElementById('bg-music');
    const musicBtn = document.getElementById('music-btn');

    openBtn.addEventListener('click', () => {
      // 1. Putar Musik
      bgMusic.play().then(() => {
        musicBtn.classList.remove('hidden');
      }).catch(err => {
        console.log("Autoplay musik terhambat browser, menampilkan kontrol tombol manual.");
        musicBtn.classList.remove('hidden');
      });

      // 2. Transisi Geser Amplop Keluar Layar
      envelopeScreen.classList.add('transition-all', 'duration-1000', '-translate-y-full', 'opacity-0');
      
      // 3. Tampilkan Konten Utama
      setTimeout(() => {
        envelopeScreen.style.display = 'none';
        mainContent.classList.remove('hidden');
        setTimeout(() => {
          mainContent.classList.add('opacity-100');
          // Jalankan perhitungan animasi kemunculan
          reveal();
        }, 100);
      }, 1000);
    });

    // Kontrol Tombol Jeda/Putar Musik Latar
    let isPlaying = true;
    musicBtn.addEventListener('click', () => {
      if (isPlaying) {
        bgMusic.pause();
        musicBtn.querySelector('i').classList.remove('animate-spin');
        musicBtn.classList.add('opacity-60');
      } else {
        bgMusic.play();
        musicBtn.querySelector('i').classList.add('animate-spin');
        musicBtn.classList.remove('opacity-60');
      }
      isPlaying = !isPlaying;
    });

    // Perhitungan Waktu Hitung Mundur Menuju Acara Utama (5 Juli 2026, 09:00:00 WIB)
    const targetDate = new Date('July 5, 2026 09:00:00').getTime();

    function updateCountdown() {
      const now = new Date().getTime();
      const difference = targetDate - now;

      if (difference > 0) {
        const days = Math.floor(difference / (1000 * 60 * 60 * 24));
        const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((difference % (1000 * 60)) / 1000);

        document.getElementById('days').innerText = String(days).padStart(2, '0');
        document.getElementById('hours').innerText = String(hours).padStart(2, '0');
        document.getElementById('minutes').innerText = String(minutes).padStart(2, '0');
        document.getElementById('seconds').innerText = String(seconds).padStart(2, '0');
      } else {
        document.getElementById('days').innerText = '00';
        document.getElementById('hours').innerText = '00';
        document.getElementById('minutes').innerText = '00';
        document.getElementById('seconds').innerText = '00';
      }
    }
    setInterval(updateCountdown, 1000);
    updateCountdown();

    // Animasi Gulir Layar (Scroll Reveal)
    function reveal() {
      const reveals = document.querySelectorAll('.reveal');
      for (let i = 0; i < reveals.length; i++) {
        const windowHeight = window.innerHeight;
        const elementTop = reveals[i].getBoundingClientRect().top;
        const elementVisible = 100;

        if (elementTop < windowHeight - elementVisible) {
          reveals[i].classList.add('active');
        }
      }
    }
    window.addEventListener('scroll', reveal);

    // Pengiriman RSVP Simulasian Berhasil
    const rsvpForm = document.getElementById('rsvp-form');
    const rsvpStatus = document.getElementById('rsvp-status-card');

    rsvpForm.addEventListener('submit', (e) => {
      e.preventDefault();
      
      const name = document.getElementById('rsvp-name').value;
      const attendance = document.querySelector('input[name="attendance"]:checked').value;
      const guests = document.getElementById('rsvp-guests').value;

      setTimeout(() => {
        rsvpForm.reset();
        rsvpStatus.classList.remove('hidden');
        rsvpStatus.scrollIntoView({ behavior: 'smooth' });
        
        setTimeout(() => {
          rsvpStatus.classList.add('hidden');
        }, 5000);
      }, 500);
    });

    // Pengiriman Pesan Baru Dinamik di Buku Tamu
    const commentForm = document.getElementById('comment-form');
    const commentAuthor = document.getElementById('comment-author');
    const commentRelation = document.getElementById('comment-relation');
    const commentText = document.getElementById('comment-text');
    const commentsContainer = document.getElementById('comments-container');

    commentForm.addEventListener('submit', (e) => {
      e.preventDefault();

      const author = commentAuthor.value;
      const relation = commentRelation.value || 'Tamu';
      const text = commentText.value;

      const newComment = document.createElement('div');
      newComment.className = 'bg-white p-5 rounded-2xl shadow-sm border border-brand-goldlight/30 transition-all duration-500 transform scale-95 opacity-0';
      newComment.innerHTML = `
        <div class="flex items-center justify-between mb-2">
          <h5 class="font-serif font-bold text-brand-navy text-sm">${author}</h5>
          <span class="text-[10px] bg-brand-goldlight/50 text-brand-navy font-semibold px-2 py-0.5 rounded-full">${relation}</span>
        </div>
        <p class="text-slate-600 text-sm italic leading-relaxed">
          "${text}"
        </p>
      `;

      commentsContainer.insertBefore(newComment, commentsContainer.firstChild);

      setTimeout(() => {
        newComment.classList.remove('scale-95', 'opacity-0');
        newComment.classList.add('scale-100', 'opacity-100');
      }, 50);

      commentForm.reset();
    });
  </script>
</body>
</html>

```
