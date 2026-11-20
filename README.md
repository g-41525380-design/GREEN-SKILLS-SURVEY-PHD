<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Soal Selidik Penyelidikan PhD UTHM | Kerangka Kemahiran Hijau TVET</title>

  <!-- Google Fonts: Inter -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet" />

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
          },
          colors: {
            uthmPurple: '#1E1656',
            uthmPurpleLight: '#2E237A',
            uthmRed: '#C8102E',
            ecoGreen: '#15803D',
          },
          animation: {
            'slide-in-right': 'slideInRight 0.35s cubic-bezier(0.16, 1, 0.3, 1) forwards',
            'slide-in-left': 'slideInLeft 0.35s cubic-bezier(0.16, 1, 0.3, 1) forwards',
            'fade-up': 'fadeUp 0.45s cubic-bezier(0.16, 1, 0.3, 1) forwards',
          },
          keyframes: {
            slideInRight: {
              '0%': { opacity: '0', transform: 'translateX(28px)' },
              '100%': { opacity: '1', transform: 'translateX(0)' },
            },
            slideInLeft: {
              '0%': { opacity: '0', transform: 'translateX(-28px)' },
              '100%': { opacity: '1', transform: 'translateX(0)' },
            },
            fadeUp: {
              '0%': { opacity: '0', transform: 'translateY(16px)' },
              '100%': { opacity: '1', transform: 'translateY(0)' },
            },
          },
        },
      },
    };
  </script>

  <style>
    /* Sekatan pemilihan teks umum kecuali ruangan input supaya paparan kemas & terlindung */
    body {
      background-color: #F4F6FA;
      background-image:
        radial-gradient(at 0% 0%, rgba(30, 22, 86, 0.06) 0px, transparent 50%),
        radial-gradient(at 100% 100%, rgba(21, 128, 61, 0.06) 0px, transparent 50%);
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
    }

    input, textarea {
      -webkit-user-select: text;
      -moz-user-select: text;
      -ms-user-select: text;
      user-select: text;
    }

    /* Gaya Butang Skala Likert 5 Warna */
    .scale-btn {
      transition: all 0.2s cubic-bezier(0.22, 1, 0.36, 1);
    }
    .scale-btn:hover {
      transform: translateY(-2px);
    }
    .scale-btn:active {
      transform: scale(0.98);
    }

    /* 1: Merah */
    .scale-1 {
      background-color: #FEF2F2;
      border-color: #FECACA;
      color: #991B1B;
    }
    .scale-1:hover {
      background-color: #FEE2E2;
      border-color: #F87171;
    }
    .scale-1.selected {
      background-color: #DC2626;
      border-color: #991B1B;
      color: #FFFFFF;
      box-shadow: 0 10px 20px -5px rgba(220, 38, 38, 0.45);
    }

    /* 2: Oren */
    .scale-2 {
      background-color: #FFF7ED;
      border-color: #FED7AA;
      color: #9A3412;
    }
    .scale-2:hover {
      background-color: #FFEDD5;
      border-color: #FB923C;
    }
    .scale-2.selected {
      background-color: #EA580C;
      border-color: #9A3412;
      color: #FFFFFF;
      box-shadow: 0 10px 20px -5px rgba(234, 88, 12, 0.45);
    }

    /* 3: Kuning */
    .scale-3 {
      background-color: #FEFCE8;
      border-color: #FEF08A;
      color: #854D0E;
    }
    .scale-3:hover {
      background-color: #FEF9C3;
      border-color: #FACC15;
    }
    .scale-3.selected {
      background-color: #EAB308;
      border-color: #854D0E;
      color: #1E1656;
      box-shadow: 0 10px 20px -5px rgba(234, 179, 8, 0.45);
    }

    /* 4: Hijau Muda */
    .scale-4 {
      background-color: #F7FEE7;
      border-color: #D9F99D;
      color: #3F6212;
    }
    .scale-4:hover {
      background-color: #ECFCCB;
      border-color: #A3E635;
    }
    .scale-4.selected {
      background-color: #65A30D;
      border-color: #3F6212;
      color: #FFFFFF;
      box-shadow: 0 10px 20px -5px rgba(101, 163, 13, 0.45);
    }

    /* 5: Hijau */
    .scale-5 {
      background-color: #F0FDF4;
      border-color: #BBF7D0;
      color: #166534;
    }
    .scale-5:hover {
      background-color: #DCFCE7;
      border-color: #4ADE80;
    }
    .scale-5.selected {
      background-color: #15803D;
      border-color: #14532D;
      color: #FFFFFF;
      box-shadow: 0 10px 20px -5px rgba(21, 128, 61, 0.45);
    }

    .custom-scroll::-webkit-scrollbar {
      width: 6px;
    }
    .custom-scroll::-webkit-scrollbar-track {
      background: #F1F5F9;
      border-radius: 8px;
    }
    .custom-scroll::-webkit-scrollbar-thumb {
      background: #CBD5E1;
      border-radius: 8px;
    }
    .custom-scroll::-webkit-scrollbar-thumb:hover {
      background: #94A3B8;
    }
  </style>
</head>
<body class="min-h-screen flex flex-col text-slate-800 antialiased selection:bg-uthmPurple selection:text-white">

  <!-- ========================================================= -->
  <!-- TOP STICKY HEADER                                         -->
  <!-- ========================================================= -->
  <header class="sticky top-0 z-40 bg-white/95 backdrop-blur-md border-b border-slate-200/80 shadow-sm">
    <div class="max-w-5xl mx-auto px-4 sm:px-6 h-16 sm:h-20 flex items-center justify-between gap-3">
      <!-- Brand / UTHM Emblem -->
      <div onclick="goHome()" class="flex items-center gap-3 cursor-pointer group">
        <div class="w-10 h-11 sm:w-12 sm:h-12 rounded-xl bg-uthmPurple flex items-center justify-center shadow-md group-hover:scale-105 transition-transform shrink-0 p-1.5 border border-slate-200">
          <svg viewBox="0 0 64 72" class="w-full h-full" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 4H58V38C58 54 32 67 32 67C32 67 6 54 6 38V4Z" fill="#1E1656" stroke="#CBD5E1" stroke-width="3"/>
            <circle cx="32" cy="27" r="15" fill="#C8102E"/>
            <polygon points="32,16 44,22 32,28 20,22" fill="#FFFFFF"/>
            <polyline points="20,27 32,33 44,27" stroke="#FFFFFF" stroke-width="2.2" fill="none"/>
            <polyline points="20,32 32,38 44,32" stroke="#FFFFFF" stroke-width="2.2" fill="none"/>
            <circle cx="32" cy="22" r="2.2" fill="#1E1656"/>
            <path d="M18 52L29 47V54L18 59V52Z" fill="#FFFFFF"/>
            <path d="M46 52L35 47V54L46 59V52Z" fill="#FFFFFF"/>
          </svg>
        </div>
        <div class="min-w-0">
          <div class="flex items-center gap-2">
            <span class="font-extrabold text-uthmPurple tracking-tight text-base sm:text-lg leading-none">UTHM</span>
            <span class="hidden sm:inline-block px-2 py-0.5 text-[11px] font-semibold rounded-full bg-emerald-50 text-emerald-700 border border-emerald-200">
              Penyelidikan PhD • TVET
            </span>
          </div>
          <p class="text-[11px] sm:text-xs text-slate-500 truncate mt-0.5 font-medium">
            Universiti Tun Hussein Onn Malaysia
          </p>
        </div>
      </div>

      <!-- Butang Tindakan Responden -->
      <div class="flex items-center gap-2 sm:gap-3">
        <!-- Senarai Soalan (Dipaparkan semasa menjawab) -->
        <button id="navDrawerBtn" onclick="toggleNavDrawer(true)" class="hidden items-center gap-1.5 px-3 py-2 rounded-xl text-xs sm:text-sm font-semibold text-slate-700 bg-slate-100 hover:bg-slate-200 transition border border-slate-200">
          <svg class="w-4 h-4 text-uthmPurple" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h10" />
          </svg>
          <span class="hidden md:inline">Senarai Soalan</span>
          <span id="navBadgeCount" class="px-1.5 py-0.5 text-[11px] rounded-md bg-uthmPurple text-white font-bold">0/77</span>
        </button>

        <!-- Maklumat Penyelidik & Penyelia -->
        <button onclick="toggleResearcherModal(true)" class="flex items-center gap-2 px-3 sm:px-4 py-2 rounded-xl text-xs sm:text-sm font-semibold text-white bg-uthmPurple hover:bg-uthmPurpleLight shadow-sm transition">
          <svg class="w-4 h-4 text-emerald-300 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
          </svg>
          <span class="hidden sm:inline">Maklumat Penyelidik & Penyelia</span>
          <span class="sm:hidden">Penyelidik</span>
        </button>
      </div>
    </div>

    <!-- Bar Kemajuan Responden -->
    <div id="topProgressContainer" class="hidden bg-slate-100 h-1.5 w-full overflow-hidden">
      <div id="topProgressBar" class="h-full bg-gradient-to-r from-uthmPurple via-uthmRed to-ecoGreen transition-all duration-300" style="width: 0%"></div>
    </div>
  </header>

  <!-- ========================================================= -->
  <!-- MAIN CONTENT AREA                                         -->
  <!-- ========================================================= -->
  <main class="flex-1 flex flex-col justify-center max-w-4xl w-full mx-auto px-4 sm:px-6 py-6 sm:py-10">

    <!-- ======================================================= -->
    <!-- VIEW 1: LANDING / PENGENALAN                            -->
    <!-- ======================================================= -->
    <section id="landingView" class="animate-fade-up space-y-6">
      <div class="bg-white rounded-3xl shadow-xl shadow-slate-200/70 border border-slate-200/80 overflow-hidden">
        <!-- Top UTHM Banner -->
        <div class="bg-gradient-to-r from-uthmPurple via-[#281E70] to-uthmPurple px-6 sm:px-10 py-8 sm:py-10 text-white relative overflow-hidden">
          <div class="absolute -right-12 -top-12 w-48 h-48 rounded-full bg-white/5 pointer-events-none"></div>
          <div class="absolute right-20 -bottom-16 w-40 h-40 rounded-full bg-emerald-400/10 pointer-events-none"></div>

          <h1 class="text-xl sm:text-2xl md:text-[26px] font-extrabold leading-snug tracking-tight">
            PEMBANGUNAN KERANGKA KEMAHIRAN HIJAU UNTUK KURIKULUM PROGRAM TEKNOLOGI ELEKTRONIK TVET: DALAM MEMENUHI KEPERLUAN EKONOMI HIJAU
          </h1>
          <p class="mt-3 text-xs sm:text-sm text-indigo-200 font-medium leading-relaxed border-t border-white/15 pt-3">
            DEVELOPMENT OF A GREEN SKILLS FRAMEWORK FOR THE TVET ELECTRONIC TECHNOLOGY PROGRAMME CURRICULUM: MEETING THE NEEDS OF THE GREEN ECONOMY
          </p>
        </div>

        <!-- Body Content -->
        <div class="p-6 sm:p-10 space-y-6">
          <!-- 1. PENGENALAN KAJIAN (DWIBAHASA) -->
          <div class="space-y-4">
            <div class="flex items-center gap-2.5 border-b border-slate-200 pb-2.5">
              <span class="w-2.5 h-6 rounded-full bg-uthmPurple"></span>
              <h2 class="text-base sm:text-lg font-extrabold text-uthmPurple">
                Pengenalan & Tujuan Kajian <span class="font-medium text-slate-500 text-sm">/ Introduction & Research Purpose</span>
              </h2>
            </div>

            <!-- Pengenalan Bahasa Melayu -->
            <div class="p-4 sm:p-5 rounded-2xl bg-slate-50 border border-slate-200/80 space-y-3 text-slate-700 text-sm leading-relaxed">
              <div class="inline-flex items-center gap-1.5 px-2.5 py-0.5 rounded-md bg-uthmPurple/10 text-uthmPurple text-xs font-bold">
                <span>🇲🇾 Bahasa Melayu</span>
              </div>
              <p>
                Kepada Tuan/Puan yang dihormati,
              </p>
              <p>
                Saya, <strong>Adib Farhan bin Zaime</strong>, merupakan pelajar separuh masa bagi program <strong>Doktor Falsafah (PhD) Pendidikan Teknik dan Vokasional di Universiti Tun Hussein Onn Malaysia (UTHM)</strong>. Sehubungan itu, saya memohon kerjasama, sokongan, dan jasa baik daripada pihak tuan/puan sebagai pakar dan pendidik TVET untuk meluangkan sedikit masa bagi melengkapkan instrumen soal selidik penyelidikan ini.
              </p>
              <p>
                Objektif utama kajian ini adalah untuk meneroka, membangunkan, dan mengesahkan <strong>Kerangka Kemahiran Hijau</strong> sebagai nilai tambah yang komprehensif bagi kurikulum <strong>Program Teknologi Elektronik TVET</strong> dalam memenuhi tuntutan pasaran kerja serta pembangunan ekonomi hijau negara. Penyelidikan ini telah dimulakan menggunakan <em>teknik Delphi</em> bagi meneroka dan mengenal pasti komponen serta elemen-elemen utama kemahiran hijau dalam kalangan panel pakar bidang.
              </p>
              <p>
                Menerusi soal selidik ini, pandangan serta kepakaran tuan/puan selaku pendidik TVET amat diperlukan bagi menentukan tahap kepentingan setiap elemen tersebut untuk diterapkan ke dalam kurikulum latihan Program Teknologi Elektronik TVET di Kolej Vokasional Malaysia. Segala maklum balas dan data yang dikumpulkan adalah <strong>sulit</strong> serta digunakan sepenuhnya bagi tujuan akademik sahaja. Soal selidik ini mengandungi <strong>Seksyen A (Demografi)</strong> dan <strong>Seksyen B</strong> yang terbahagi kepada tiga bahagian utama iaitu <strong>Bahagian A (Pengetahuan)</strong>, <strong>Bahagian B (Kemahiran)</strong>, dan <strong>Bahagian C (Sikap dan Nilai)</strong>.
              </p>
            </div>

            <!-- Pengenalan Bahasa Inggeris -->
            <div class="p-4 sm:p-5 rounded-2xl bg-indigo-50/40 border border-indigo-100 space-y-3 text-slate-700 text-sm leading-relaxed">
              <div class="inline-flex items-center gap-1.5 px-2.5 py-0.5 rounded-md bg-indigo-100 text-uthmPurple text-xs font-bold">
                <span>🌐 English</span>
              </div>
              <p>
                Dear Sir/Madam,
              </p>
              <p>
                I am <strong>Adib Farhan bin Zaime</strong>, a part-time student for the <strong>Doctor of Philosophy (PhD) in Technical and Vocational Education at Universiti Tun Hussein Onn Malaysia (UTHM)</strong>. I kindly seek your valuable cooperation, expertise, and support as a TVET educator to participate in this research survey, which is essential to the successful completion of my doctoral thesis.
              </p>
              <p>
                The primary objective of this study is to explore, develop, and validate a comprehensive <strong>Green Skills Framework</strong> as a value-added component for the <strong>TVET Electronic Technology Programme curriculum</strong> to meet the evolving demands of the green economy. This study commenced using the <em>Delphi technique</em> to identify and establish essential green skills components and elements among field experts.
              </p>
              <p>
                Through this questionnaire, your professional judgment as a TVET educator is sought to determine the extent of importance of integrating these elements into the TVET Electronic Technology Programme training curriculum at Malaysian Vocational Colleges. All information and responses provided will be kept <strong>strictly confidential</strong> and used solely for academic research purposes. This instrument comprises <strong>Section A (Demographics)</strong> and <strong>Section B</strong>, divided into three core parts: <strong>Part A (Knowledge)</strong>, <strong>Part B (Skills)</strong>, and <strong>Part C (Attitudes and Values)</strong>.
              </p>
            </div>
          </div>

          <!-- 2. DEFINISI OPERASI KEMAHIRAN HIJAU (DWIBAHASA) -->
          <div class="p-5 sm:p-6 rounded-2xl bg-emerald-50/80 border border-emerald-200 space-y-4">
            <div class="flex items-center gap-2.5 border-b border-emerald-200 pb-2.5">
              <div class="w-8 h-8 rounded-xl bg-emerald-600 text-white flex items-center justify-center shrink-0 shadow-sm">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z" />
                </svg>
              </div>
              <h3 class="text-sm sm:text-base font-extrabold text-emerald-950">
                Definisi Operasi Kemahiran Hijau <span class="font-medium text-emerald-700 text-xs sm:text-sm">/ Operational Definition of Green Skills</span>
              </h3>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-xs sm:text-sm leading-relaxed">
              <!-- Definisi BM -->
              <div class="p-4 rounded-xl bg-white/80 border border-emerald-200/80 text-emerald-950 space-y-2">
                <span class="inline-block px-2 py-0.5 rounded bg-emerald-100 text-emerald-800 text-[11px] font-bold">Bahasa Melayu</span>
                <p>
                  Dalam konteks kajian ini, <strong>Kemahiran Hijau</strong> merujuk kepada satu set keupayaan holistik yang merangkumi <strong>kemahiran teknikal, pengetahuan, nilai, dan sikap</strong> yang diperlukan dalam pekerjaan hijau (<em>green jobs</em>) serta bidang teknologi elektronik bagi menyokong kelestarian ekonomi, sosial, dan pemuliharaan alam sekitar.
                </p>
                <p>
                  Ia melibatkan kecekapan mengaplikasikan teknologi elektronik mesra alam, kecekapan tenaga, pengurusan sisa buangan elektronik (<em>e-waste</em>) secara selamat, reka bentuk litar mampan berteraskan prinsip 5R, serta pembudayaan amalan hijau merentasi aktiviti bengkel, industri, perniagaan, dan komuniti.
                </p>
              </div>

              <!-- Definisi EN -->
              <div class="p-4 rounded-xl bg-white/80 border border-emerald-200/80 text-emerald-950 space-y-2">
                <span class="inline-block px-2 py-0.5 rounded bg-emerald-100 text-emerald-800 text-[11px] font-bold">English</span>
                <p>
                  Within the context of this study, <strong>Green Skills</strong> refer to a holistic set of competencies encompassing <strong>technical skills, knowledge, values, and attitudes</strong> required in green jobs and the electronics technology sector to support economic, social, and environmental sustainability.
                </p>
                <p>
                  This includes proficiency in applying eco-friendly electronic technologies, energy efficiency, safe electronic waste (<em>e-waste</em>) management, sustainable circuit design based on the 5R principles, and cultivating green ethics across workshops, industries, businesses, and communities.
                </p>
              </div>
            </div>
          </div>

          <!-- 3. MAKLUMAT PENYELIDIK & PENYELIA -->
          <div class="space-y-3 pt-1">
            <div class="flex items-center gap-2.5 border-b border-slate-200 pb-2">
              <span class="w-2.5 h-5 rounded-full bg-uthmRed"></span>
              <h3 class="text-sm sm:text-base font-extrabold text-uthmPurple">
                Maklumat Penyelidik & Penyelia <span class="font-medium text-slate-500 text-xs sm:text-sm">/ Researcher & Supervisor Information</span>
              </h3>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <!-- Card 1: Penyelidik -->
              <div class="p-4 sm:p-5 rounded-2xl bg-slate-50 border border-slate-200 hover:border-uthmPurple/30 transition">
                <div class="flex items-center gap-3 mb-2.5">
                  <div class="w-10 h-10 rounded-xl bg-uthmPurple text-white font-bold flex items-center justify-center text-sm shrink-0">
                    AF
                  </div>
                  <div>
                    <span class="text-[11px] font-bold uppercase tracking-wider text-uthmRed">Penyelidik / Researcher</span>
                    <h3 class="font-bold text-slate-900 text-sm sm:text-base">Adib Farhan bin Zaime</h3>
                  </div>
                </div>
                <p class="text-xs text-slate-600 mb-3">
                  Pelajar Doktor Falsafah (PhD) Pendidikan Teknik dan Vokasional, Universiti Tun Hussein Onn Malaysia (UTHM)
                </p>
                <div class="flex flex-wrap gap-2 text-xs">
                  <a href="tel:+60136502508" class="inline-flex items-center gap-1.5 px-2.5 py-1.5 rounded-lg bg-white border border-slate-200 text-slate-700 hover:text-uthmPurple hover:border-uthmPurple transition font-medium">
                    <span>📞</span> +60 13 650 2508
                  </a>
                  <a href="https://wa.me/60136502508" target="_blank" rel="noopener" class="inline-flex items-center gap-1.5 px-2.5 py-1.5 rounded-lg bg-emerald-50 border border-emerald-200 text-emerald-700 hover:bg-emerald-100 transition font-medium">
                    <span>💬</span> WhatsApp
                  </a>
                  <a href="mailto:adibfarhanzaime@gmail.com" class="inline-flex items-center gap-1.5 px-2.5 py-1.5 rounded-lg bg-white border border-slate-200 text-slate-700 hover:text-uthmPurple hover:border-uthmPurple transition font-medium">
                    <span>✉️</span> adibfarhanzaime@gmail.com
                  </a>
                </div>
              </div>

              <!-- Card 2: Penyelia -->
              <div class="p-4 sm:p-5 rounded-2xl bg-slate-50 border border-slate-200 hover:border-uthmPurple/30 transition">
                <div class="flex items-center gap-3 mb-2.5">
                  <div class="w-10 h-10 rounded-xl bg-uthmRed text-white font-bold flex items-center justify-center text-sm shrink-0">
                    LC
                  </div>
                  <div>
                    <span class="text-[11px] font-bold uppercase tracking-wider text-uthmPurple">Penyelia / Supervisor</span>
                    <h3 class="font-bold text-slate-900 text-sm sm:text-base">Prof. Ts. Dr. Lai Chee Sern</h3>
                  </div>
                </div>
                <p class="text-xs text-slate-600 mb-3">
                  Pensyarah Kanan / Senior Lecturer, Fakulti Pendidikan Teknikal & Vokasional (FPTV), UTHM
                </p>
                <div class="flex flex-wrap gap-2 text-xs">
                  <a href="tel:+60125768327" class="inline-flex items-center gap-1.5 px-2.5 py-1.5 rounded-lg bg-white border border-slate-200 text-slate-700 hover:text-uthmPurple hover:border-uthmPurple transition font-medium">
                    <span>📞</span> +60 12 576 8327
                  </a>
                  <a href="https://wa.me/60125768327" target="_blank" rel="noopener" class="inline-flex items-center gap-1.5 px-2.5 py-1.5 rounded-lg bg-emerald-50 border border-emerald-200 text-emerald-700 hover:bg-emerald-100 transition font-medium">
                    <span>💬</span> WhatsApp
                  </a>
                  <a href="mailto:lcsern@uthm.edu.my" class="inline-flex items-center gap-1.5 px-2.5 py-1.5 rounded-lg bg-white border border-slate-200 text-slate-700 hover:text-uthmPurple hover:border-uthmPurple transition font-medium">
                    <span>✉️</span> lcsern@uthm.edu.my
                  </a>
                </div>
              </div>
            </div>
          </div>

          <!-- 4. PANDUAN SKALA LIKERT BERKOD WARNA -->
          <div class="pt-1">
            <h3 class="text-xs font-bold uppercase tracking-wider text-slate-500 mb-3">
              Panduan Skala Likert Berkod Warna / Color-Coded Likert Scale Guide
            </h3>
            <div class="grid grid-cols-2 sm:grid-cols-5 gap-2.5">
              <div class="p-3 rounded-2xl bg-red-50 border border-red-200 text-center">
                <span class="inline-flex items-center justify-center w-7 h-7 rounded-full bg-red-600 text-white font-extrabold text-sm mb-1">1</span>
                <p class="text-xs font-bold text-red-900">Sangat Tidak Penting</p>
                <p class="text-[10px] text-red-700">Not at all important (Stp)</p>
              </div>
              <div class="p-3 rounded-2xl bg-orange-50 border border-orange-200 text-center">
                <span class="inline-flex items-center justify-center w-7 h-7 rounded-full bg-orange-600 text-white font-extrabold text-sm mb-1">2</span>
                <p class="text-xs font-bold text-orange-900">Tidak Penting</p>
                <p class="text-[10px] text-orange-700">Slightly important (Tp)</p>
              </div>
              <div class="p-3 rounded-2xl bg-yellow-50 border border-yellow-200 text-center">
                <span class="inline-flex items-center justify-center w-7 h-7 rounded-full bg-yellow-500 text-uthmPurple font-extrabold text-sm mb-1">3</span>
                <p class="text-xs font-bold text-yellow-900">Hampir Penting</p>
                <p class="text-[10px] text-yellow-800">Somewhat important (Hp)</p>
              </div>
              <div class="p-3 rounded-2xl bg-lime-50 border border-lime-200 text-center">
                <span class="inline-flex items-center justify-center w-7 h-7 rounded-full bg-lime-600 text-white font-extrabold text-sm mb-1">4</span>
                <p class="text-xs font-bold text-lime-900">Penting</p>
                <p class="text-[10px] text-lime-700">Important (P)</p>
              </div>
              <div class="col-span-2 sm:col-span-1 p-3 rounded-2xl bg-green-50 border border-green-200 text-center">
                <span class="inline-flex items-center justify-center w-7 h-7 rounded-full bg-green-700 text-white font-extrabold text-sm mb-1">5</span>
                <p class="text-xs font-bold text-green-900">Sangat Penting</p>
                <p class="text-[10px] text-green-700">Strongly important (Sp)</p>
              </div>
            </div>
          </div>

          <!-- Start / Resume Buttons -->
          <div class="pt-3 flex flex-col sm:flex-row items-center justify-between gap-4 border-t border-slate-100">
            <div class="text-xs text-slate-500 flex items-center gap-2">
              <span class="inline-block w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
              <span>Anggaran masa menjawab: <strong>5 – 8 minit</strong> • Jawapan direkodkan secara automatik.</span>
            </div>

            <div class="flex flex-wrap items-center gap-3 w-full sm:w-auto justify-end">
              <button id="resumeBtn" onclick="startSurvey(true)" class="hidden w-full sm:w-auto px-5 py-3.5 rounded-2xl font-bold text-sm text-uthmPurple bg-purple-50 hover:bg-purple-100 border border-purple-200 transition">
                Sambung Jawapan Sedia Ada →
              </button>
              <button onclick="startSurvey(false)" class="w-full sm:w-auto px-7 py-3.5 rounded-2xl font-bold text-sm sm:text-base text-white bg-gradient-to-r from-uthmPurple to-uthmPurpleLight hover:shadow-lg hover:shadow-uthmPurple/30 transition flex items-center justify-center gap-2">
                <span>Mula Menjawab Soal Selidik</span>
                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6" />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ======================================================= -->
    <!-- VIEW 2: QUESTIONNAIRE ENGINE (ONE BY ONE)               -->
    <!-- ======================================================= -->
    <section id="surveyView" class="hidden space-y-5">
      <!-- Section & Progress Header Pill -->
      <div class="flex flex-wrap items-center justify-between gap-2 px-1">
        <div class="flex items-center gap-2">
          <span id="sectionBadge" class="px-3 py-1 rounded-full text-xs font-bold bg-uthmPurple text-white shadow-sm">
            Seksyen A: Demografi
          </span>
          <span id="subDomainBadge" class="hidden sm:inline-block px-3 py-1 rounded-full text-xs font-semibold bg-white text-slate-600 border border-slate-200">
            Maklumat Responden
          </span>
        </div>

        <div class="flex items-center gap-3 text-xs sm:text-sm font-bold text-slate-600">
          <span>Soalan <span id="currentQNum" class="text-uthmPurple">1</span> / <span id="totalQNum">77</span></span>
          <span class="px-2 py-0.5 rounded-md bg-emerald-100 text-emerald-800 text-xs" id="percentText">0%</span>
        </div>
      </div>

      <!-- Main Question Card -->
      <div id="questionCard" class="bg-white rounded-3xl shadow-xl shadow-slate-200/70 border border-slate-200/80 p-6 sm:p-10 min-h-[380px] flex flex-col justify-between transition-all">
        <!-- Dynamic Question Content Injected Here -->
        <div id="questionContent" class="space-y-6"></div>

        <!-- Validation Notice -->
        <div id="validationToast" class="hidden mt-4 p-3 rounded-xl bg-amber-50 border border-amber-200 text-amber-800 text-xs sm:text-sm font-medium flex items-center gap-2">
          <svg class="w-4 h-4 text-amber-600 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" />
          </svg>
          <span>Sila pilih atau isi jawapan anda sebelum meneruskan ke soalan seterusnya.</span>
        </div>

        <!-- Bottom Navigation Controls -->
        <div class="pt-6 mt-6 border-t border-slate-100 flex items-center justify-between gap-3">
          <button id="prevBtn" onclick="prevQuestion()" class="px-4 sm:px-5 py-3 rounded-2xl text-xs sm:text-sm font-bold text-slate-600 bg-slate-100 hover:bg-slate-200 transition flex items-center gap-1.5 disabled:opacity-40 disabled:pointer-events-none">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
            </svg>
            <span>Sebelumnya</span>
          </button>

          <button id="nextBtn" onclick="nextQuestion()" class="px-6 sm:px-7 py-3 rounded-2xl text-xs sm:text-sm font-bold text-white bg-uthmPurple hover:bg-uthmPurpleLight shadow-md transition flex items-center gap-1.5">
            <span id="nextBtnText">Seterusnya</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
            </svg>
          </button>
        </div>
      </div>
    </section>

    <!-- ======================================================= -->
    <!-- VIEW 3: COMPLETION / TERIMA KASIH (RESPONDEN SAHAJA)    -->
    <!-- ======================================================= -->
    <section id="completionView" class="hidden animate-fade-up space-y-6">
      <div class="bg-white rounded-3xl shadow-xl shadow-slate-200/70 border border-slate-200/80 overflow-hidden">
        <div class="h-2.5 bg-gradient-to-r from-uthmPurple via-uthmRed to-ecoGreen"></div>
        <div class="p-6 sm:p-10">
          <!-- Thank You Header -->
          <div class="text-center max-w-2xl mx-auto mb-8">
            <div class="w-16 h-16 rounded-2xl bg-emerald-100 text-emerald-700 flex items-center justify-center mx-auto mb-4 shadow-sm border border-emerald-200">
              <svg class="w-9 h-9" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M5 13l4 4L19 7" />
              </svg>
            </div>
            <span class="inline-block px-3 py-1 rounded-full bg-emerald-50 text-emerald-700 text-xs font-bold border border-emerald-200 mb-2">
              Soal Selidik Selesai / Survey Completed
            </span>
            <h2 class="text-2xl sm:text-3xl font-extrabold text-uthmPurple mb-2">
              Terima Kasih Atas Kerjasama Tuan/Puan!
            </h2>
            <p class="text-sm sm:text-base text-slate-600">
              Maklum balas kepakaran anda amat bermakna dalam pembangunan Kerangka Kemahiran Hijau untuk Kurikulum Program Teknologi Elektronik TVET di Kolej Vokasional Malaysia.
            </p>

            <!-- Status Penghantaran ke Google Sheet -->
            <div id="cloudSyncStatus" class="mt-5 inline-flex items-center gap-2.5 px-5 py-2.5 rounded-2xl bg-slate-100 border border-slate-200 text-xs sm:text-sm font-semibold text-slate-700">
              <span id="cloudSyncSpinner" class="w-4 h-4 border-2 border-uthmPurple border-t-transparent rounded-full animate-spin"></span>
              <span id="cloudSyncText">Menghantar dan merekodkan jawapan anda...</span>
            </div>

            <!-- Butang Hantar Semula (Jika diperlukan) -->
            <div class="mt-3">
              <button id="retrySyncBtn" onclick="retrySubmitToGoogleSheet()" class="hidden inline-flex items-center gap-1.5 px-4 py-2 rounded-xl text-xs font-bold text-white bg-uthmPurple hover:bg-uthmPurpleLight shadow-sm transition">
                <span>↻ Hantar Semula ke Google Sheet</span>
              </button>
            </div>
          </div>

          <!-- Ringkasan Profil Responden -->
          <div class="p-4 sm:p-5 rounded-2xl bg-slate-50 border border-slate-200 mb-6">
            <h3 class="text-xs font-bold uppercase tracking-wider text-slate-500 mb-3">Ringkasan Profil Responden</h3>
            <div id="summaryProfileGrid" class="grid grid-cols-1 sm:grid-cols-3 gap-3 text-xs sm:text-sm"></div>
          </div>

          <!-- Ringkasan Penyertaan Mengikut Bahagian -->
          <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-8">
            <div class="p-5 rounded-2xl bg-purple-50/70 border border-purple-200">
              <span class="text-xs font-bold text-uthmPurple uppercase">Bahagian A</span>
              <h4 class="font-bold text-slate-900 text-sm mt-0.5">Elemen Pengetahuan</h4>
              <div class="mt-3 flex items-baseline justify-between">
                <span id="partACountBadge" class="text-lg font-extrabold text-uthmPurple">0/10 item</span>
                <span class="text-xs font-semibold text-emerald-700">Lengkap</span>
              </div>
            </div>

            <div class="p-5 rounded-2xl bg-emerald-50/70 border border-emerald-200">
              <span class="text-xs font-bold text-emerald-800 uppercase">Bahagian B</span>
              <h4 class="font-bold text-slate-900 text-sm mt-0.5">Elemen Kemahiran</h4>
              <div class="mt-3 flex items-baseline justify-between">
                <span id="partBCountBadge" class="text-lg font-extrabold text-emerald-800">0/46 item</span>
                <span class="text-xs font-semibold text-emerald-700">Lengkap</span>
              </div>
            </div>

            <div class="p-5 rounded-2xl bg-amber-50/70 border border-amber-200">
              <span class="text-xs font-bold text-amber-900 uppercase">Bahagian C</span>
              <h4 class="font-bold text-slate-900 text-sm mt-0.5">Elemen Sikap & Nilai</h4>
              <div class="mt-3 flex items-baseline justify-between">
                <span id="partCCountBadge" class="text-lg font-extrabold text-amber-900">0/12 item</span>
                <span class="text-xs font-semibold text-emerald-700">Lengkap</span>
              </div>
            </div>
          </div>

          <!-- Footer Actions -->
          <div class="flex flex-wrap items-center justify-between gap-3 pt-4 border-t border-slate-100">
            <button onclick="reviewAnswers()" class="px-5 py-2.5 rounded-xl text-xs sm:text-sm font-semibold text-uthmPurple bg-purple-50 hover:bg-purple-100 border border-purple-200 transition">
              ← Semak Semula Jawapan
            </button>
            <button onclick="resetSurveyConfirm()" class="px-5 py-2.5 rounded-xl text-xs sm:text-sm font-semibold text-slate-600 hover:text-red-600 hover:bg-red-50 transition">
              Mula Responden Baharu
            </button>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ========================================================= -->
  <!-- FOOTER (BERSIH TANPA SEBARANG AKSES PENTADBIR)            -->
  <!-- ========================================================= -->
  <footer class="py-5 px-4 text-center text-xs text-slate-500 border-t border-slate-200/70 bg-white/60">
    <p class="font-semibold text-slate-700">
      Fakulti Pendidikan Teknikal dan Vokasional (FPTV) • Universiti Tun Hussein Onn Malaysia (UTHM)
    </p>
    <p class="mt-1">
      Penyelidik: Adib Farhan bin Zaime | Penyelia: Prof. Ts. Dr. Lai Chee Sern
    </p>
  </footer>

  <!-- ========================================================= -->
  <!-- MODAL 1: MAKLUMAT PENYELIDIK & PENYELIA                   -->
  <!-- ========================================================= -->
  <div id="researcherModal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-xl w-full shadow-2xl border border-slate-200 overflow-hidden animate-fade-up">
      <div class="bg-uthmPurple px-6 py-4 flex items-center justify-between text-white">
        <div class="flex items-center gap-2.5">
          <span class="w-2.5 h-2.5 rounded-full bg-emerald-400"></span>
          <h3 class="font-bold text-base">Maklumat Penyelidik & Penyelia</h3>
        </div>
        <button onclick="toggleResearcherModal(false)" class="p-1.5 rounded-xl hover:bg-white/15 transition">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <div class="p-6 space-y-4 max-h-[80vh] overflow-y-auto custom-scroll">
        <p class="text-xs text-slate-600 leading-relaxed">
          Sebarang pertanyaan atau maklum balas berkaitan kajian <strong>Pembangunan Kerangka Kemahiran Hijau untuk Kurikulum Program Teknologi Elektronik TVET</strong> bolehlah menghubungi:
        </p>

        <!-- Penyelidik -->
        <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200 space-y-2">
          <span class="inline-block px-2.5 py-0.5 rounded-full text-[11px] font-bold bg-red-100 text-uthmRed">
            1. Penyelidik (Pelajar PhD)
          </span>
          <h4 class="font-extrabold text-slate-900 text-base">Adib Farhan bin Zaime</h4>
          <p class="text-xs text-slate-600">
            Program Doktor Falsafah Pendidikan Teknik dan Vokasional<br/>
            Universiti Tun Hussein Onn Malaysia (UTHM)
          </p>
          <div class="pt-2 flex flex-wrap gap-2 text-xs">
            <a href="tel:+60136502508" class="px-3 py-1.5 rounded-xl bg-white border border-slate-200 font-semibold text-slate-700 hover:border-uthmPurple">
              📞 +60 13 650 2508
            </a>
            <a href="https://wa.me/60136502508" target="_blank" rel="noopener" class="px-3 py-1.5 rounded-xl bg-emerald-600 text-white font-semibold hover:bg-emerald-700">
              💬 WhatsApp Penyelidik
            </a>
            <a href="mailto:adibfarhanzaime@gmail.com" class="px-3 py-1.5 rounded-xl bg-white border border-slate-200 font-semibold text-slate-700 hover:border-uthmPurple">
              ✉️ adibfarhanzaime@gmail.com
            </a>
          </div>
        </div>

        <!-- Penyelia -->
        <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200 space-y-2">
          <span class="inline-block px-2.5 py-0.5 rounded-full text-[11px] font-bold bg-purple-100 text-uthmPurple">
            2. Penyelia Utama / Main Supervisor
          </span>
          <h4 class="font-extrabold text-slate-900 text-base">Prof. Ts. Dr. Lai Chee Sern</h4>
          <p class="text-xs text-slate-600">
            Pensyarah Kanan / Senior Lecturer<br/>
            Fakulti Pendidikan Teknikal & Vokasional (FPTV), UTHM
          </p>
          <div class="pt-2 flex flex-wrap gap-2 text-xs">
            <a href="tel:+60125768327" class="px-3 py-1.5 rounded-xl bg-white border border-slate-200 font-semibold text-slate-700 hover:border-uthmPurple">
              📞 +60 12 576 8327
            </a>
            <a href="https://wa.me/60125768327" target="_blank" rel="noopener" class="px-3 py-1.5 rounded-xl bg-emerald-600 text-white font-semibold hover:bg-emerald-700">
              💬 WhatsApp Penyelia
            </a>
            <a href="mailto:lcsern@uthm.edu.my" class="px-3 py-1.5 rounded-xl bg-white border border-slate-200 font-semibold text-slate-700 hover:border-uthmPurple">
              ✉️ lcsern@uthm.edu.my
            </a>
          </div>
        </div>
      </div>

      <div class="px-6 py-3.5 bg-slate-50 border-t border-slate-200 flex justify-end">
        <button onclick="toggleResearcherModal(false)" class="px-5 py-2 rounded-xl text-xs sm:text-sm font-bold text-white bg-uthmPurple hover:bg-uthmPurpleLight transition">
          Tutup
        </button>
      </div>
    </div>
  </div>

  <!-- ========================================================= -->
  <!-- MODAL 2: NAVIGASI PANTAS SOALAN                           -->
  <!-- ========================================================= -->
  <div id="navDrawerModal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/60 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-2xl w-full shadow-2xl border border-slate-200 overflow-hidden animate-fade-up">
      <div class="bg-uthmPurple px-6 py-4 flex items-center justify-between text-white">
        <div>
          <h3 class="font-bold text-base">Senarai & Status Soalan</h3>
          <p class="text-xs text-indigo-200">Klik mana-mana nombor soalan untuk melompat terus</p>
        </div>
        <button onclick="toggleNavDrawer(false)" class="p-1.5 rounded-xl hover:bg-white/15 transition">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <div class="p-5 max-h-[65vh] overflow-y-auto custom-scroll space-y-5" id="navDrawerGrid"></div>

      <div class="px-6 py-3.5 bg-slate-50 border-t border-slate-200 flex flex-wrap items-center justify-between gap-2">
        <div class="flex items-center gap-3 text-xs text-slate-600">
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded bg-emerald-500 inline-block"></span> Dijawab</span>
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded bg-slate-200 inline-block"></span> Belum</span>
        </div>
        <button onclick="finishSurveyEarlyCheck()" class="px-4 py-2 rounded-xl text-xs font-bold text-white bg-emerald-700 hover:bg-emerald-800 transition">
          Hantar Soal Selidik →
        </button>
      </div>
    </div>
  </div>

  <!-- ========================================================= -->
  <!-- JAVASCRIPT APPLICATION LOGIC & GOOGLE SHEET SYNC          -->
  <!-- ========================================================= -->
  <script>
    (function () {
      'use strict';

      // Sekat klik kanan & pintasan melihat kod sumber / DevTools supaya responden hanya fokus menjawab soalan
      document.addEventListener('contextmenu', function (e) {
        if (e.target.tagName !== 'INPUT' && e.target.tagName !== 'TEXTAREA') {
          e.preventDefault();
        }
      });

      document.addEventListener('keydown', function (e) {
        const key = (e.key || '').toUpperCase();
        if (
          e.key === 'F12' ||
          (e.ctrlKey && e.shiftKey && (key === 'I' || key === 'J' || key === 'C')) ||
          (e.ctrlKey && (key === 'U' || key === 'S')) ||
          (e.metaKey && e.altKey && (key === 'I' || key === 'J' || key === 'C')) ||
          (e.metaKey && (key === 'U' || key === 'S'))
        ) {
          e.preventDefault();
          return false;
        }
      });

      // URL Google Apps Script Web App
      const GOOGLE_SHEET_WEBAPP_URL = 'https://script.google.com/macros/s/AKfycbweOY7QBE0FrxsgQ-tVWkAHGQZM732D5t_28itmuRWCbeDobVIAyihPot-jdIaFYf8rYg/exec';

      // Skala Likert 1-5 Berkod Warna
      const LIKERT_SCALE = [
        { value: 1, abbr: 'Stp', labelMs: 'Sangat Tidak Penting', labelEn: 'Not at all important', colorClass: 'scale-1', dotColor: 'bg-red-600' },
        { value: 2, abbr: 'Tp', labelMs: 'Tidak Penting', labelEn: 'Slightly important', colorClass: 'scale-2', dotColor: 'bg-orange-600' },
        { value: 3, abbr: 'Hp', labelMs: 'Hampir Penting', labelEn: 'Somewhat important', colorClass: 'scale-3', dotColor: 'bg-yellow-500' },
        { value: 4, abbr: 'P', labelMs: 'Penting', labelEn: 'Important', colorClass: 'scale-4', dotColor: 'bg-lime-600' },
        { value: 5, abbr: 'Sp', labelMs: 'Sangat Penting', labelEn: 'Strongly important', colorClass: 'scale-5', dotColor: 'bg-green-700' },
      ];

      // Senarai Penuh 77 Item Soal Selidik
      const QUESTIONS = [
        // ==================== SEKSYEN A: DEMOGRAFI ====================
        {
          id: 'D1',
          section: 'Seksyen A: Demografi',
          subDomain: 'Maklumat Latar Belakang Responden',
          code: '1',
          type: 'choice',
          required: true,
          textMs: 'Jantina',
          textEn: 'Gender',
          options: [
            { value: 'Lelaki', labelMs: 'Lelaki', labelEn: 'Male' },
            { value: 'Perempuan', labelMs: 'Perempuan', labelEn: 'Female' },
          ],
        },
        {
          id: 'D2',
          section: 'Seksyen A: Demografi',
          subDomain: 'Maklumat Latar Belakang Responden',
          code: '2',
          type: 'choice',
          required: true,
          textMs: 'Umur',
          textEn: 'Age',
          options: [
            { value: '23-32 tahun', labelMs: '23 – 32 tahun', labelEn: '23 – 32 years old' },
            { value: '33-42 tahun', labelMs: '33 – 42 tahun', labelEn: '33 – 42 years old' },
            { value: '43-52 tahun', labelMs: '43 – 52 tahun', labelEn: '43 – 52 years old' },
            { value: '53 tahun & ke atas', labelMs: '53 tahun & ke atas', labelEn: '53 years old & above' },
          ],
        },
        {
          id: 'D3',
          section: 'Seksyen A: Demografi',
          subDomain: 'Maklumat Latar Belakang Responden',
          code: '3',
          type: 'choice',
          required: true,
          textMs: 'Tahap Pendidikan Tertinggi',
          textEn: 'Education Level',
          options: [
            { value: 'Diploma / DKM', labelMs: 'Diploma / Diploma Kemahiran Malaysia (DKM)', labelEn: 'Diploma / Malaysian Skills Diploma' },
            { value: 'Diploma Lanjutan / DLKM', labelMs: 'Diploma Lanjutan Kemahiran Malaysia (DLKM)', labelEn: 'Malaysian Advanced Skills Diploma' },
            { value: 'Sarjana Muda', labelMs: 'Sarjana Muda', labelEn: "Bachelor's Degree" },
            { value: 'Sarjana', labelMs: 'Sarjana', labelEn: "Master's Degree" },
            { value: 'Doktor Falsafah (PhD)', labelMs: 'Doktor Falsafah (PhD)', labelEn: 'Doctor of Philosophy (PhD)' },
          ],
        },
        {
          id: 'D4',
          section: 'Seksyen A: Demografi',
          subDomain: 'Maklumat Latar Belakang Responden',
          code: '4',
          type: 'choice',
          required: true,
          textMs: 'Pengalaman Mengajar',
          textEn: 'Teaching Experience',
          options: [
            { value: '0-5 tahun', labelMs: '0 – 5 tahun', labelEn: '0 – 5 years' },
            { value: '6-10 tahun', labelMs: '6 – 10 tahun', labelEn: '6 – 10 years' },
            { value: '11 tahun & ke atas', labelMs: '11 tahun & ke atas', labelEn: '11 years & above' },
          ],
        },
        {
          id: 'D5',
          section: 'Seksyen A: Demografi',
          subDomain: 'Maklumat Latar Belakang Responden',
          code: '5',
          type: 'text',
          required: true,
          textMs: 'Subjek atau Modul Utama yang Diajar',
          textEn: 'Main Subjects or Modules Taught',
          placeholder: 'Contoh: Teknologi Elektronik, Sistem Terbenam / Mikropengawal, Lukisan Kejuruteraan...',
        },
        {
          id: 'D6',
          section: 'Seksyen A: Demografi',
          subDomain: 'Maklumat Latar Belakang Responden',
          code: '6',
          type: 'text',
          required: true,
          textMs: 'Nama Kolej Vokasional / Institusi',
          textEn: 'Vocational College / Institution Name',
          placeholder: 'Contoh: Kolej Vokasional Batu Pahat',
        },

        // ==================== BAHAGIAN A: ELEMEN PENGETAHUAN ====================
        {
          id: 'A1_0', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '1.0 Pengetahuan Teknologi Hijau Elektronik',
          code: '1.0', type: 'likert', required: true,
          textMs: 'Pengetahuan Teknologi Hijau Elektronik',
          textEn: 'Knowledge of Green Electronic Technology',
        },
        {
          id: 'A1_1', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '1.0 Pengetahuan Teknologi Hijau Elektronik',
          code: '1.1', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang teknologi hijau dalam bidang elektronik (seperti sistem solar fotovolta, penyongsang, dan pengurusan bateri).',
          textEn: 'Knowledge of green technology in the electronics field (such as solar photovoltaic systems, inverters, and battery management).',
        },
        {
          id: 'A1_2', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '1.0 Pengetahuan Teknologi Hijau Elektronik',
          code: '1.2', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang reka bentuk dan pembangunan produk teknologi hijau dalam bidang elektronik.',
          textEn: 'Knowledge of green technology product design and development in electronics.',
        },
        {
          id: 'A1_3', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '1.0 Pengetahuan Teknologi Hijau Elektronik',
          code: '1.3', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang aplikasi produk teknologi hijau dalam bidang elektronik (seperti ESP32, dan papan litar PCB bebas plumbum).',
          textEn: 'Knowledge concerning the application of green technology products in the field of electronics (such as ESP32 and lead-free PCBs).',
        },
        {
          id: 'A1_4', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '1.0 Pengetahuan Teknologi Hijau Elektronik',
          code: '1.4', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang penyelenggaraan atau pengujian kualiti bagi produk teknologi hijau elektronik.',
          textEn: 'Knowledge of maintenance or testing for green electronic products.',
        },
        {
          id: 'A2_0', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
          code: '2.0', type: 'likert', required: true,
          textMs: 'Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
          textEn: 'Knowledge of Electronic Waste (E-Waste) and Waste Material Management',
        },
        {
          id: 'A2_1', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
          code: '2.1', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang pengurusan bahan berbahaya dalam sisa elektronik (seperti pateri plumbum, kadmium, dan elektrolit bateri).',
          textEn: 'Knowledge of management of hazardous materials in e-waste (such as lead solder, cadmium, and battery electrolytes).',
        },
        {
          id: 'A2_2', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
          code: '2.2', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang kaedah pelupusan sisa pepejal atau komponen elektronik terpakai secara selamat.',
          textEn: 'Knowledge of safe disposal methods for solid waste or used electronic components.',
        },
        {
          id: 'A2_3', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
          code: '2.3', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang aplikasi prinsip 5R (reduce, reuse, recycle, recover & refuse) dalam pengurusan bahan elektronik.',
          textEn: 'Knowledge of applying 5R principles (reduce, reuse, recycle, recover & refuse) in managing electronics materials.',
        },
        {
          id: 'A2_4', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
          code: '2.4', type: 'likert', required: true,
          textMs: 'Pengetahuan tentang pengasingan sisa bahan buangan atau komponen elektronik yang rosak.',
          textEn: 'Knowledge of segregation of waste materials or defective electronic components.',
        },
        {
          id: 'A_OPEN', part: 'A', section: 'Bahagian A: Elemen Pengetahuan',
          subDomain: 'Soalan Terbuka Bahagian A',
          code: 'Terbuka A', type: 'textarea', required: false,
          textMs: 'Apakah elemen pengetahuan kemahiran hijau lain yang penting tetapi tidak tersenarai di atas? (Pilihan)',
          textEn: 'What other green skills knowledge elements are important but not listed above? (Optional)',
          placeholder: 'Taipkan cadangan elemen pengetahuan tambahan di sini (atau tekan Seterusnya jika tiada)...',
        },

        // ==================== BAHAGIAN B: ELEMEN KEMAHIRAN ====================
        {
          id: 'B1_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
          code: '1.0', type: 'likert', required: true,
          textMs: 'Kemahiran Pengurusan Sisa Buangan Elektronik',
          textEn: 'Electronic Waste (E-Waste) Management Skills',
        },
        {
          id: 'B1_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
          code: '1.1', type: 'likert', required: true,
          textMs: 'Kemahiran mengurangkan pembaziran bahan semasa proses pematerian dan pembuatan papan litar bercetak (PCB).',
          textEn: 'Skills in reducing material waste during soldering and PCB fabrication/assembly.',
        },
        {
          id: 'B1_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
          code: '1.2', type: 'likert', required: true,
          textMs: 'Kemahiran menggunakan semula komponen elektronik yang masih berfungsi.',
          textEn: 'Skill in reusing functional electronic components.',
        },
        {
          id: 'B1_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
          code: '1.3', type: 'likert', required: true,
          textMs: 'Kemahiran mengitar semula sisa logam atau komponen elektronik terpakai.',
          textEn: 'Skills in recycling scrap metal or used electronic components.',
        },
        {
          id: 'B1_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
          code: '1.4', type: 'likert', required: true,
          textMs: 'Kemahiran membaiki peralatan elektronik yang rosak.',
          textEn: 'Skills in repairing damaged electronic equipment.',
        },
        {
          id: 'B2_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
          code: '2.0', type: 'likert', required: true,
          textMs: 'Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
          textEn: 'Eco-Friendly Circuit and Electronic Device Design Skills',
        },
        {
          id: 'B2_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
          code: '2.1', type: 'likert', required: true,
          textMs: 'Kemahiran mereka bentuk litar elektronik berkecekapan tinggi atau berkuasa rendah (low-power design).',
          textEn: 'Skills in designing high-efficiency or low-power electronic circuits.',
        },
        {
          id: 'B2_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
          code: '2.2', type: 'likert', required: true,
          textMs: 'Kemahiran mereka bentuk perkakasan elektronik mesra alam berteraskan perlindungan alam sekitar.',
          textEn: 'Skills in designing eco-friendly electronic hardware focused on environmental protection.',
        },
        {
          id: 'B2_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
          code: '2.3', type: 'likert', required: true,
          textMs: 'Kemahiran mereka bentuk litar yang menekankan prinsip 5R (reduce, reuse, recycle, recover & refuse).',
          textEn: 'Skills in designing circuits that emphasize the 5R principles (reduce, reuse, recycle, recover, and refuse).',
        },
        {
          id: 'B2_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
          code: '2.4', type: 'likert', required: true,
          textMs: 'Kemahiran mengaplikasikan prinsip reka bentuk mampan dalam penghasilan produk elektronik.',
          textEn: 'Skills in applying sustainable design principles in electronic product development.',
        },
        {
          id: 'B3_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          code: '3.0', type: 'likert', required: true,
          textMs: 'Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          textEn: 'Skills in the planning, management, and procurement of electronic equipment and components.',
        },
        {
          id: 'B3_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          code: '3.1', type: 'likert', required: true,
          textMs: 'Kemahiran merancang projek elektronik berasaskan kelestarian alam sekitar.',
          textEn: 'Skills in planning environmentally sustainable electronic projects.',
        },
        {
          id: 'B3_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          code: '3.2', type: 'likert', required: true,
          textMs: 'Kemahiran memilih eko-bahan (seperti pateri bebas plumbum dan bahan PCB mesra alam).',
          textEn: 'Skills in selecting eco-materials (such as lead-free solder and eco-friendly PCB materials).',
        },
        {
          id: 'B3_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          code: '3.3', type: 'likert', required: true,
          textMs: 'Kemahiran pengurusan inventori komponen elektronik mesra alam (seperti penyimpanan berlabel, sistem FiFo dan kabinet pengering pintar).',
          textEn: 'Skills in managing inventory of eco-friendly electronic component (such as labeled storage, FiFo systems, and smart dry cabinets).',
        },
        {
          id: 'B3_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          code: '3.4', type: 'likert', required: true,
          textMs: 'Kemahiran perolehan mampan bagi peralatan elektronik (seperti kriteria pembungkusan hijau dan rantai bekalan mesra alam).',
          textEn: 'Skills in sustainable procurement for electronic equipment (such as green packaging criteria and eco-friendly supply chains).',
        },
        {
          id: 'B3_5', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
          code: '3.5', type: 'likert', required: true,
          textMs: 'Kemahiran perolehan perkhidmatan penyelenggaraan elektronik mesra alam.',
          textEn: 'Skills in procuring eco-friendly electronic maintenance services.',
        },
        {
          id: 'B4_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.0', type: 'likert', required: true,
          textMs: 'Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          textEn: 'Energy Saving and Electronic Power Efficiency Skills',
        },
        {
          id: 'B4_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.1', type: 'likert', required: true,
          textMs: 'Kemahiran mengoptimumkan pengurusan tenaga dalam sistem atau peranti elektronik.',
          textEn: 'Skills in optimizing energy management in electronic systems or devices.',
        },
        {
          id: 'B4_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.2', type: 'likert', required: true,
          textMs: 'Kemahiran mengaplikasikan peranti elektronik dalam sistem tenaga boleh baharu (seperti tenaga solar dan angin).',
          textEn: 'Skills in applying electronic devices to renewable energy systems (such as solar and wind energy).',
        },
        {
          id: 'B4_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.3', type: 'likert', required: true,
          textMs: 'Kemahiran menganalisis kecekapan sistem pengurusan tenaga untuk mengurangkan pembaziran elektrik.',
          textEn: 'Skills in analyzing energy management system efficiency to minimize electrical waste.',
        },
        {
          id: 'B4_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.4', type: 'likert', required: true,
          textMs: 'Kemahiran mengoptimumkan kualiti atau kecekapan kuasa litar.',
          textEn: 'Skills in optimizing circuit power quality or circuit power efficiency.',
        },
        {
          id: 'B4_5', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.5', type: 'likert', required: true,
          textMs: 'Kemahiran mereka bentuk sistem pengurusan haba litar bagi mengurangkan pelepasan haba.',
          textEn: 'Skills in designing circuit thermal management systems to reduce heat dissipation.',
        },
        {
          id: 'B4_6', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.6', type: 'likert', required: true,
          textMs: 'Kemahiran kawalan dan pengurusan kualiti kuasa dalam sistem elektronik.',
          textEn: 'Skills in power quality control and management in electronic systems.',
        },
        {
          id: 'B4_7', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
          code: '4.7', type: 'likert', required: true,
          textMs: 'Kemahiran mengintegrasikan sistem penuaian tenaga (seperti penderia piezoelektrik).',
          textEn: 'Skills in integrating energy harvesting systems (such as piezoelectric sensors).',
        },
        {
          id: 'B5_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          code: '5.0', type: 'likert', required: true,
          textMs: 'Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          textEn: 'Green Technology-Based Communication Skills in the Electronics Field',
        },
        {
          id: 'B5_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          code: '5.1', type: 'likert', required: true,
          textMs: 'Kemahiran berkomunikasi secara digital tanpa kertas dalam pelaksanaan tugasan amali elektronik.',
          textEn: 'Skills in paperless digital communication during electronic practical tasks.',
        },
        {
          id: 'B5_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          code: '5.2', type: 'likert', required: true,
          textMs: 'Kemahiran berkomunikasi menggunakan sistem ICT (Teknologi Maklumat dan Komunikasi) hijau (seperti e-mel).',
          textEn: 'Skills in communicating using green ICT (Information and Communications Technology) systems (such as email).',
        },
        {
          id: 'B5_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          code: '5.3', type: 'likert', required: true,
          textMs: 'Kemahiran berkomunikasi atau mengawal peranti menggunakan sistem IoT (Internet Pelbagai Benda).',
          textEn: 'Skills in communicating or controlling devices using IoT (Internet of Things) systems.',
        },
        {
          id: 'B5_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          code: '5.4', type: 'likert', required: true,
          textMs: 'Kemahiran mengaplikasikan platform komunikasi digital hibrid (seperti Google Meet dan Zoom) bagi mengurangkan pelepasan gas rumah hijau.',
          textEn: 'Skills in applying hybrid digital communication platforms, such as Google Meet and Zoom, to reduce greenhouse gas emissions.',
        },
        {
          id: 'B5_5', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
          code: '5.5', type: 'likert', required: true,
          textMs: 'Kemahiran mengendalikan pemantauan data litar secara jarak jauh menggunakan aplikasi pengkomputeran awan mesra tenaga.',
          textEn: 'Skills in remote circuit data monitoring using energy-efficient cloud computing applications.',
        },
        {
          id: 'B6_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          code: '6.0', type: 'likert', required: true,
          textMs: 'Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          textEn: 'Teamwork Skills for Green Practices in Electronics',
        },
        {
          id: 'B6_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          code: '6.1', type: 'likert', required: true,
          textMs: 'Kemahiran kerja berpasukan memastikan setiap ahli menyumbang secara aktif kepada amalan hijau di makmal atau bengkel.',
          textEn: 'Teamwork skills to ensure every member actively contributes to green practices in the laboratory or workshop.',
        },
        {
          id: 'B6_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          code: '6.2', type: 'likert', required: true,
          textMs: 'Kemahiran berkolaborasi dengan pihak luar/industri bagi menyokong aktiviti pencegahan pencemaran alam sekitar.',
          textEn: 'Skills in collaborating with external parties/industry to support environmental pollution prevention activities.',
        },
        {
          id: 'B6_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          code: '6.3', type: 'likert', required: true,
          textMs: 'Kemahiran perhubungan pasukan secara segerak (seperti persidangan video atau audio) bagi mencegah pencemaran alam sekitar.',
          textEn: 'Skills in synchronous team communication (such as video or audio conferencing) to prevent environmental pollution.',
        },
        {
          id: 'B6_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          code: '6.4', type: 'likert', required: true,
          textMs: 'Kemahiran memahami peranan ahli pasukan berasaskan keperluan teknikal bagi mencegah pencemaran alam sekitar.',
          textEn: "Skills in understanding team members' roles based on technical requirements to prevent environmental pollution.",
        },
        {
          id: 'B6_5', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
          code: '6.5', type: 'likert', required: true,
          textMs: 'Kemahiran mengkoordinasi peranan ahli pasukan bagi meminimumkan pembaziran komponen dan bahan amali.',
          textEn: 'Skills in coordinating team roles to minimize component and practical material waste.',
        },
        {
          id: 'B7_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.0', type: 'likert', required: true,
          textMs: 'Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          textEn: 'Problem-Solving and Creative Thinking Skills in Green Electronics',
        },
        {
          id: 'B7_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.1', type: 'likert', required: true,
          textMs: 'Kemahiran menyelesaikan masalah kegagalan litar dengan mengambil kira pengurangan impak negatif alam sekitar.',
          textEn: 'Skills in troubleshooting circuit failure by taking into account environmental impact reduction.',
        },
        {
          id: 'B7_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.2', type: 'likert', required: true,
          textMs: 'Kemahiran berfikir secara kritis dalam mereka bentuk peranti elektronik mesra alam.',
          textEn: 'Critical thinking skills in designing eco-friendly electronic devices.',
        },
        {
          id: 'B7_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.3', type: 'likert', required: true,
          textMs: 'Kemahiran berfikir secara strategik bagi mengurangkan jejak karbon (carbon footprint) produk elektronik.',
          textEn: 'Strategic thinking skills to reduce the carbon footprint of electronic products.',
        },
        {
          id: 'B7_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.4', type: 'likert', required: true,
          textMs: 'Kemahiran berfikir secara terbuka terhadap inovasi teknologi hijau baharu dalam bidang elektronik.',
          textEn: 'Skills in adopting an open-minded approach toward new green technology innovations in the electronics field.',
        },
        {
          id: 'B7_5', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.5', type: 'likert', required: true,
          textMs: 'Kemahiran Berfikir Aras Tinggi (KBAT) dalam merancang penyelesaian kelestarian sistem elektronik.',
          textEn: 'Higher Order Thinking Skills (HOTS) in planning electronic system sustainability solutions.',
        },
        {
          id: 'B7_6', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
          code: '7.6', type: 'likert', required: true,
          textMs: 'Kemahiran berfikir secara strategik bagi mengurangkan jejak karbon (carbon footprint) produk elektronik.',
          textEn: 'Strategic thinking skill to reduce the carbon footprint of electronic products.',
        },
        {
          id: 'B8_0', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          code: '8.0', type: 'likert', required: true,
          textMs: 'Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          textEn: 'Biodiversity and Ecosystem Protection Skills through Electronic Applications',
        },
        {
          id: 'B8_1', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          code: '8.1', type: 'likert', required: true,
          textMs: 'Kemahiran melindungi alam sekitar melalui penggunaan peralatan atau peranti pengawasan elektronik yang sesuai haruslah diterapkan dalam kurikulum Program Teknologi Elektronik TVET.',
          textEn: 'Environmental protection skills through the appropriate use of electronic monitoring equipment or devices should be incorporated into the Electronic Technology Program curriculum.',
        },
        {
          id: 'B8_2', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          code: '8.2', type: 'likert', required: true,
          textMs: 'Kemahiran pemantauan elektronik bagi memulihara biodiversiti haruslah diterapkan dalam kurikulum Program Teknologi Elektronik TVET.',
          textEn: 'Electronic monitoring skills to conserve biodiversity should be incorporated into the Electronic Technology Program curriculum.',
        },
        {
          id: 'B8_3', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          code: '8.3', type: 'likert', required: true,
          textMs: 'Kemahiran mengaplikasikan penderia (sensors) atau peranti elektronik bagi pemantauan kualiti alam sekitar/ekosistem.',
          textEn: 'Skills in applying sensors or electronic devices for environmental/ecosystem quality monitoring.',
        },
        {
          id: 'B8_4', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          code: '8.4', type: 'likert', required: true,
          textMs: 'Kemahiran mengaplikasikan sistem elektronik hijau (seperti solar) bagi memulihara landskap alam sekitar.',
          textEn: 'Skills in applying green electronic systems (such as solar) to conserve environmental landscapes.',
        },
        {
          id: 'B8_5', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
          code: '8.5', type: 'likert', required: true,
          textMs: 'Kemahiran menyelenggara sistem dan peranti pemantauan elektronik hijau.',
          textEn: 'Skills in maintaining green electronic monitoring systems and devices.',
        },
        {
          id: 'B_OPEN', part: 'B', section: 'Bahagian B: Elemen Kemahiran',
          subDomain: 'Soalan Terbuka Bahagian B',
          code: 'Terbuka B', type: 'textarea', required: false,
          textMs: 'Apakah elemen kemahiran praktikal hijau lain yang penting tetapi tidak tersenarai di atas? (Pilihan)',
          textEn: 'What other practical green skill elements are important but not listed above? (Optional)',
          placeholder: 'Taipkan cadangan kemahiran praktikal tambahan di sini (atau tekan Seterusnya jika tiada)...',
        },

        // ==================== BAHAGIAN C: ELEMEN SIKAP DAN NILAI ====================
        {
          id: 'C1_0', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
          code: '1.0', type: 'likert', required: true,
          textMs: 'Kesedaran Alam Sekitar dalam Bidang Elektronik',
          textEn: 'Environmental Awareness in the Field of Electronics',
        },
        {
          id: 'C1_1', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
          code: '1.1', type: 'likert', required: true,
          textMs: 'Kesedaran terhadap kepentingan melindungi alam sekitar di tempat kerja atau bengkel elektronik.',
          textEn: 'Awareness of the importance of environmental protection in the workplace or electronics workshop.',
        },
        {
          id: 'C1_2', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
          code: '1.2', type: 'likert', required: true,
          textMs: 'Kesedaran terhadap dasar, perundangan, atau standard piawaian hijau industri elektronik.',
          textEn: 'Awareness of green policies, regulations, or industry standards in electronics.',
        },
        {
          id: 'C1_3', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
          code: '1.3', type: 'likert', required: true,
          textMs: 'Kesedaran terhadap impak pengurangan sisa buangan elektronik (e-waste) kepada alam sekitar.',
          textEn: 'Awareness of the impact of electronic waste (e-waste) reduction on the environment.',
        },
        {
          id: 'C1_4', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
          code: '1.4', type: 'likert', required: true,
          textMs: 'Kesedaran terhadap amalan hijau dalam proses pembuatan atau perkhidmatan elektronik.',
          textEn: 'Awareness of green practices in electronic manufacturing or service processes.',
        },
        {
          id: 'C1_5', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
          code: '1.5', type: 'likert', required: true,
          textMs: 'Kesedaran terhadap penggunaan sumber tenaga boleh baharu dalam pengoperasian sistem elektronik.',
          textEn: 'Awareness of using renewable energy sources in electronic system operations.',
        },
        {
          id: 'C2_0', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
          code: '2.0', type: 'likert', required: true,
          textMs: 'Nilai Positif & Budaya Hijau Industri Elektronik',
          textEn: 'Positive Values and Green Culture in the Electronics Industry',
        },
        {
          id: 'C2_1', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
          code: '2.1', type: 'likert', required: true,
          textMs: 'Nilai amalan penjimatan tenaga elektrik (seperti mematikan peralatan dan suis utama apabila tidak digunakan).',
          textEn: 'Values of electrical energy conservation practices (such as switching off equipment and main switches when not in use).',
        },
        {
          id: 'C2_2', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
          code: '2.2', type: 'likert', required: true,
          textMs: 'Nilai amalan 5R (reduce, reuse, recycle, recover & refuse) terhadap perkakasan elektronik.',
          textEn: 'Values of the 5R practices (reduce, reuse, recycle, recover, and refuse) regarding electronic hardware.',
        },
        {
          id: 'C2_3', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
          code: '2.3', type: 'likert', required: true,
          textMs: 'Nilai komitmen terhadap pengurusan selamat sisa toksik (seperti asid punaran) atau komponen berbahaya (seperti bateri litium atau kapasitor elektrolit).',
          textEn: 'Values of commitment to safe management of toxic waste (such as etching acid) or hazardous components (such as lithium batteries or electrolytic capacitors).',
        },
        {
          id: 'C2_4', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
          code: '2.4', type: 'likert', required: true,
          textMs: 'Nilai keutamaan terhadap pemuliharaan sumber melalui kecekapan reka bentuk litar.',
          textEn: 'Values of prioritizing resource conservation through circuit design efficiency.',
        },
        {
          id: 'C2_5', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
          code: '2.5', type: 'likert', required: true,
          textMs: 'Nilai pembudayaan amalan atau etika hijau dalam kerjaya bidang elektronik.',
          textEn: 'Values of cultivating green practices or ethics in electronic careers.',
        },
        {
          id: 'C_OPEN', part: 'C', section: 'Bahagian C: Elemen Sikap dan Nilai',
          subDomain: 'Soalan Terbuka Bahagian C',
          code: 'Terbuka C', type: 'textarea', required: false,
          textMs: 'Apakah elemen sikap dan nilai hijau lain yang penting tetapi tidak tersenarai di atas? (Pilihan)',
          textEn: 'What other green attitudes and values elements are important but not listed above? (Optional)',
          placeholder: 'Taipkan cadangan sikap & nilai hijau tambahan di sini (atau tekan Hantar Soal Selidik)...',
        },
      ];

      // State Aplikasi (Dalam Memori Sesi Sahaja)
      let currentIndex = 0;
      let responses = {};
      let autoAdvanceTimer = null;
      let submissionId = null;
      let lastSubmissionPayload = null;

      window.addEventListener('DOMContentLoaded', () => {
        document.getElementById('totalQNum').textContent = QUESTIONS.length;
        updateProgressUI();
      });

      function updateProgressUI() {
        const total = QUESTIONS.length;
        const answeredCount = QUESTIONS.filter((q) => {
          const val = responses[q.id];
          return val !== undefined && val !== null && String(val).trim() !== '';
        }).length;

        const pct = Math.round((answeredCount / total) * 100);
        document.getElementById('topProgressBar').style.width = `${pct}%`;
        document.getElementById('percentText').textContent = `${pct}% Selesai`;
        document.getElementById('navBadgeCount').textContent = `${answeredCount}/${total}`;
      }

      window.goHome = function () {
        document.getElementById('landingView').classList.remove('hidden');
        document.getElementById('surveyView').classList.add('hidden');
        document.getElementById('completionView').classList.add('hidden');
        document.getElementById('topProgressContainer').classList.add('hidden');
        document.getElementById('navDrawerBtn').classList.add('hidden');
        document.getElementById('navDrawerBtn').classList.remove('flex');
        if (Object.keys(responses).length > 0) {
          document.getElementById('resumeBtn').classList.remove('hidden');
        }
      };

      window.startSurvey = function (resume = false) {
        if (!resume) {
          currentIndex = 0;
          submissionId = `RESP-${Date.now()}`;
        } else if (!submissionId) {
          submissionId = `RESP-${Date.now()}`;
        }
        document.getElementById('landingView').classList.add('hidden');
        document.getElementById('completionView').classList.add('hidden');
        document.getElementById('surveyView').classList.remove('hidden');
        document.getElementById('topProgressContainer').classList.remove('hidden');
        document.getElementById('navDrawerBtn').classList.remove('hidden');
        document.getElementById('navDrawerBtn').classList.add('flex');
        renderQuestion('right');
      };

      function renderQuestion(direction = 'right') {
        const q = QUESTIONS[currentIndex];
        const card = document.getElementById('questionCard');
        const content = document.getElementById('questionContent');
        const toast = document.getElementById('validationToast');

        toast.classList.add('hidden');

        document.getElementById('sectionBadge').textContent = q.section;
        document.getElementById('subDomainBadge').textContent = q.subDomain;
        document.getElementById('currentQNum').textContent = currentIndex + 1;
        document.getElementById('prevBtn').disabled = currentIndex === 0;
        document.getElementById('nextBtnText').textContent =
          currentIndex === QUESTIONS.length - 1 ? 'Hantar Soal Selidik' : 'Seterusnya';

        card.classList.remove('animate-slide-in-right', 'animate-slide-in-left');
        void card.offsetWidth;
        card.classList.add(direction === 'right' ? 'animate-slide-in-right' : 'animate-slide-in-left');

        const currentVal = responses[q.id];
        let html = `
          <div class="space-y-3">
            <div class="flex items-center gap-2">
              <span class="px-2.5 py-1 rounded-lg bg-slate-100 text-uthmPurple font-extrabold text-xs border border-slate-200">
                Item ${q.code}
              </span>
              ${q.type === 'likert' ? `
                <span class="text-xs font-medium text-slate-500">
                  Nilaikan tahap kepentingan / Rate the importance
                </span>
              ` : ''}
            </div>

            <h2 class="text-lg sm:text-xl md:text-2xl font-bold text-slate-900 leading-snug">
              ${q.textMs}
            </h2>

            ${q.textEn ? `
              <p class="text-xs sm:text-sm text-slate-500 italic leading-relaxed border-l-2 border-slate-200 pl-3">
                ${q.textEn}
              </p>
            ` : ''}
          </div>
        `;

        if (q.type === 'choice') {
          html += `<div class="grid grid-cols-1 sm:grid-cols-2 gap-3 pt-2">`;
          q.options.forEach((opt) => {
            const isSelected = currentVal === opt.value;
            html += `
              <button type="button" onclick="selectChoiceOption('${opt.value.replace(/'/g, "\\'")}')"
                class="text-left p-4 rounded-2xl border-2 transition-all flex items-center justify-between gap-3 ${
                  isSelected
                    ? 'border-uthmPurple bg-purple-50/80 text-uthmPurple shadow-md'
                    : 'border-slate-200 bg-white hover:border-uthmPurple/40 hover:bg-slate-50 text-slate-800'
                }">
                <div>
                  <div class="font-bold text-sm sm:text-base">${opt.labelMs}</div>
                  <div class="text-xs text-slate-500 mt-0.5">${opt.labelEn}</div>
                </div>
                <div class="w-6 h-6 rounded-full border-2 flex items-center justify-center shrink-0 ${
                  isSelected ? 'border-uthmPurple bg-uthmPurple text-white' : 'border-slate-300'
                }">
                  ${isSelected ? '<svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M5 13l4 4L19 7"/></svg>' : ''}
                </div>
              </button>
            `;
          });
          html += `</div>`;
        } else if (q.type === 'text') {
          html += `
            <div class="pt-2">
              <input type="text" id="textInputField" value="${currentVal ? escapeHtml(currentVal) : ''}"
                oninput="handleTextInput(this.value)"
                onkeydown="if(event.key==='Enter'){ event.preventDefault(); nextQuestion(); }"
                placeholder="${q.placeholder || 'Taip jawapan anda di sini...'}"
                class="w-full px-4 py-4 rounded-2xl border-2 border-slate-200 focus:border-uthmPurple focus:ring-4 focus:ring-uthmPurple/10 outline-none text-sm sm:text-base font-medium text-slate-900 transition" />
              <p class="mt-2 text-xs text-slate-400">Tekan <strong>Enter</strong> atau klik <strong>Seterusnya</strong> selepas mengisi.</p>
            </div>
          `;
        } else if (q.type === 'textarea') {
          html += `
            <div class="pt-2">
              <textarea id="textareaInputField" rows="4"
                oninput="handleTextInput(this.value)"
                placeholder="${q.placeholder || 'Taip cadangan anda di sini...'}"
                class="w-full px-4 py-3.5 rounded-2xl border-2 border-slate-200 focus:border-uthmPurple focus:ring-4 focus:ring-uthmPurple/10 outline-none text-sm sm:text-base text-slate-900 transition resize-none">${currentVal ? escapeHtml(currentVal) : ''}</textarea>
            </div>
          `;
        } else if (q.type === 'likert') {
          html += `<div class="grid grid-cols-1 sm:grid-cols-5 gap-3 pt-2">`;
          LIKERT_SCALE.forEach((s) => {
            const isSelected = Number(currentVal) === s.value;
            html += `
              <button type="button" onclick="selectLikert(${s.value})"
                class="scale-btn ${s.colorClass} ${isSelected ? 'selected' : ''} p-4 sm:p-5 rounded-2xl border-2 flex sm:flex-col items-center justify-between sm:justify-center text-left sm:text-center gap-3 cursor-pointer">
                <div class="flex items-center sm:flex-col gap-3 sm:gap-2">
                  <span class="w-9 h-9 sm:w-11 sm:h-11 rounded-full flex items-center justify-center font-extrabold text-base sm:text-lg shadow-sm ${
                    isSelected ? 'bg-white/25 text-current ring-2 ring-white/60' : `${s.dotColor} ${s.value === 3 ? 'text-uthmPurple' : 'text-white'}`
                  }">
                    ${s.value}
                  </span>
                  <div>
                    <div class="font-extrabold text-xs sm:text-sm leading-tight">${s.labelMs}</div>
                    <div class="text-[11px] opacity-85 mt-0.5 leading-tight">${s.labelEn}</div>
                  </div>
                </div>
                <span class="text-[10px] font-bold uppercase px-2 py-0.5 rounded-md bg-black/5">
                  ${s.abbr}
                </span>
              </button>
            `;
          });
          html += `</div>`;
        }

        content.innerHTML = html;

        if (q.type === 'text') {
          setTimeout(() => document.getElementById('textInputField')?.focus(), 80);
        } else if (q.type === 'textarea') {
          setTimeout(() => document.getElementById('textareaInputField')?.focus(), 80);
        }

        updateProgressUI();
      }

      window.selectChoiceOption = function (val) {
        const q = QUESTIONS[currentIndex];
        responses[q.id] = val;
        renderQuestion('right');

        clearTimeout(autoAdvanceTimer);
        autoAdvanceTimer = setTimeout(() => {
          if (currentIndex < QUESTIONS.length - 1) {
            currentIndex++;
            renderQuestion('right');
          }
        }, 320);
      };

      window.selectLikert = function (score) {
        const q = QUESTIONS[currentIndex];
        responses[q.id] = score;
        renderQuestion('right');

        clearTimeout(autoAdvanceTimer);
        autoAdvanceTimer = setTimeout(() => {
          if (currentIndex < QUESTIONS.length - 1) {
            currentIndex++;
            renderQuestion('right');
          } else {
            showCompletionScreen();
          }
        }, 340);
      };

      window.handleTextInput = function (val) {
        const q = QUESTIONS[currentIndex];
        responses[q.id] = val;
        updateProgressUI();
      };

      window.prevQuestion = function () {
        clearTimeout(autoAdvanceTimer);
        if (currentIndex > 0) {
          currentIndex--;
          renderQuestion('left');
        }
      };

      window.nextQuestion = function () {
        clearTimeout(autoAdvanceTimer);
        const q = QUESTIONS[currentIndex];
        const val = responses[q.id];

        if (q.required && (val === undefined || val === null || String(val).trim() === '')) {
          document.getElementById('validationToast').classList.remove('hidden');
          return;
        }

        if (currentIndex < QUESTIONS.length - 1) {
          currentIndex++;
          renderQuestion('right');
        } else {
          showCompletionScreen();
        }
      };

      function calculatePartStats(partKey) {
        const items = QUESTIONS.filter((q) => q.part === partKey && q.type === 'likert');
        let sum = 0;
        let answered = 0;

        items.forEach((item) => {
          const val = Number(responses[item.id]);
          if (val >= 1 && val <= 5) {
            sum += val;
            answered++;
          }
        });

        const mean = answered > 0 ? (sum / answered).toFixed(2) : '0.00';
        return { answered, total: items.length, mean };
      }

      async function sendResponsesToGoogleSheet(payload) {
        lastSubmissionPayload = payload;
        const statusEl = document.getElementById('cloudSyncStatus');
        const spinnerEl = document.getElementById('cloudSyncSpinner');
        const textEl = document.getElementById('cloudSyncText');
        const retryBtn = document.getElementById('retrySyncBtn');

        if (retryBtn) retryBtn.classList.add('hidden');
        if (statusEl) {
          statusEl.className = 'mt-5 inline-flex items-center gap-2.5 px-5 py-2.5 rounded-2xl bg-slate-100 border border-slate-200 text-xs sm:text-sm font-semibold text-slate-700';
        }
        if (spinnerEl) spinnerEl.classList.remove('hidden');
        if (textEl) textEl.textContent = 'Menghantar jawapan anda ke pangkalan data penyelidikan...';

        const maxAttempts = 3;
        let delayMs = 1000;
        let success = false;
        let serverMessage = '';

        for (let attempt = 1; attempt <= maxAttempts; attempt++) {
          try {
            // Cuba penghantaran dengan pengesahan respons JSON daripada Google Apps Script
            const res = await fetch(GOOGLE_SHEET_WEBAPP_URL, {
              method: 'POST',
              redirect: 'follow',
              headers: { 'Content-Type': 'text/plain;charset=utf-8' },
              body: JSON.stringify(payload),
            });

            if (res.ok) {
              const data = await res.json();
              if (data && data.status === 'success') {
                success = true;
                serverMessage = `Rekod #${data.rowNumber || ''} (${data.respondentId || payload.submissionId})`;
                break;
              } else if (data && data.status === 'error') {
                throw new Error(data.message || 'Ralat pelayan Google Sheet');
              }
            }
            success = true;
            break;
          } catch (err) {
            // Sandaran no-cors jika pelayar menyekat bacaan redirect Google Apps Script
            try {
              await fetch(GOOGLE_SHEET_WEBAPP_URL, {
                method: 'POST',
                mode: 'no-cors',
                headers: { 'Content-Type': 'text/plain;charset=utf-8' },
                body: JSON.stringify(payload),
              });
              success = true;
              break;
            } catch (fallbackErr) {
              if (attempt < maxAttempts) {
                await new Promise((resolve) => setTimeout(resolve, delayMs));
                delayMs *= 2;
              }
            }
          }
        }

        if (spinnerEl) spinnerEl.classList.add('hidden');

        if (success) {
          if (statusEl) {
            statusEl.className = 'mt-5 inline-flex items-center gap-2.5 px-5 py-2.5 rounded-2xl bg-emerald-50 border border-emerald-300 text-xs sm:text-sm font-bold text-emerald-800';
          }
          if (textEl) {
            textEl.textContent = serverMessage
              ? `✅ Berjaya! Jawapan direkodkan ke Google Sheet (${serverMessage}).`
              : '✅ Terima kasih! Semua jawapan anda telah berjaya direkodkan secara automatik.';
          }
          if (retryBtn) retryBtn.classList.remove('hidden');
        } else {
          if (statusEl) {
            statusEl.className = 'mt-5 inline-flex items-center gap-2.5 px-5 py-2.5 rounded-2xl bg-amber-50 border border-amber-300 text-xs sm:text-sm font-semibold text-amber-800';
          }
          if (textEl) {
            textEl.textContent = '⚠️ Gangguan rangkaian dikesan. Sila tekan butang di bawah untuk menghantar semula.';
          }
          if (retryBtn) retryBtn.classList.remove('hidden');
        }
      }

      window.retrySubmitToGoogleSheet = function () {
        if (lastSubmissionPayload) {
          sendResponsesToGoogleSheet(lastSubmissionPayload);
        }
      };

      function showCompletionScreen() {
        document.getElementById('landingView').classList.add('hidden');
        document.getElementById('surveyView').classList.add('hidden');
        document.getElementById('topProgressContainer').classList.add('hidden');
        document.getElementById('completionView').classList.remove('hidden');

        const profileGrid = document.getElementById('summaryProfileGrid');
        profileGrid.innerHTML = `
          <div class="p-3 rounded-xl bg-white border border-slate-200">
            <span class="text-[11px] text-slate-400 block">Jantina / Umur</span>
            <strong class="text-slate-800">${escapeHtml(responses.D1 || '-')} • ${escapeHtml(responses.D2 || '-')}</strong>
          </div>
          <div class="p-3 rounded-xl bg-white border border-slate-200">
            <span class="text-[11px] text-slate-400 block">Pendidikan / Pengalaman</span>
            <strong class="text-slate-800">${escapeHtml(responses.D3 || '-')} • ${escapeHtml(responses.D4 || '-')}</strong>
          </div>
          <div class="p-3 rounded-xl bg-white border border-slate-200">
            <span class="text-[11px] text-slate-400 block">Kolej Vokasional</span>
            <strong class="text-slate-800">${escapeHtml(responses.D6 || '-')}</strong>
          </div>
        `;

        const statsA = calculatePartStats('A');
        const statsB = calculatePartStats('B');
        const statsC = calculatePartStats('C');

        document.getElementById('partACountBadge').textContent = `${statsA.answered}/${statsA.total} item`;
        document.getElementById('partBCountBadge').textContent = `${statsB.answered}/${statsB.total} item`;
        document.getElementById('partCCountBadge').textContent = `${statsC.answered}/${statsC.total} item`;

        if (!submissionId) {
          submissionId = `RESP-${Date.now()}`;
        }

        // Hantar terus semua jawapan ke URL Google Apps Script
        sendResponsesToGoogleSheet({
          submissionId: submissionId,
          uid: 'Portal_Responden_UTHM',
          responses: { ...responses },
          stats: {
            meanA: statsA.mean,
            meanB: statsB.mean,
            meanC: statsC.mean,
          },
        });
      }

      window.reviewAnswers = function () {
        currentIndex = 0;
        startSurvey(true);
      };

      window.resetSurveyConfirm = function () {
        responses = {};
        currentIndex = 0;
        submissionId = null;
        document.getElementById('resumeBtn').classList.add('hidden');
        goHome();
      };

      function renderNavDrawerGrid() {
        const container = document.getElementById('navDrawerGrid');
        const sections = [
          { title: 'Seksyen A: Demografi (6 Item)', filter: (q) => q.section.startsWith('Seksyen A') },
          { title: 'Bahagian A: Elemen Pengetahuan (11 Item)', filter: (q) => q.part === 'A' },
          { title: 'Bahagian B: Elemen Kemahiran (47 Item)', filter: (q) => q.part === 'B' },
          { title: 'Bahagian C: Elemen Sikap dan Nilai (13 Item)', filter: (q) => q.part === 'C' },
        ];

        container.innerHTML = sections
          .map((sec) => {
            const list = QUESTIONS.map((q, idx) => ({ q, idx })).filter((item) => sec.filter(item.q));
            const btns = list
              .map(({ q, idx }) => {
                const answered =
                  responses[q.id] !== undefined &&
                  responses[q.id] !== null &&
                  String(responses[q.id]).trim() !== '';
                const isCurrent = idx === currentIndex;
                return `
                  <button onclick="jumpToQuestion(${idx})"
                    class="h-9 rounded-xl text-xs font-bold border transition flex items-center justify-center ${
                      isCurrent
                        ? 'ring-2 ring-uthmPurple bg-uthmPurple text-white border-uthmPurple'
                        : answered
                        ? 'bg-emerald-50 text-emerald-800 border-emerald-300 hover:bg-emerald-100'
                        : 'bg-slate-50 text-slate-600 border-slate-200 hover:bg-slate-100'
                    }">
                    ${q.code}
                  </button>
                `;
              })
              .join('');

            return `
              <div>
                <h4 class="text-xs font-bold text-slate-700 mb-2">${sec.title}</h4>
                <div class="grid grid-cols-5 sm:grid-cols-8 gap-2">${btns}</div>
              </div>
            `;
          })
          .join('');
      }

      window.jumpToQuestion = function (idx) {
        currentIndex = idx;
        toggleNavDrawer(false);
        renderQuestion('right');
      };

      window.toggleNavDrawer = function (show) {
        const modal = document.getElementById('navDrawerModal');
        if (!modal) return;
        if (show) {
          renderNavDrawerGrid();
          modal.classList.remove('hidden');
          modal.classList.add('flex');
        } else {
          modal.classList.add('hidden');
          modal.classList.remove('flex');
        }
      };

      window.toggleResearcherModal = function (show) {
        const modal = document.getElementById('researcherModal');
        if (!modal) return;
        if (show) {
          modal.classList.remove('hidden');
          modal.classList.add('flex');
        } else {
          modal.classList.add('hidden');
          modal.classList.remove('flex');
        }
      };

      window.finishSurveyEarlyCheck = function () {
        toggleNavDrawer(false);
        showCompletionScreen();
      };

      function escapeHtml(str) {
        return String(str)
          .replace(/&/g, '&amp;')
          .replace(/</g, '&lt;')
          .replace(/>/g, '&gt;')
          .replace(/"/g, '&quot;')
          .replace(/'/g, '&#039;');
      }
    })();
  </script>
</body>
</html>
