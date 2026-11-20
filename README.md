<!DOCTYPE html>
<html lang="ms" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soal Selidik PhD: Kerangka Kemahiran Hijau TVET Elektronik | UTHM</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Plus Jakarta Sans & Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@600;700;800&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                    colors: {
                        emerald: {
                            50: '#ecfdf5',
                            100: '#d1fae5',
                            200: '#a7f3d0',
                            300: '#6ee7b7',
                            400: '#34d399',
                            500: '#10b981',
                            600: '#059669',
                            700: '#047857',
                            800: '#065f46',
                            900: '#064e3b',
                            950: '#022c22',
                        },
                        slate: {
                            850: '#152033',
                            900: '#0f172a',
                            950: '#080d1a',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Corak Litar Elektronik Halus */
        .circuit-bg {
            background-color: #064e3b;
            background-image: radial-gradient(rgba(16, 185, 129, 0.22) 1.5px, transparent 1.5px),
                              radial-gradient(rgba(52, 211, 153, 0.14) 1.5px, #064e3b 1.5px);
            background-size: 36px 36px;
            background-position: 0 0, 18px 18px;
        }

        /* Animasi Peralihan Kad Soalan */
        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(24px); }
            to { opacity: 1; transform: translateX(0); }
        }
        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-24px); }
            to { opacity: 1; transform: translateX(0); }
        }
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(14px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-slide-right { animation: slideInRight 0.28s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
        .animate-slide-left { animation: slideInLeft 0.28s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
        .animate-fade-up { animation: fadeUp 0.32s cubic-bezier(0.16, 1, 0.3, 1) forwards; }

        /* Gaya Pilihan Jawapan Interaktif */
        .option-card {
            transition: all 0.18s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .option-card:hover {
            border-color: #10b981;
            background-color: #f0fdf4;
            transform: translateY(-1px);
        }
        .option-card.selected {
            border-color: #059669;
            background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%);
            box-shadow: 0 8px 20px -4px rgba(5, 150, 105, 0.22);
        }
        .option-card.selected .key-badge {
            background-color: #059669;
            color: #ffffff;
            border-color: #059669;
        }

        /* Ralat Pengesahan */
        @keyframes shakeError {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-6px); }
            40%, 80% { transform: translateX(6px); }
        }
        .shake-error {
            animation: shakeError 0.35s ease-in-out;
            border-color: #ef4444 !important;
        }

        /* Mod Paparan Bahasa */
        body.lang-bm .text-en { display: none !important; }
        body.lang-en .text-bm { display: none !important; }
        body.lang-en .text-en { font-style: normal !important; color: inherit !important; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col justify-between antialiased selection:bg-emerald-200 selection:text-emerald-950">

    <!-- =====================================================================
         BAR ATAS MELEKIT: IDENTITI KAJIAN, KEMAJUAN & PENUKAR BAHASA
    ====================================================================== -->
    <header class="sticky top-0 z-40 bg-white/95 backdrop-blur-md border-b border-slate-200/90 shadow-sm">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 py-2.5 flex items-center justify-between gap-3">
            <!-- Jenama UTHM -->
            <button type="button" onclick="returnToCover()" class="flex items-center gap-2.5 text-left group focus:outline-none">
                <div class="w-9 h-9 rounded-xl bg-emerald-700 group-hover:bg-emerald-600 text-white flex items-center justify-center shadow-sm transition">
                    <i data-lucide="cpu" class="w-5 h-5"></i>
                </div>
                <div>
                    <div class="flex items-center gap-1.5">
                        <span class="text-xs font-extrabold tracking-wider text-emerald-700 uppercase font-display">UTHM</span>
                        <span class="text-[10px] px-1.5 py-0.5 rounded bg-slate-100 text-slate-600 font-semibold">PhD TVET</span>
                    </div>
                    <span class="text-[11px] text-slate-500 font-medium hidden sm:block">Green Skills Electronics Survey</span>
                </div>
            </button>

            <!-- Bar Kemajuan (Dipaparkan semasa menjawab soalan) -->
            <div id="header-progress-wrapper" class="hidden flex-1 max-w-md mx-2">
                <div class="flex items-center justify-between text-[11px] font-semibold text-slate-600 mb-1">
                    <span id="header-q-counter" class="text-slate-800 font-bold">Soalan 1 daripada 90</span>
                    <span id="header-pct-text" class="text-emerald-700 font-bold">0%</span>
                </div>
                <div class="w-full h-2 bg-slate-200 rounded-full overflow-hidden">
                    <div id="header-progress-bar" class="h-full bg-gradient-to-r from-emerald-500 to-teal-600 rounded-full transition-all duration-300" style="width: 0%"></div>
                </div>
            </div>

            <!-- Penukar Bahasa -->
            <div class="flex items-center bg-slate-100 p-1 rounded-xl border border-slate-200 text-xs font-semibold shrink-0">
                <button type="button" onclick="setLanguage('both')" id="btn-lang-both" class="px-2.5 py-1 rounded-lg bg-emerald-600 text-white shadow-sm transition">BM/EN</button>
                <button type="button" onclick="setLanguage('bm')" id="btn-lang-bm" class="px-2.5 py-1 rounded-lg text-slate-600 hover:text-slate-900 transition">BM</button>
                <button type="button" onclick="setLanguage('en')" id="btn-lang-en" class="px-2.5 py-1 rounded-lg text-slate-600 hover:text-slate-900 transition">EN</button>
            </div>
        </div>
    </header>

    <!-- =====================================================================
         KANDUNGAN UTAMA (COVER SCREEN / WIZARD QUESTION / THANK YOU SCREEN)
    ====================================================================== -->
    <main class="flex-1 flex flex-col justify-center py-6 sm:py-10 px-4 sm:px-6">
        <div class="max-w-4xl w-full mx-auto">

            <!-- *****************************************************************
                 1. SKRIN PENGENALAN / COVER SCREEN
            ****************************************************************** -->
            <div id="cover-screen" class="animate-fade-up space-y-6">
                <!-- Banner Tajuk Utama -->
                <div class="circuit-bg rounded-3xl p-6 sm:p-10 text-white shadow-xl border border-emerald-700/60 relative overflow-hidden">
                    <div class="relative z-10 space-y-5">
                        <!-- Lencana Institusi -->
                        <div class="inline-flex items-center gap-3 bg-white/10 backdrop-blur-md border border-white/20 rounded-2xl px-4 py-2">
                            <div class="w-9 h-9 rounded-xl bg-white text-indigo-950 font-extrabold flex flex-col items-center justify-center leading-none shadow-sm">
                                <span class="text-[9px] text-red-600 tracking-tighter">UTHM</span>
                                <i data-lucide="graduation-cap" class="w-4 h-4 text-indigo-950 mt-0.5"></i>
                            </div>
                            <div>
                                <p class="text-xs sm:text-sm font-bold text-emerald-300 uppercase tracking-wide font-display">Universiti Tun Hussein Onn Malaysia</p>
                                <p class="text-[11px] text-slate-200">Fakulti Pendidikan Teknikal & Vokasional (FPTV)</p>
                            </div>
                        </div>

                        <!-- Tajuk Penyelidikan -->
                        <div class="space-y-2.5">
                            <h1 class="text-xl sm:text-3xl font-extrabold font-display leading-snug tracking-tight text-white text-bm">
                                PEMBANGUNAN KERANGKA KEMAHIRAN HIJAU UNTUK KURIKULUM PROGRAM TEKNOLOGI ELEKTRONIK TVET: DALAM MEMENUHI KEPERLUAN EKONOMI HIJAU
                            </h1>
                            <p class="text-sm sm:text-lg font-medium text-emerald-200 leading-relaxed text-en">
                                DEVELOPMENT OF A GREEN SKILLS FRAMEWORK FOR THE TVET ELECTRONIC TECHNOLOGY PROGRAMME CURRICULUM: MEETING THE NEEDS OF THE GREEN ECONOMY
                            </p>
                        </div>

                        <!-- Butang Mula Pantas -->
                        <div class="pt-2 flex flex-wrap items-center gap-3">
                            <button type="button" onclick="startSurvey(false)" id="btn-start-survey" class="px-7 py-4 rounded-2xl bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-extrabold text-sm sm:text-base shadow-lg shadow-emerald-950/50 flex items-center gap-2.5 transition transform hover:-translate-y-0.5 cursor-pointer">
                                <span>Mula Menjawab / Start Survey</span>
                                <i data-lucide="arrow-right" class="w-5 h-5"></i>
                            </button>
                            <button type="button" onclick="startSurvey(true)" id="btn-resume-survey" class="hidden px-6 py-4 rounded-2xl bg-white/15 hover:bg-white/25 text-white border border-white/30 font-bold text-sm sm:text-base flex items-center gap-2 transition cursor-pointer">
                                <i data-lucide="play-circle" class="w-5 h-5 text-emerald-300"></i>
                                <span id="resume-btn-label">Sambung Jawapan / Resume</span>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Kad Surat Permohonan, Definisi & Maklumat Penyelidik -->
                <div class="bg-white rounded-3xl shadow-md border border-slate-200/90 p-6 sm:p-8 space-y-6">
                    <!-- Teks Pengenalan BM -->
                    <div class="space-y-3 text-sm sm:text-[15px] leading-relaxed text-slate-700 text-bm">
                        <p class="font-bold text-slate-900 text-base">Kepada Tuan/Puan yang dihormati,</p>
                        <p>
                            Saya, <strong>Adib Farhan bin Zaime</strong> merupakan pelajar separuh masa bagi program <strong>Doktor Falsafah Pendidikan Teknik dan Vokasional di Universiti Tun Hussein Onn Malaysia</strong>. Di sini, saya memohon kerjasama dan sokongan daripada pihak tuan/puan untuk saya menjalankan kajian penyelidikan ini. Tujuan utama kajian ini untuk memperoleh ilmu pengetahuan dalam bidang yang dikaji. Soal selidik ini memerlukan sedikit masa tuan/puan untuk dijawab. Namun demikian, kerjasama dan maklum balas daripada tuan/puan amat penting bagi membantu saya dalam menyelesaikan tesis PhD. Oleh itu, saya amat berterima kasih atas kerjasama tuan/puan dalam membantu saya menjawab soal selidik ini.
                        </p>
                        <p>
                            Objektif kajian ini adalah untuk <strong>meneroka, membangunkan, dan mengesahkan kerangka kemahiran hijau sebagai nilai tambah untuk kurikulum Program Teknologi Elektronik TVET</strong>. Penyelidikan ini telah bermula dengan menggunakan teknik Delphi. Teknik ini digunakan bagi meneroka elemen-elemen kemahiran hijau dalam kalangan pakar. Menerusi teknik Delphi, komponen yang telah dikenal pasti oleh pakar adalah penting untuk diterapkan dalam kerangka kurikulum Program Teknologi Elektronik TVET. Oleh itu, menerusi soal selidik ini, saya ingin mendapatkan kepakaran anda sebagai pendidik TVET dalam menentukan sejauh mana elemen-elemen ini penting untuk dimasukkan dalam kurikulum latihan Program Teknologi Elektronik TVET di Kolej Vokasional Malaysia. Segala jawapan yang diberikan adalah <strong>sulit</strong> dan maklumat yang dikumpulkan digunakan bagi <strong>tujuan akademik</strong>. Soal selidik ini mengandungi dua seksyen dan tiga bahagian.
                        </p>
                    </div>

                    <!-- Teks Pengenalan EN -->
                    <div class="space-y-3 text-sm leading-relaxed text-slate-600 italic border-t border-slate-100 pt-5 text-en">
                        <p class="font-bold text-slate-800 not-italic">Dear Sir/Madam,</p>
                        <p>
                            I am <strong>Adib Farhan bin Zaime</strong>, a part-time student candidate for <strong>Doctor of Philosophy (PhD) in Technical and Vocational Education at Universiti Tun Hussein Onn Malaysia</strong>. I am writing to seek your kind cooperation and support in conducting this research study. The main objective of this study is to gain valuable knowledge and insights in the field under research. While completing this questionnaire will take a few moments of your time, your response is crucial to the completion of my PhD. I truly appreciate your time and assistance in answering this questionnaire.
                        </p>
                        <p>
                            The objective of this study is to <strong>explore, develop, and validate a green skills framework as an added value for the TVET Electronic Technology Programme curriculum</strong>. This research commenced by using the Delphi technique to explore green skills elements among experts. Through this technique, the components identified by experts were deemed essential to be integrated into the TVET Electronic Technology Programme curriculum framework. Therefore, through this questionnaire, I would like to seek your expertise as a TVET educator to determine the extent to which these elements are important to be included in the training curriculum of the TVET Electronic Technology Programme at Malaysian Vocational Colleges. All responses provided will be kept <strong>strictly confidential</strong>, and the data collected will be used <strong>solely for academic purposes</strong>. This questionnaire consists of two sections and three parts.
                        </p>
                    </div>

                    <!-- Definisi Kemahiran Hijau -->
                    <div class="bg-emerald-50/90 border border-emerald-200 rounded-2xl p-4 sm:p-5 flex items-start gap-3.5">
                        <div class="w-9 h-9 rounded-xl bg-emerald-600 text-white flex items-center justify-center shrink-0 mt-0.5">
                            <i data-lucide="leaf" class="w-5 h-5"></i>
                        </div>
                        <div class="space-y-1.5 text-sm">
                            <h3 class="font-bold text-emerald-950 uppercase tracking-wide text-xs font-display">Definisi Kemahiran Hijau / Definition of Green Skills</h3>
                            <p class="text-emerald-900 text-bm">
                                <strong>Kemahiran hijau</strong> adalah satu set kemahiran yang merangkumi kemahiran teknikal, pengetahuan, nilai, dan sikap yang diperlukan dalam pekerjaan hijau untuk menyokong ekonomi, sosial, dan alam sekitar yang mampan melalui aktiviti seperti industri, perniagaan, dan komuniti.
                            </p>
                            <p class="text-emerald-800 italic text-xs sm:text-sm text-en">
                                <strong>Green skills</strong> refer to a set of skills encompassing technical skills, knowledge, values, and attitudes required in green jobs to support economic, social, and environmental sustainability through activities across industries, businesses, and communities.
                            </p>
                        </div>
                    </div>

                    <!-- Maklumat Perhubungan -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-1">
                        <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200/90 flex items-start gap-3">
                            <div class="w-10 h-10 rounded-full bg-slate-800 text-white font-bold flex items-center justify-center shrink-0 text-sm">AF</div>
                            <div class="text-xs sm:text-sm">
                                <span class="text-[11px] font-bold uppercase tracking-wider text-emerald-700">1) Penyelidik / Researcher</span>
                                <p class="font-bold text-slate-900">Adib Farhan bin Zaime</p>
                                <p class="text-slate-600 mt-1 flex items-center gap-1.5"><i data-lucide="phone" class="w-3.5 h-3.5 text-emerald-600"></i> +60 13 650 2508</p>
                                <p class="text-slate-600 flex items-center gap-1.5"><i data-lucide="mail" class="w-3.5 h-3.5 text-emerald-600"></i> adibfarhanzaime@gmail.com</p>
                            </div>
                        </div>
                        <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200/90 flex items-start gap-3">
                            <div class="w-10 h-10 rounded-full bg-indigo-900 text-white font-bold flex items-center justify-center shrink-0 text-sm">LC</div>
                            <div class="text-xs sm:text-sm">
                                <span class="text-[11px] font-bold uppercase tracking-wider text-indigo-700">2) Penyelia / Supervisor</span>
                                <p class="font-bold text-slate-900">Prof. Ts. Dr. Lai Chee Sern</p>
                                <p class="text-slate-500 text-xs">Pensyarah Kanan / Senior Lecturer, FPTV UTHM</p>
                                <p class="text-slate-600 mt-1 flex items-center gap-1.5"><i data-lucide="phone" class="w-3.5 h-3.5 text-emerald-600"></i> +60 12 576 8327</p>
                                <p class="text-slate-600 flex items-center gap-1.5"><i data-lucide="mail" class="w-3.5 h-3.5 text-emerald-600"></i> lcsern@uthm.edu.my</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- *****************************************************************
                 2. PAPARAN SATU SOALAN PADA SATU MASA (WIZARD CARD VIEW)
            ****************************************************************** -->
            <div id="wizard-screen" class="hidden space-y-4">
                <!-- Bar Kawalan Pantas Atas Kad: Lompat Bahagian & Togol Auto-Advance -->
                <div class="flex flex-wrap items-center justify-between gap-2 bg-white px-4 py-2.5 rounded-2xl border border-slate-200 shadow-sm text-xs">
                    <!-- Pemilih Bahagian -->
                    <div class="flex items-center gap-2">
                        <i data-lucide="layers" class="w-4 h-4 text-emerald-600 shrink-0"></i>
                        <select id="section-jumper" onchange="jumpToSection(this.value)" class="bg-slate-50 border border-slate-200 rounded-lg px-2.5 py-1.5 font-semibold text-slate-700 focus:border-emerald-600 outline-none cursor-pointer max-w-[210px] sm:max-w-xs">
                            <option value="0">Seksyen A: Demografi (1–6)</option>
                            <option value="6">Seksyen B • Bhg A: Pengetahuan (7–20)</option>
                            <option value="20">Seksyen B • Bhg B: Kemahiran (21–76)</option>
                            <option value="76">Seksyen B • Bhg C: Sikap & Nilai (77–90)</option>
                        </select>
                    </div>

                    <!-- Togol Auto-Terus -->
                    <label class="inline-flex items-center gap-2 cursor-pointer select-none">
                        <input type="checkbox" id="auto-advance-toggle" checked class="sr-only peer">
                        <div class="w-9 h-5 bg-slate-200 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-slate-300 after:border after:rounded-full after:h-4 after:w-4 after:transition-all peer-checked:bg-emerald-600 relative"></div>
                        <span class="font-semibold text-slate-600">Auto-terus / <span class="italic font-normal">Auto-next</span></span>
                    </label>
                </div>

                <!-- KAD SOALAN TUNGGAL (SINGLE QUESTION FOCUS CARD) -->
                <div id="question-card" class="bg-white rounded-3xl shadow-xl border border-slate-200/90 overflow-hidden">
                    <!-- Header Seksyen & Sub-domain -->
                    <div class="bg-slate-900 text-white px-6 sm:px-8 py-4 border-b border-slate-800">
                        <div class="flex flex-wrap items-center justify-between gap-2">
                            <span id="q-section-badge" class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-emerald-500/20 border border-emerald-400/30 text-emerald-300 text-xs font-bold uppercase tracking-wider">
                                Seksyen A: Demografi
                            </span>
                            <span id="q-code-badge" class="text-xs font-mono text-slate-400 bg-slate-800 px-2.5 py-1 rounded-lg">
                                Item D1
                            </span>
                        </div>
                        <div id="q-construct-box" class="hidden mt-3 pt-3 border-t border-slate-800/90">
                            <p id="q-construct-bm" class="text-xs sm:text-sm font-bold text-emerald-300 text-bm"></p>
                            <p id="q-construct-en" class="text-[11px] sm:text-xs text-slate-300 italic text-en"></p>
                        </div>
                    </div>

                    <!-- Badan Soalan -->
                    <div class="p-6 sm:p-9 space-y-6">
                        <!-- Arahan Ringkas Kontekstual -->
                        <p id="q-instruction" class="text-xs text-slate-500 bg-slate-50 border border-slate-200/80 rounded-xl px-3.5 py-2 leading-relaxed"></p>

                        <!-- Teks Soalan Utama -->
                        <div class="space-y-2">
                            <div class="flex items-start gap-3">
                                <span id="q-number-pill" class="inline-flex items-center justify-center px-3 py-1 rounded-xl bg-emerald-700 text-white font-extrabold text-sm sm:text-base shrink-0 mt-0.5 shadow-sm">
                                    1
                                </span>
                                <div class="space-y-1.5">
                                    <h2 id="q-text-bm" class="text-lg sm:text-2xl font-bold text-slate-900 leading-snug font-display text-bm"></h2>
                                    <p id="q-text-en" class="text-sm sm:text-base text-slate-500 italic leading-relaxed text-en"></p>
                                </div>
                            </div>
                        </div>

                        <!-- Kawasan Input / Pilihan Jawapan Dinamik -->
                        <div id="q-input-area" class="pt-1"></div>

                        <!-- Petunjuk Pintasan Papan Kekunci -->
                        <div id="keyboard-hint" class="hidden sm:flex items-center justify-center gap-4 text-[11px] text-slate-400 pt-2">
                            <span><kbd class="px-1.5 py-0.5 bg-slate-100 border border-slate-300 rounded text-slate-600 font-mono">1</kbd>–<kbd class="px-1.5 py-0.5 bg-slate-100 border border-slate-300 rounded text-slate-600 font-mono">5</kbd> Pilih Skala</span>
                            <span><kbd class="px-1.5 py-0.5 bg-slate-100 border border-slate-300 rounded text-slate-600 font-mono">Enter</kbd> Seterusnya</span>
                            <span><kbd class="px-1.5 py-0.5 bg-slate-100 border border-slate-300 rounded text-slate-600 font-mono">←</kbd> <kbd class="px-1.5 py-0.5 bg-slate-100 border border-slate-300 rounded text-slate-600 font-mono">→</kbd> Navigasi</span>
                        </div>
                    </div>

                    <!-- Footer Navigasi Kad -->
                    <div class="bg-slate-50 px-6 sm:px-8 py-4 border-t border-slate-200 flex items-center justify-between gap-3">
                        <button type="button" onclick="prevQuestion()" id="btn-prev" class="px-5 py-3 rounded-xl bg-white hover:bg-slate-100 text-slate-700 border border-slate-300 font-bold text-sm flex items-center gap-2 transition cursor-pointer">
                            <i data-lucide="arrow-left" class="w-4 h-4"></i>
                            <span>Sebelum / <span class="italic font-normal">Prev</span></span>
                        </button>

                        <button type="button" onclick="nextQuestion()" id="btn-next" class="px-6 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-sm shadow-md shadow-emerald-600/20 flex items-center gap-2 transition cursor-pointer">
                            <span id="btn-next-label">Seterusnya / <span class="italic font-normal">Next</span></span>
                            <i data-lucide="arrow-right" class="w-4 h-4"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- *****************************************************************
                 3. SKRIN TAMAT / TERIMA KASIH (THANK YOU SCREEN)
            ****************************************************************** -->
            <div id="thank-you-screen" class="hidden animate-fade-up bg-white rounded-3xl shadow-xl border border-emerald-200 p-8 sm:p-12 text-center space-y-6">
                <div class="w-20 h-20 rounded-full bg-emerald-100 text-emerald-600 flex items-center justify-center mx-auto shadow-inner">
                    <i data-lucide="check-circle-2" class="w-11 h-11"></i>
                </div>
                <div class="space-y-2 max-w-2xl mx-auto">
                    <span class="inline-block px-3.5 py-1 rounded-full bg-emerald-100 text-emerald-800 text-xs font-bold uppercase tracking-wider">Penghantaran Selesai / Submission Completed</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold text-slate-900 font-display">Terima kasih atas kesudian tuan/puan dalam menjawab soal selidik ini.</h2>
                    <p class="text-base font-medium text-emerald-700 italic">Thank you for taking the time to complete this survey.</p>
                    <p class="text-sm text-slate-600 pt-2 leading-relaxed">
                        Maklum balas anda amat berharga dalam menyokong pembangunan <strong>Kerangka Kemahiran Hijau untuk Kurikulum Program Teknologi Elektronik TVET</strong> di Universiti Tun Hussein Onn Malaysia (UTHM).
                    </p>
                </div>

                <div id="submission-status-box" class="max-w-lg mx-auto p-4 rounded-2xl bg-slate-50 border border-slate-200 text-xs sm:text-sm text-slate-700"></div>

                <div class="flex flex-wrap items-center justify-center gap-3 pt-2">
                    <button type="button" onclick="downloadReceiptCSV()" class="px-5 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-sm shadow flex items-center gap-2 transition cursor-pointer">
                        <i data-lucide="download" class="w-4 h-4"></i>
                        <span>Muat Turun Salinan Jawapan (CSV)</span>
                    </button>
                    <button type="button" onclick="resetAndStartNew()" class="px-5 py-3 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold text-sm flex items-center gap-2 transition cursor-pointer">
                        <i data-lucide="rotate-ccw" class="w-4 h-4"></i>
                        <span>Hantar Jawapan Baharu / Submit Another</span>
                    </button>
                </div>
            </div>

        </div>
    </main>

    <!-- =====================================================================
         FOOTER & AKSES SETUP GOOGLE SHEETS / GITHUB PAGES
    ====================================================================== -->
    <footer class="bg-slate-900 text-slate-400 border-t border-slate-800 py-6 px-4 sm:px-6">
        <div class="max-w-4xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4 text-xs">
            <div class="text-center sm:text-left">
                <p class="font-semibold text-slate-200">© 2026 Penyelidikan PhD Pendidikan Teknik dan Vokasional • UTHM</p>
                <p class="mt-0.5 text-slate-400">Adib Farhan bin Zaime & Prof. Ts. Dr. Lai Chee Sern</p>
            </div>
            <button type="button" onclick="openSetupModal()" class="px-4 py-2 rounded-xl bg-slate-800 hover:bg-slate-700 text-emerald-400 border border-slate-700 font-semibold flex items-center gap-2 transition cursor-pointer">
                <i data-lucide="settings" class="w-4 h-4"></i>
                <span>Setup Google Sheets & GitHub</span>
            </button>
        </div>
    </footer>

    <!-- =====================================================================
         NOTIFIKASI TOAST (PENGGANTI ALERT)
    ====================================================================== -->
    <div id="toast-box" class="fixed bottom-5 right-5 z-50 max-w-sm bg-slate-900 text-white px-4 py-3.5 rounded-2xl shadow-2xl border border-slate-700 flex items-start gap-3 transform translate-y-28 opacity-0 transition-all duration-300 pointer-events-none">
        <i id="toast-icon" data-lucide="alert-circle" class="w-5 h-5 text-amber-400 shrink-0 mt-0.5"></i>
        <div class="text-xs sm:text-sm">
            <p id="toast-title" class="font-bold">Perhatian</p>
            <p id="toast-msg" class="text-slate-300 mt-0.5"></p>
        </div>
    </div>

    <!-- =====================================================================
         MODAL SETUP GOOGLE SHEETS & EKSPORT FAIL GITHUB PAGES
    ====================================================================== -->
    <div id="setup-modal" class="fixed inset-0 z-50 hidden bg-slate-950/75 backdrop-blur-sm flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-white rounded-3xl max-w-3xl w-full shadow-2xl border border-slate-200 overflow-hidden my-8">
            <div class="bg-slate-900 text-white px-6 py-4 flex items-center justify-between">
                <div class="flex items-center gap-2.5">
                    <i data-lucide="sheet" class="w-5 h-5 text-emerald-400"></i>
                    <h3 class="font-bold text-base sm:text-lg font-display">Integrasi Automatik Google Sheets & GitHub Pages</h3>
                </div>
                <button type="button" onclick="closeSetupModal()" class="text-slate-400 hover:text-white p-1 rounded-lg">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>

            <div class="p-6 space-y-5 max-h-[80vh] overflow-y-auto text-sm text-slate-700">
                <!-- Status URL -->
                <div class="bg-emerald-50 border border-emerald-200 rounded-2xl p-4">
                    <p class="font-bold text-emerald-950 text-xs uppercase tracking-wider mb-1">Status Sambungan Google Sheet:</p>
                    <p id="setup-url-status" class="text-xs font-mono text-emerald-800 break-all"></p>
                </div>

                <!-- Input URL & Muat Turun Fail GitHub -->
                <div class="space-y-2.5">
                    <label class="block font-bold text-slate-900">Langkah 1: Tampal URL Google Apps Script Web App Anda</label>
                    <div class="flex flex-col sm:flex-row gap-2">
                        <input type="url" id="setup-url-input" placeholder="https://script.google.com/macros/s/AKfycb.../exec"
                            class="flex-1 px-3.5 py-2.5 rounded-xl border border-slate-300 text-xs font-mono focus:border-emerald-600 outline-none">
                        <button type="button" onclick="saveScriptUrl()" class="px-4 py-2.5 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-xs shrink-0 transition cursor-pointer">
                            Simpan & Aktifkan
                        </button>
                    </div>
                    <div class="pt-1 flex flex-wrap items-center gap-2">
                        <button type="button" onclick="downloadConfiguredHTML()" class="px-4 py-2.5 rounded-xl bg-slate-900 hover:bg-slate-800 text-emerald-300 font-bold text-xs flex items-center gap-2 transition cursor-pointer">
                            <i data-lucide="file-code" class="w-4 h-4"></i>
                            <span>Muat Turun Fail index.html Sedia GitHub (Dengan URL Terbina)</span>
                        </button>
                    </div>
                </div>

                <!-- Kod Google Apps Script -->
                <div class="space-y-2">
                    <div class="flex items-center justify-between">
                        <label class="font-bold text-slate-900">Langkah 2: Salin Kod Google Apps Script ke Google Sheet Anda</label>
                        <button type="button" onclick="copyAppsScript()" class="px-3 py-1.5 rounded-lg bg-emerald-100 hover:bg-emerald-200 text-emerald-800 font-bold text-xs flex items-center gap-1.5 transition cursor-pointer">
                            <i data-lucide="copy" class="w-3.5 h-3.5"></i>
                            <span>Salin Kod</span>
                        </button>
                    </div>
                    <pre id="apps-script-snippet" class="bg-slate-900 text-emerald-300 p-4 rounded-2xl text-xs font-mono overflow-x-auto leading-relaxed">function doPost(e) {
  var lock = LockService.getScriptLock();
  lock.tryLock(10000);
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var data = JSON.parse(e.postData.contents);
    var headers = Object.keys(data);
    
    // Bina baris tajuk secara automatik pada penghantaran pertama
    if (sheet.getLastRow() === 0) {
      sheet.appendRow(headers);
      sheet.getRange(1, 1, 1, headers.length)
           .setFontWeight("bold")
           .setBackground("#d1fae5");
    } else {
      headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getValues()[0];
    }
    
    var row = headers.map(function(h) {
      return data[h] !== undefined ? data[h] : "";
    });
    
    sheet.appendRow(row);
    
    return ContentService
      .createTextOutput(JSON.stringify({ "result": "success" }))
      .setMimeType(ContentService.MimeType.JSON);
  } catch (err) {
    return ContentService
      .createTextOutput(JSON.stringify({ "result": "error", "message": err.toString() }))
      .setMimeType(ContentService.MimeType.JSON);
  } finally {
    lock.releaseLock();
  }
}</pre>
                </div>

                <!-- Arahan Ringkas -->
                <div class="bg-slate-50 border border-slate-200 rounded-2xl p-4 space-y-1.5 text-xs text-slate-600">
                    <p class="font-bold text-slate-800">Cara Deploy di Google Sheets & GitHub:</p>
                    <p>1. Buka <strong>sheets.new</strong> &rarr; klik <strong>Extensions &gt; Apps Script</strong> &rarr; tampal kod di atas &rarr; klik <strong>Deploy &gt; New deployment &gt; Web app</strong> (Execute as: <em>Me</em>, Who has access: <em>Anyone</em>).</p>
                    <p>2. Salin Web App URL tersebut ke kotak Langkah 1 di atas, kemudian klik <strong>Muat Turun Fail index.html Sedia GitHub</strong>.</p>
                    <p>3. Muat naik fail <code class="bg-slate-200 px-1 rounded">index.html</code> ke repositori GitHub anda dan aktifkan <strong>Settings &gt; Pages</strong>.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- =====================================================================
         SKRIP UTAMA: STRUKTUR SEMUA 90 ITEM SOALAN, FLOW SATU-PERSATU & SHEETS
    ====================================================================== -->
    <script>
        // ===================================================================
        // KONFIGURASI URL GOOGLE APPS SCRIPT (GANTIKAN DENGAN URL WEB APP ANDA)
        // ===================================================================
        const DEFAULT_SCRIPT_URL = "YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL";
        let SCRIPT_URL = localStorage.getItem('uthm_gs_script_url') || DEFAULT_SCRIPT_URL;

        // ===================================================================
        // SKALA LIKERT 1 - 5
        // ===================================================================
        const LIKERT_SCALE = [
            { val: "1", code: "Stp", bm: "Sangat tidak penting", en: "Not at all important" },
            { val: "2", code: "Tp", bm: "Tidak penting", en: "Slightly important" },
            { val: "3", code: "Hp", bm: "Hampir penting", en: "Somewhat important" },
            { val: "4", code: "P", bm: "Penting", en: "Important" },
            { val: "5", code: "Sp", bm: "Sangat penting", en: "Strongly important" }
        ];

        // ===================================================================
        // SENARAI LENGKAP SEMUA SOALAN (SATU PERSATU MENGIKUT DOKUMEN ASAL)
        // ===================================================================
        const QUESTIONS = [
            // --- SEKSYEN A: DEMOGRAFI (6 SOALAN) ---
            {
                id: "D1",
                type: "radio",
                required: true,
                sectionBadge: "Seksyen A: Demografi / Section A: Demographics",
                instruction: "Arahan: Sila pilih pada ruangan yang berkenaan. / Instruction: Please select the appropriate option.",
                no: "1",
                bm: "Jantina",
                en: "Gender",
                options: [
                    { value: "Lelaki / Male", bm: "Lelaki", en: "Male" },
                    { value: "Perempuan / Female", bm: "Perempuan", en: "Female" }
                ]
            },
            {
                id: "D2",
                type: "radio",
                required: true,
                sectionBadge: "Seksyen A: Demografi / Section A: Demographics",
                instruction: "Arahan: Sila pilih kumpulan umur anda. / Instruction: Please select your age group.",
                no: "2",
                bm: "Umur",
                en: "Age",
                options: [
                    { value: "23-32 tahun", bm: "23-32 tahun", en: "23-32 years old" },
                    { value: "33-42 tahun", bm: "33-42 tahun", en: "33-42 years old" },
                    { value: "43-52 tahun", bm: "43-52 tahun", en: "43-52 years old" },
                    { value: "53 tahun & ke atas", bm: "53 tahun & ke atas", en: "53 years old & above" }
                ]
            },
            {
                id: "D3",
                type: "radio",
                required: true,
                sectionBadge: "Seksyen A: Demografi / Section A: Demographics",
                instruction: "Arahan: Sila pilih tahap pendidikan tertinggi anda. / Instruction: Please select your highest education level.",
                no: "3",
                bm: "Pendidikan",
                en: "Education level",
                options: [
                    { value: "Diploma / Diploma Kemahiran Malaysia", bm: "Diploma / Diploma Kemahiran Malaysia", en: "Diploma / Malaysian Skills Diploma" },
                    { value: "Diploma Lanjutan Kemahiran Malaysia", bm: "Diploma Lanjutan Kemahiran Malaysia", en: "Malaysian Skills Advanced Diploma" },
                    { value: "Sarjana Muda / Bachelor's Degree", bm: "Sarjana Muda", en: "Bachelor’s Degree" },
                    { value: "Sarjana / Master's Degree", bm: "Sarjana", en: "Master’s Degree" },
                    { value: "Doktor Falsafah / PhD", bm: "Doktor Falsafah", en: "Doctor of Philosophy (PhD)" }
                ]
            },
            {
                id: "D4",
                type: "radio",
                required: true,
                sectionBadge: "Seksyen A: Demografi / Section A: Demographics",
                instruction: "Arahan: Sila pilih tempoh pengalaman mengajar anda. / Instruction: Please select your teaching experience.",
                no: "4",
                bm: "Pengalaman Mengajar",
                en: "Teaching Experience",
                options: [
                    { value: "0-5 tahun", bm: "0-5 tahun", en: "0-5 years" },
                    { value: "6-10 tahun", bm: "6-10 tahun", en: "6-10 years" },
                    { value: "11 tahun & ke atas", bm: "11 tahun & ke atas", en: "11 years & above" }
                ]
            },
            {
                id: "D5",
                type: "text",
                required: true,
                sectionBadge: "Seksyen A: Demografi / Section A: Demographics",
                instruction: "Arahan: Sila nyatakan subjek atau modul utama yang anda ajar. / Instruction: Please state the main subjects or modules you teach.",
                no: "5",
                bm: "Subjek atau Modul Utama yang Diajar",
                en: "Main Subjects or Modules Taught",
                placeholder: "Contoh: Teknologi Elektronik, Sistem Digital, Mikropengawal..."
            },
            {
                id: "D6",
                type: "text",
                required: true,
                sectionBadge: "Seksyen A: Demografi / Section A: Demographics",
                instruction: "Arahan: Sila nyatakan nama Kolej Vokasional tempat anda bertugas. / Instruction: Please state your Vocational College.",
                no: "6",
                bm: "Kolej Vokasional",
                en: "Vocational College",
                placeholder: "Contoh: Kolej Vokasional Batu Pahat / Kolej Vokasional Sungai Buloh..."
            },

            // --- SEKSYEN B - BAHAGIAN A: ELEMEN PENGETAHUAN (13 LIKERT + 1 TERBUKA) ---
            // Konstruk 1.0
            { id: "BA_1_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.0", bm: "Pengetahuan Teknologi Hijau Elektronik", en: "Knowledge of Green Electronic Technology" },
            { id: "BA_1_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.1", bm: "Pengetahuan tentang teknologi hijau dalam bidang elektronik (seperti sistem solar fotovolta, penyongsang, dan pengurusan bateri).", en: "Knowledge of green technology in the electronics field (such as solar photovoltaic systems, inverters, and battery management)." },
            { id: "BA_1_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.2", bm: "Pengetahuan tentang pembangunan dan reka bentuk produk teknologi hijau dalam bidang elektronik.", en: "Knowledge of green technology product development and design in electronics." },
            { id: "BA_1_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.3", bm: "Pengetahuan tentang aplikasi produk teknologi hijau dalam bidang elektronik (seperti ESP32, dan papan litar PCB bebas plumbum).", en: "Knowledge of the application of green technology products in the field of electronics (such as ESP32 and lead-free PCBs)." },
            { id: "BA_1_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.4", bm: "Pengetahuan tentang penyelenggaraan dan ujian kualiti bagi produk teknologi hijau elektronik.", en: "Knowledge of maintenance and testing for green electronic products." },
            { id: "BA_1_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.5", bm: "Pengetahuan tentang penggunaan peralatan pengujian dan pengukuran teknologi hijau dalam bidang elektronik.", en: "Knowledge of using green technology testing and measurement equipment in electronics." },
            { id: "BA_1_6", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "1.0 Pengetahuan Teknologi Hijau Elektronik", constructEN: "Knowledge of Green Electronic Technology", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.6", bm: "Pengetahuan tentang sistem dan seni bina teknologi hijau industri yang diguna pakai dalam bidang elektronik.", en: "Knowledge of industry-applied green technology systems and architecture in electronics." },
            // Konstruk 2.0
            { id: "BA_2_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan", constructEN: "Knowledge of Electronic Waste (E-Waste) and Waste Material Management", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.0", bm: "Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan", en: "Knowledge of Electronic Waste (E-Waste) and Waste Material Management" },
            { id: "BA_2_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan", constructEN: "Knowledge of Electronic Waste (E-Waste) and Waste Material Management", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.1", bm: "Pengetahuan tentang pengurusan dan sifat bahan berbahaya dalam sisa elektronik (seperti pateri plumbum, kadmium, dan elektrolit bateri).", en: "Knowledge of management and characteristics of hazardous materials in e-waste (such as lead solder, cadmium, and battery electrolytes)." },
            { id: "BA_2_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan", constructEN: "Knowledge of Electronic Waste (E-Waste) and Waste Material Management", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.2", bm: "Pengetahuan tentang kaedah pelupusan sisa pepejal dan komponen elektronik terpakai secara selamat.", en: "Knowledge of safe disposal methods for solid waste and used electronic components." },
            { id: "BA_2_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan", constructEN: "Knowledge of Electronic Waste (E-Waste) and Waste Material Management", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.3", bm: "Pengetahuan tentang aplikasi prinsip 5R (reduce, reuse, recycle, recover & refuse) dalam pengurusan bahan bengkel elektronik.", en: "Knowledge of applying 5R principles (reduce, reuse, recycle, recover & refuse) in managing electronics workshop materials." },
            { id: "BA_2_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian A: Elemen Pengetahuan", constructBM: "2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan", constructEN: "Knowledge of Electronic Waste (E-Waste) and Waste Material Management", instruction: "Nilaikan tahap kepentingan elemen pengetahuan berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.4", bm: "Pengetahuan tentang pengasingan sisa bahan buangan dan komponen elektronik yang rosak.", en: "Knowledge of segregation of waste materials and defective electronic components." },
            // Soalan Terbuka Bahagian A
            { id: "BA_OPEN", type: "textarea", required: false, sectionBadge: "Seksyen B • Bahagian A: Soalan Terbuka", instruction: "Soalan Terbuka (Pilihan / Optional): Anda boleh mengosongkan ruangan ini jika tiada cadangan tambahan.", no: "A+", bm: "Apakah elemen pengetahuan kemahiran hijau lain yang penting tetapi tidak tersenarai di atas?", en: "What other green skills knowledge elements are important but not listed above?", placeholder: "Nyatakan cadangan elemen pengetahuan tambahan di sini..." },

            // --- SEKSYEN B - BAHAGIAN B: ELEMEN KEMAHIRAN (55 LIKERT + 1 TERBUKA) ---
            // Konstruk 1.0
            { id: "BB_1_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "1.0 Kemahiran Pengurusan Sisa Buangan Elektronik", constructEN: "Electronic Waste (E-Waste) Management Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.0", bm: "Kemahiran Pengurusan Sisa Buangan Elektronik", en: "Electronic Waste (E-Waste) Management Skills" },
            { id: "BB_1_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "1.0 Kemahiran Pengurusan Sisa Buangan Elektronik", constructEN: "Electronic Waste (E-Waste) Management Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.1", bm: "Kemahiran mengurangkan pembaziran bahan semasa proses pematerian dan pembuatan papan litar bercetak (PCB).", en: "Skills in reducing material waste during soldering and PCB fabrication/assembly." },
            { id: "BB_1_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "1.0 Kemahiran Pengurusan Sisa Buangan Elektronik", constructEN: "Electronic Waste (E-Waste) Management Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.2", bm: "Kemahiran menggunakan semula komponen elektronik yang masih berfungsi.", en: "Skill in reusing functional electronic components." },
            { id: "BB_1_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "1.0 Kemahiran Pengurusan Sisa Buangan Elektronik", constructEN: "Electronic Waste (E-Waste) Management Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.3", bm: "Kemahiran mengitar semula sisa logam dan komponen elektronik terpakai.", en: "Skills in recycling scrap metal and used electronic components." },
            { id: "BB_1_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "1.0 Kemahiran Pengurusan Sisa Buangan Elektronik", constructEN: "Electronic Waste (E-Waste) Management Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.4", bm: "Kemahiran membaiki dan memulihkan peralatan elektronik yang rosak.", en: "Skills in repairing and restoring damaged electronic equipment." },
            // Konstruk 2.0
            { id: "BB_2_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam", constructEN: "Eco-Friendly Circuit and Electronic Device Design Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.0", bm: "Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam", en: "Eco-Friendly Circuit and Electronic Device Design Skills" },
            { id: "BB_2_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam", constructEN: "Eco-Friendly Circuit and Electronic Device Design Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.1", bm: "Kemahiran mereka bentuk litar elektronik berkecekapan tinggi dan berkuasa rendah (low-power design).", en: "Skills in designing high-efficiency and low-power electronic circuits." },
            { id: "BB_2_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam", constructEN: "Eco-Friendly Circuit and Electronic Device Design Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.2", bm: "Kemahiran mereka bentuk perkakasan elektronik mesra alam berteraskan perlindungan alam sekitar.", en: "Skills in designing eco-friendly electronic hardware focused on environmental protection." },
            { id: "BB_2_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam", constructEN: "Eco-Friendly Circuit and Electronic Device Design Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.3", bm: "Kemahiran mereka bentuk litar yang menekankan prinsip 5R (reduce, reuse, recycle, recover & refuse).", en: "Skills in designing circuits that emphasize the 5R principles (reduce, reuse, recycle, recover, and refuse)." },
            { id: "BB_2_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam", constructEN: "Eco-Friendly Circuit and Electronic Device Design Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.4", bm: "Kemahiran mengaplikasikan prinsip reka bentuk mampan dalam penghasilan produk elektronik.", en: "Skills in applying design for sustainability principles in electronic product development." },
            // Konstruk 3.0
            { id: "BB_3_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", constructEN: "Skills in the planning, management, and procurement of electronic equipment and components", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "3.0", bm: "Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", en: "Skills in the planning, management, and procurement of electronic equipment and components." },
            { id: "BB_3_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", constructEN: "Skills in the planning, management, and procurement of electronic equipment and components", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "3.1", bm: "Kemahiran merancang projek elektronik berasaskan kelestarian alam sekitar.", en: "Skills in planning environmentally sustainable electronic projects." },
            { id: "BB_3_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", constructEN: "Skills in the planning, management, and procurement of electronic equipment and components", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "3.2", bm: "Kemahiran memilih eko-bahan (seperti pateri bebas plumbum dan bahan PCB mesra alam).", en: "Skills in selecting eco-materials (such as lead-free solder and eco-friendly PCB materials)." },
            { id: "BB_3_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", constructEN: "Skills in the planning, management, and procurement of electronic equipment and components", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "3.3", bm: "Kemahiran pengurusan inventori komponen elektronik mesra alam (seperti penyimpanan berlabel, sistem FiFo dan kabinet pengering pintar).", en: "Skills in eco-friendly electronic component inventory management (such as labeled storage, FiFo systems, and smart dry cabinets)." },
            { id: "BB_3_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", constructEN: "Skills in the planning, management, and procurement of electronic equipment and components", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "3.4", bm: "Kemahiran perolehan mampan bagi peralatan elektronik (seperti kriteria pembungkusan hijau dan rantai bekalan mesra alam).", en: "Skills in sustainable procurement for electronic equipment (such as green packaging criteria and eco-friendly supply chains)." },
            { id: "BB_3_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik", constructEN: "Skills in the planning, management, and procurement of electronic equipment and components", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "3.5", bm: "Kemahiran perolehan perkhidmatan penyelenggaraan elektronik mesra alam.", en: "Skills in procuring eco-friendly electronic maintenance services." },
            // Konstruk 4.0
            { id: "BB_4_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.0", bm: "Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", en: "Energy Saving and Electronic Power Efficiency Skills" },
            { id: "BB_4_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.1", bm: "Kemahiran mengoptimumkan pengurusan tenaga dalam sistem dan peranti elektronik.", en: "Skills in optimizing energy management in electronic systems and devices." },
            { id: "BB_4_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.2", bm: "Kemahiran mengaplikasikan peranti elektronik dalam sistem tenaga boleh baharu (seperti tenaga solar dan angin).", en: "Skills in applying electronic devices to renewable energy systems (such as solar and wind energy)." },
            { id: "BB_4_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.3", bm: "Kemahiran menganalisis kecekapan sistem pengurusan tenaga untuk mengurangkan pembaziran elektrik.", en: "Skills in analyzing energy management system efficiency to minimize electrical waste." },
            { id: "BB_4_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.4", bm: "Kemahiran mengoptimumkan kualiti dan kecekapan kuasa litar.", en: "Skills in optimizing circuit power quality and efficiency." },
            { id: "BB_4_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.5", bm: "Kemahiran mereka bentuk sistem pengurusan haba litar bagi mengurangkan pelepasan haba.", en: "Skills in designing circuit thermal management systems to reduce heat dissipation." },
            { id: "BB_4_6", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.6", bm: "Kemahiran kawalan dan pengurusan kualiti kuasa dalam sistem elektronik.", en: "Skills in power quality control and management in electronic systems." },
            { id: "BB_4_7", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik", constructEN: "Energy Saving and Electronic Power Efficiency Skills", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "4.7", bm: "Kemahiran mengintegrasikan sistem penuaian tenaga (seperti penderia piezoelektrik).", en: "Skills in integrating energy harvesting systems (such as piezoelectric sensors)." },
            // Konstruk 5.0
            { id: "BB_5_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", constructEN: "Green Technology-Based Communication Skills in the Electronics Field", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "5.0", bm: "Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", en: "Green Technology-Based Communication Skills in the Electronics Field" },
            { id: "BB_5_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", constructEN: "Green Technology-Based Communication Skills in the Electronics Field", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "5.1", bm: "Kemahiran berkomunikasi secara digital tanpa kertas dalam pelaksanaan tugasan amali elektronik.", en: "Skills in paperless digital communication during electronic practical tasks." },
            { id: "BB_5_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", constructEN: "Green Technology-Based Communication Skills in the Electronics Field", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "5.2", bm: "Kemahiran berkomunikasi menggunakan sistem ICT (Teknologi Maklumat dan Komunikasi) hijau (seperti e-mel).", en: "Skills in communicating using green ICT (Information and Communications Technology) systems (such as email)." },
            { id: "BB_5_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", constructEN: "Green Technology-Based Communication Skills in the Electronics Field", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "5.3", bm: "Kemahiran berkomunikasi dan mengawal peranti menggunakan sistem IoT (Internet Pelbagai Benda).", en: "Skills in communicating and controlling devices using IoT (Internet of Things) systems." },
            { id: "BB_5_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", constructEN: "Green Technology-Based Communication Skills in the Electronics Field", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "5.4", bm: "Kemahiran mengaplikasikan platform komunikasi digital hibrid (seperti Google Meet dan Zoom) bagi mengurangkan pelepasan gas rumah hijau.", en: "Skills in applying hybrid digital communication platforms, such as Google Meet and Zoom, to reduce greenhouse gas emissions." },
            { id: "BB_5_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik", constructEN: "Green Technology-Based Communication Skills in the Electronics Field", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "5.5", bm: "Kemahiran mengendalikan pemantauan data litar secara jarak jauh menggunakan aplikasi pengkomputeran awan mesra tenaga.", en: "Skills in remote circuit data monitoring using energy-efficient cloud computing applications." },
            // Konstruk 6.0
            { id: "BB_6_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", constructEN: "Teamwork Skills for Green Practices in Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "6.0", bm: "Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", en: "Teamwork Skills for Green Practices in Electronics" },
            { id: "BB_6_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", constructEN: "Teamwork Skills for Green Practices in Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "6.1", bm: "Kemahiran kerja berpasukan memastikan setiap ahli menyumbang secara aktif kepada amalan hijau di makmal atau bengkel.", en: "Skills in teamwork to ensure every member actively contributes to green practices in the laboratory or workshop." },
            { id: "BB_6_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", constructEN: "Teamwork Skills for Green Practices in Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "6.2", bm: "Kemahiran berkolaborasi dengan pihak luar/industri bagi menyokong aktiviti pencegahan pencemaran alam sekitar.", en: "Skills in collaborating with external parties/industry to support environmental pollution prevention activities." },
            { id: "BB_6_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", constructEN: "Teamwork Skills for Green Practices in Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "6.3", bm: "Kemahiran perhubungan pasukan secara segerak (seperti persidangan video atau audio) bagi mencegah pencemaran alam sekitar.", en: "Skills in synchronous team communication (such as video or audio conferencing) to prevent environmental pollution." },
            { id: "BB_6_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", constructEN: "Teamwork Skills for Green Practices in Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "6.4", bm: "Kemahiran memahami peranan ahli pasukan berasaskan keperluan teknikal bagi mencegah pencemaran alam sekitar.", en: "Skills in understanding team members' roles based on technical requirements to prevent environmental pollution." },
            { id: "BB_6_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik", constructEN: "Teamwork Skills for Green Practices in Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "6.5", bm: "Kemahiran mengkoordinasi peranan ahli pasukan bagi meminimumkan pembaziran komponen dan bahan amali.", en: "Skills in coordinating team roles to minimize component and practical material waste." },
            // Konstruk 7.0
            { id: "BB_7_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.0", bm: "Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", en: "Problem-Solving and Creative Thinking Skills in Green Electronics" },
            { id: "BB_7_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.1", bm: "Kemahiran menyelesaikan masalah kegagalan litar yang mengambil kira pengurangan impak negatif alam sekitar.", en: "Skills in solving circuit failure problems taking into account environmental impact reduction." },
            { id: "BB_7_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.2", bm: "Kemahiran berfikir secara kritis dalam mereka bentuk peranti elektronik mesra alam.", en: "Critical thinking skills in designing eco-friendly electronic devices." },
            { id: "BB_7_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.3", bm: "Kemahiran berfikir secara strategik bagi mengurangkan jejak karbon (carbon footprint) produk elektronik.", en: "Skills in strategic thinking to reduce the carbon footprint of electronic products." },
            { id: "BB_7_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.4", bm: "Kemahiran berfikir secara terbuka terhadap inovasi teknologi hijau baharu dalam bidang elektronik.", en: "Skills in adopting an open-minded approach toward new green technology innovations in the electronics field." },
            { id: "BB_7_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.5", bm: "Kemahiran Berfikir Aras Tinggi (KBAT) dalam merancang penyelesaian kelestarian sistem elektronik.", en: "Higher Order Thinking Skills (HOTS) in planning electronic system sustainability solutions." },
            { id: "BB_7_6", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau", constructEN: "Problem-Solving and Creative Thinking Skills in Green Electronics", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "7.6", bm: "Kemahiran berfikir secara strategik bagi mengurangkan jejak karbon (carbon footprint) produk elektronik.", en: "Skills in strategic thinking to reduce the carbon footprint of electronic products." },
            // Konstruk 8.0
            { id: "BB_8_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", constructEN: "Biodiversity and Ecosystem Protection Skills through Electronic Applications", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "8.0", bm: "Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", en: "Biodiversity and Ecosystem Protection Skills through Electronic Applications" },
            { id: "BB_8_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", constructEN: "Biodiversity and Ecosystem Protection Skills through Electronic Applications", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "8.1", bm: "Kemahiran melindungi alam sekitar melalui penggunaan peralatan dan peranti pengawasan elektronik yang sesuai haruslah diterapkan dalam kurikulum Program Teknologi Elektronik TVET.", en: "Environmental protection skills through the appropriate use of electronic monitoring equipment and devices should be incorporated into the TVET Electronic Technology Program curriculum." },
            { id: "BB_8_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", constructEN: "Biodiversity and Ecosystem Protection Skills through Electronic Applications", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "8.2", bm: "Kemahiran pemantauan elektronik bagi memulihara biodiversiti haruslah diterapkan dalam kurikulum Program Teknologi Elektronik TVET.", en: "Electronic monitoring skills to conserve biodiversity should be incorporated into the TVET Electronic Technology Program curriculum." },
            { id: "BB_8_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", constructEN: "Biodiversity and Ecosystem Protection Skills through Electronic Applications", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "8.3", bm: "Kemahiran mengaplikasikan penderia (sensors) dan peranti elektronik bagi pemantauan kualiti alam sekitar/ekosistem.", en: "Skills in applying sensors and electronic devices for environmental/ecosystem quality monitoring." },
            { id: "BB_8_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", constructEN: "Biodiversity and Ecosystem Protection Skills through Electronic Applications", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "8.4", bm: "Kemahiran mengaplikasikan sistem elektronik hijau (seperti solar) bagi memulihara landskap alam sekitar.", en: "Skills in applying green electronic systems (such as solar) to conserve environmental landscapes." },
            { id: "BB_8_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian B: Elemen Kemahiran", constructBM: "8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik", constructEN: "Biodiversity and Ecosystem Protection Skills through Electronic Applications", instruction: "Nilaikan tahap kepentingan elemen kemahiran berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "8.5", bm: "Kemahiran menyelenggara sistem dan peranti pemantauan elektronik hijau.", en: "Skills in maintaining green electronic monitoring systems and devices." },
            // Soalan Terbuka Bahagian B
            { id: "BB_OPEN", type: "textarea", required: false, sectionBadge: "Seksyen B • Bahagian B: Soalan Terbuka", instruction: "Soalan Terbuka (Pilihan / Optional): Anda boleh mengosongkan ruangan ini jika tiada cadangan tambahan.", no: "B+", bm: "Apakah elemen kemahiran praktikal hijau lain yang penting tetapi tidak tersenarai di atas?", en: "What other practical green skill elements are important but not listed above?", placeholder: "Nyatakan cadangan elemen kemahiran praktikal tambahan di sini..." },

            // --- SEKSYEN B - BAHAGIAN C: ELEMEN SIKAP DAN NILAI (12 LIKERT + 1 TERBUKA) ---
            // Konstruk 1.0
            { id: "BC_1_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik", constructEN: "Environmental Awareness in the Field of Electronics", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.0", bm: "Kesedaran Alam Sekitar dalam Bidang Elektronik", en: "Environmental Awareness in the Field of Electronics" },
            { id: "BC_1_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik", constructEN: "Environmental Awareness in the Field of Electronics", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.1", bm: "Kesedaran terhadap kepentingan melindungi alam sekitar di tempat kerja atau bengkel elektronik.", en: "Awareness of the importance of environmental protection in the workplace or electronics workshop." },
            { id: "BC_1_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik", constructEN: "Environmental Awareness in the Field of Electronics", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.2", bm: "Kesedaran terhadap dasar, perundangan, dan standard piawaian hijau industri elektronik.", en: "Awareness of green policies, regulations, and industry standards in electronics." },
            { id: "BC_1_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik", constructEN: "Environmental Awareness in the Field of Electronics", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.3", bm: "Kesedaran terhadap impak pengurangan sisa buangan elektronik (e-waste) kepada alam sekitar.", en: "Awareness of the impact of electronic waste (e-waste) reduction on the environment." },
            { id: "BC_1_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik", constructEN: "Environmental Awareness in the Field of Electronics", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.4", bm: "Kesedaran terhadap amalan hijau dalam proses pembuatan dan perkhidmatan elektronik.", en: "Awareness of green practices in electronic manufacturing and service processes." },
            { id: "BC_1_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik", constructEN: "Environmental Awareness in the Field of Electronics", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "1.5", bm: "Kesedaran terhadap penggunaan sumber tenaga boleh baharu dalam pengoperasian sistem elektronik.", en: "Awareness of using renewable energy sources in electronic system operations." },
            // Konstruk 2.0
            { id: "BC_2_0", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "2.0 Nilai Positif & Budaya Hijau Industri Elektronik", constructEN: "Positive Values and Green Culture in the Electronics Industry", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.0", bm: "Nilai Positif & Budaya Hijau Industri Elektronik", en: "Positive Values and Green Culture in the Electronics Industry" },
            { id: "BC_2_1", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "2.0 Nilai Positif & Budaya Hijau Industri Elektronik", constructEN: "Positive Values and Green Culture in the Electronics Industry", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.1", bm: "Nilai amalan penjimatan tenaga elektrik (seperti mematikan peralatan dan suis utama apabila tidak digunakan).", en: "Values of electrical energy conservation practices (such as switching off equipment and main switches when not in use)." },
            { id: "BC_2_2", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "2.0 Nilai Positif & Budaya Hijau Industri Elektronik", constructEN: "Positive Values and Green Culture in the Electronics Industry", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.2", bm: "Nilai amalan 5R (reduce, reuse, recycle, recover & refuse) terhadap perkakasan elektronik.", en: "Values of the 5R practices (reduce, reuse, recycle, recover, and refuse) regarding electronic hardware." },
            { id: "BC_2_3", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "2.0 Nilai Positif & Budaya Hijau Industri Elektronik", constructEN: "Positive Values and Green Culture in the Electronics Industry", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.3", bm: "Nilai komitmen terhadap pengurusan selamat sisa toksik (seperti asid punaran) dan komponen berbahaya (seperti bateri litium atau kapasitor elektrolit).", en: "Values of commitment to safe management of toxic waste (such as etching acid) and hazardous components (such as lithium batteries or electrolytic capacitors)." },
            { id: "BC_2_4", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "2.0 Nilai Positif & Budaya Hijau Industri Elektronik", constructEN: "Positive Values and Green Culture in the Electronics Industry", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.4", bm: "Nilai keutamaan terhadap pemuliharaan sumber melalui kecekapan reka bentuk litar.", en: "Values of prioritizing resource conservation through circuit design efficiency." },
            { id: "BC_2_5", type: "likert", required: true, sectionBadge: "Seksyen B • Bahagian C: Elemen Sikap dan Nilai", constructBM: "2.0 Nilai Positif & Budaya Hijau Industri Elektronik", constructEN: "Positive Values and Green Culture in the Electronics Industry", instruction: "Nilaikan tahap kepentingan penerapan elemen sikap dan nilai hijau berikut untuk kurikulum Program Teknologi Elektronik TVET:", no: "2.5", bm: "Nilai pembudayaan amalan dan etika hijau dalam kerjaya bidang elektronik.", en: "Values of cultivating green practices and ethics in electronic careers." },
            // Soalan Terbuka Bahagian C
            { id: "BC_OPEN", type: "textarea", required: false, sectionBadge: "Seksyen B • Bahagian C: Soalan Terbuka", instruction: "Soalan Terbuka Akhir (Pilihan / Optional): Klik 'Hantar Jawapan' untuk melengkapkan soal selidik.", no: "C+", bm: "Apakah elemen sikap dan nilai hijau lain yang penting tetapi tidak tersenarai di atas?", en: "What other green attitudes and values elements are important but not listed above?", placeholder: "Nyatakan cadangan elemen sikap dan nilai tambahan di sini..." }
        ];

        // ===================================================================
        // KEADAAN APLIKASI (STATE & LOCALSTORAGE AUTO-SAVE)
        // ===================================================================
        let currentIndex = 0;
        let answers = {};
        let autoAdvanceTimer = null;
        let lastSubmittedRecord = null;

        try {
            const savedAnswers = localStorage.getItem('uthm_green_skills_answers');
            const savedIndex = localStorage.getItem('uthm_green_skills_index');
            if (savedAnswers) answers = JSON.parse(savedAnswers);
            if (savedIndex !== null) currentIndex = Math.min(Math.max(0, parseInt(savedIndex, 10)), QUESTIONS.length - 1);
        } catch (e) {
            console.warn("Local storage tidak tersedia:", e);
        }

        function saveState() {
            try {
                localStorage.setItem('uthm_green_skills_answers', JSON.stringify(answers));
                localStorage.setItem('uthm_green_skills_index', String(currentIndex));
            } catch (e) {}
        }

        // ===================================================================
        // NAVIGASI SKRIN UTAMA (COVER -> WIZARD -> THANK YOU)
        // ===================================================================
        function startSurvey(resume = false) {
            if (!resume) {
                currentIndex = 0;
            }
            document.getElementById('cover-screen').classList.add('hidden');
            document.getElementById('thank-you-screen').classList.add('hidden');
            document.getElementById('wizard-screen').classList.remove('hidden');
            document.getElementById('header-progress-wrapper').classList.remove('hidden');
            renderQuestion(currentIndex, 'right');
        }

        function returnToCover() {
            document.getElementById('wizard-screen').classList.add('hidden');
            document.getElementById('header-progress-wrapper').classList.add('hidden');
            document.getElementById('cover-screen').classList.remove('hidden');
            checkResumeButton();
        }

        function checkResumeButton() {
            const answeredCount = Object.keys(answers).filter(k => answers[k] !== "").length;
            const resumeBtn = document.getElementById('btn-resume-survey');
            if (answeredCount > 0) {
                resumeBtn.classList.remove('hidden');
                document.getElementById('resume-btn-label').textContent = `Sambung Jawapan (${answeredCount}/${QUESTIONS.length})`;
            } else {
                resumeBtn.classList.add('hidden');
            }
        }

        // ===================================================================
        // PENJANAAN PAPARAN SATU SOALAN PADA SATU MASA
        // ===================================================================
        function renderQuestion(idx, direction = 'right') {
            clearTimeout(autoAdvanceTimer);
            currentIndex = idx;
            saveState();

            const q = QUESTIONS[idx];
            const total = QUESTIONS.length;
            const pct = Math.round(((idx + 1) / total) * 100);

            // Kemas kini Bar Kemajuan Header
            document.getElementById('header-q-counter').textContent = `Soalan ${idx + 1} daripada ${total}`;
            document.getElementById('header-pct-text').textContent = `${pct}%`;
            document.getElementById('header-progress-bar').style.width = `${pct}%`;

            // Kemas kini Dropdown Lompat Bahagian
            const jumper = document.getElementById('section-jumper');
            if (idx < 6) jumper.value = "0";
            else if (idx < 20) jumper.value = "6";
            else if (idx < 76) jumper.value = "20";
            else jumper.value = "76";

            // Animasi Kad
            const card = document.getElementById('question-card');
            card.classList.remove('animate-slide-right', 'animate-slide-left', 'shake-error');
            void card.offsetWidth; // trigger reflow
            card.classList.add(direction === 'left' ? 'animate-slide-left' : 'animate-slide-right');

            // Isi Metadata Soalan
            document.getElementById('q-section-badge').textContent = q.sectionBadge;
            document.getElementById('q-code-badge').textContent = `Kod: ${q.id}`;
            document.getElementById('q-instruction').textContent = q.instruction;
            document.getElementById('q-number-pill').textContent = q.no;
            document.getElementById('q-text-bm').innerHTML = `${q.bm} ${q.required ? '<span class="text-red-500">*</span>' : ''}`;
            document.getElementById('q-text-en').textContent = q.en;

            // Papar Konstruk jika berkaitan (Seksyen B)
            const constructBox = document.getElementById('q-construct-box');
            if (q.constructBM) {
                constructBox.classList.remove('hidden');
                document.getElementById('q-construct-bm').textContent = q.constructBM;
                document.getElementById('q-construct-en').textContent = q.constructEN;
            } else {
                constructBox.classList.add('hidden');
            }

            // Jana Kawasan Input Mengikut Jenis Soalan
            const inputArea = document.getElementById('q-input-area');
            const kbdHint = document.getElementById('keyboard-hint');
            const currentVal = answers[q.id] || "";

            if (q.type === 'radio') {
                kbdHint.classList.add('hidden');
                inputArea.innerHTML = `
                    <div class="grid grid-cols-1 gap-3">
                        ${q.options.map((opt, oIdx) => {
                            const isSelected = currentVal === opt.value;
                            const letter = String.fromCharCode(65 + oIdx);
                            return `
                                <button type="button" onclick="selectOption('${q.id}', '${opt.value.replace(/'/g, "\\'")}')"
                                    class="option-card w-full text-left p-4 rounded-2xl border-2 border-slate-200 bg-white flex items-center gap-3.5 cursor-pointer ${isSelected ? 'selected' : ''}">
                                    <span class="key-badge w-8 h-8 rounded-xl border-2 border-slate-300 bg-slate-50 text-slate-700 font-bold text-xs flex items-center justify-center shrink-0">
                                        ${letter}
                                    </span>
                                    <div class="flex-1">
                                        <span class="font-bold text-slate-900 text-sm sm:text-base block text-bm">${opt.bm}</span>
                                        <span class="text-xs sm:text-sm text-slate-500 italic block text-en">${opt.en}</span>
                                    </div>
                                    ${isSelected ? '<i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-600 shrink-0"></i>' : ''}
                                </button>
                            `;
                        }).join('')}
                    </div>
                `;
            } else if (q.type === 'likert') {
                kbdHint.classList.remove('hidden');
                inputArea.innerHTML = `
                    <div class="grid grid-cols-1 sm:grid-cols-5 gap-2.5 sm:gap-3">
                        ${LIKERT_SCALE.map(opt => {
                            const isSelected = currentVal === opt.val;
                            return `
                                <button type="button" onclick="selectOption('${q.id}', '${opt.val}')"
                                    class="option-card p-3.5 sm:p-4 rounded-2xl border-2 border-slate-200 bg-white flex sm:flex-col items-center sm:justify-center text-left sm:text-center gap-3 sm:gap-1.5 cursor-pointer ${isSelected ? 'selected' : ''}">
                                    <span class="key-badge w-10 h-10 rounded-xl border-2 border-slate-300 bg-slate-50 text-slate-800 font-extrabold text-base flex items-center justify-center shrink-0">
                                        ${opt.val}
                                    </span>
                                    <div class="flex-1 sm:flex-initial">
                                        <span class="text-[11px] font-extrabold uppercase tracking-wider text-emerald-700 block">(${opt.code})</span>
                                        <span class="text-xs sm:text-[13px] font-bold text-slate-900 block leading-tight mt-0.5 text-bm">${opt.bm}</span>
                                        <span class="text-[11px] text-slate-500 italic block leading-tight mt-0.5 text-en">${opt.en}</span>
                                    </div>
                                </button>
                            `;
                        }).join('')}
                    </div>
                `;
            } else if (q.type === 'text') {
                kbdHint.classList.add('hidden');
                inputArea.innerHTML = `
                    <div>
                        <input type="text" id="active-text-input" value="${currentVal.replace(/"/g, '&quot;')}"
                            placeholder="${q.placeholder || ''}"
                            oninput="answers['${q.id}'] = this.value; saveState();"
                            class="w-full px-4 py-4 rounded-2xl border-2 border-slate-200 bg-slate-50/50 focus:bg-white text-slate-900 text-base focus:border-emerald-600 focus:ring-4 focus:ring-emerald-500/15 outline-none transition">
                    </div>
                `;
                setTimeout(() => document.getElementById('active-text-input')?.focus(), 100);
            } else if (q.type === 'textarea') {
                kbdHint.classList.add('hidden');
                inputArea.innerHTML = `
                    <div>
                        <textarea id="active-textarea-input" rows="4"
                            placeholder="${q.placeholder || ''}"
                            oninput="answers['${q.id}'] = this.value; saveState();"
                            class="w-full px-4 py-3.5 rounded-2xl border-2 border-slate-200 bg-slate-50/50 focus:bg-white text-slate-900 text-sm sm:text-base focus:border-emerald-600 focus:ring-4 focus:ring-emerald-500/15 outline-none transition">${currentVal}</textarea>
                    </div>
                `;
                setTimeout(() => document.getElementById('active-textarea-input')?.focus(), 100);
            }

            // Kemas kini Butang Sebelum & Seterusnya / Hantar
            const prevBtn = document.getElementById('btn-prev');
            prevBtn.disabled = idx === 0;
            prevBtn.classList.toggle('opacity-40', idx === 0);
            prevBtn.classList.toggle('pointer-events-none', idx === 0);

            const nextBtn = document.getElementById('btn-next');
            const nextLabel = document.getElementById('btn-next-label');
            if (idx === total - 1) {
                nextBtn.className = "px-7 py-3.5 rounded-xl bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-500 hover:to-teal-500 text-white font-extrabold text-sm shadow-lg shadow-emerald-600/30 flex items-center gap-2 transition cursor-pointer";
                nextLabel.innerHTML = `Hantar Jawapan / <span class="italic font-normal">Submit</span>`;
            } else {
                nextBtn.className = "px-6 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white font-bold text-sm shadow-md shadow-emerald-600/20 flex items-center gap-2 transition cursor-pointer";
                nextLabel.innerHTML = `Seterusnya / <span class="italic font-normal">Next</span>`;
            }

            lucide.createIcons();
        }

        // ===================================================================
        // PILIH JAWAPAN & AUTO-ADVANCE
        // ===================================================================
        function selectOption(qId, value) {
            answers[qId] = value;
            saveState();

            // Sorot pilihan semasa
            renderQuestion(currentIndex, 'none');

            const autoAdvance = document.getElementById('auto-advance-toggle').checked;
            if (autoAdvance && currentIndex < QUESTIONS.length - 1) {
                clearTimeout(autoAdvanceTimer);
                autoAdvanceTimer = setTimeout(() => {
                    renderQuestion(currentIndex + 1, 'right');
                }, 340);
            }
        }

        function prevQuestion() {
            if (currentIndex > 0) {
                renderQuestion(currentIndex - 1, 'left');
            }
        }

        function nextQuestion() {
            const q = QUESTIONS[currentIndex];
            const val = (answers[q.id] || "").trim();

            if (q.required && val === "") {
                const card = document.getElementById('question-card');
                card.classList.remove('shake-error');
                void card.offsetWidth;
                card.classList.add('shake-error');
                showToast("Jawapan Diperlukan", "Sila pilih atau isi jawapan untuk soalan ini sebelum meneruskan.", "error");
                return;
            }

            if (currentIndex < QUESTIONS.length - 1) {
                renderQuestion(currentIndex + 1, 'right');
            } else {
                submitFullSurvey();
            }
        }

        function jumpToSection(targetIdxStr) {
            const targetIdx = parseInt(targetIdxStr, 10);
            const direction = targetIdx >= currentIndex ? 'right' : 'left';
            renderQuestion(targetIdx, direction);
        }

        // ===================================================================
        // SOKONGAN PINTASAN PAPAN KEKUNCI (KEYBOARD SHORTCUTS)
        // ===================================================================
        document.addEventListener('keydown', function(e) {
            if (document.getElementById('wizard-screen').classList.contains('hidden')) return;
            if (!document.getElementById('setup-modal').classList.contains('hidden')) return;

            const activeTag = document.activeElement.tagName.toLowerCase();
            const q = QUESTIONS[currentIndex];

            // Jika pengguna sedang menaip dalam input teks
            if (activeTag === 'input' || activeTag === 'textarea') {
                if (e.key === 'Enter' && activeTag === 'input') {
                    e.preventDefault();
                    nextQuestion();
                }
                return;
            }

            // Kekunci 1 - 5 untuk skala Likert
            if (q.type === 'likert' && ['1', '2', '3', '4', '5'].includes(e.key)) {
                e.preventDefault();
                selectOption(q.id, e.key);
            }
            // Kekunci A - E untuk Demografi Radio
            else if (q.type === 'radio') {
                const idx = e.key.toUpperCase().charCodeAt(0) - 65;
                if (idx >= 0 && idx < q.options.length) {
                    e.preventDefault();
                    selectOption(q.id, q.options[idx].value);
                }
            }
            // Kekunci Anak Panah / Enter
            else if (e.key === 'ArrowRight' || e.key === 'Enter') {
                e.preventDefault();
                nextQuestion();
            } else if (e.key === 'ArrowLeft') {
                e.preventDefault();
                prevQuestion();
            }
        });

        // ===================================================================
        // PENGHANTARAN KE GOOGLE SHEETS
        // ===================================================================
        async function submitFullSurvey() {
            // Semak jika ada mana-mana soalan wajib tertinggal
            const firstMissingIdx = QUESTIONS.findIndex(item => item.required && !(answers[item.id] || "").trim());
            if (firstMissingIdx !== -1) {
                showToast("Soal Selidik Belum Lengkap", `Sila lengkapkan Soalan ${firstMissingIdx + 1} (${QUESTIONS[firstMissingIdx].id}) terlebih dahulu.`, "error");
                renderQuestion(firstMissingIdx, 'left');
                return;
            }

            const nextBtn = document.getElementById('btn-next');
            nextBtn.disabled = true;
            nextBtn.innerHTML = `<i data-lucide="loader-2" class="w-4 h-4 animate-spin"></i> <span>Menghantar...</span>`;
            lucide.createIcons();

            // Susun lajur mengikut urutan tepat soal selidik
            const payload = {
                Timestamp: new Date().toLocaleString('en-GB', { timeZone: 'Asia/Kuala_Lumpur' })
            };
            QUESTIONS.forEach(item => {
                payload[item.id] = (answers[item.id] || "").trim();
            });

            lastSubmittedRecord = payload;
            const statusBox = document.getElementById('submission-status-box');

            try {
                if (!SCRIPT_URL || SCRIPT_URL === "YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL") {
                    await new Promise(r => setTimeout(r, 700));
                    statusBox.innerHTML = `
                        <p class="font-bold text-amber-700">Mod Pratonton (URL Google Sheet Belum Ditetapkan)</p>
                        <p class="mt-1 text-xs">Data anda disimpan secara tempatan. Penyelidik boleh menyambungkan Google Sheet melalui butang <strong>Setup Google Sheets & GitHub</strong> di footer bawah.</p>
                    `;
                } else {
                    await fetch(SCRIPT_URL, {
                        method: 'POST',
                        mode: 'no-cors',
                        headers: { 'Content-Type': 'text/plain;charset=utf-8' },
                        body: JSON.stringify(payload)
                    });
                    statusBox.innerHTML = `
                        <p class="font-bold text-emerald-700">Berjaya Dihantar ke Google Sheets!</p>
                        <p class="mt-1 text-xs">Masa Rekod: <strong>${payload.Timestamp}</strong></p>
                    `;
                }

                // Kosongkan cache jawapan semasa selepas berjaya hantar
                localStorage.removeItem('uthm_green_skills_answers');
                localStorage.removeItem('uthm_green_skills_index');

                document.getElementById('wizard-screen').classList.add('hidden');
                document.getElementById('header-progress-wrapper').classList.add('hidden');
                document.getElementById('thank-you-screen').classList.remove('hidden');
                lucide.createIcons();

            } catch (err) {
                console.error(err);
                showToast("Ralat Rangkaian", "Gagal menghantar ke Google Sheet. Sila muat turun salinan CSV anda.", "error");
                statusBox.innerHTML = `<p class="font-bold text-red-600">Ralat sambungan internet. Sila muat turun salinan CSV di bawah.</p>`;
                document.getElementById('wizard-screen').classList.add('hidden');
                document.getElementById('thank-you-screen').classList.remove('hidden');
            } finally {
                nextBtn.disabled = false;
            }
        }

        function resetAndStartNew() {
            answers = {};
            currentIndex = 0;
            localStorage.removeItem('uthm_green_skills_answers');
            localStorage.removeItem('uthm_green_skills_index');
            startSurvey(false);
        }

        // ===================================================================
        // MUAT TURUN CSV, BAHASA, TOAST & MODAL SETUP GITHUB
        // ===================================================================
        function downloadReceiptCSV() {
            if (!lastSubmittedRecord) return;
            const headers = Object.keys(lastSubmittedRecord);
            const values = headers.map(h => `"${String(lastSubmittedRecord[h]).replace(/"/g, '""')}"`);
            const csv = "data:text/csv;charset=utf-8," + headers.join(",") + "\n" + values.join(",");
            const link = document.createElement("a");
            link.setAttribute("href", encodeURI(csv));
            link.setAttribute("download", `SoalSelidik_GreenSkills_UTHM_${Date.now()}.csv`);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }

        function setLanguage(mode) {
            document.body.classList.remove('lang-bm', 'lang-en');
            if (mode === 'bm') document.body.classList.add('lang-bm');
            if (mode === 'en') document.body.classList.add('lang-en');

            ['both', 'bm', 'en'].forEach(m => {
                const btn = document.getElementById(`btn-lang-${m}`);
                btn.className = (m === mode)
                    ? "px-2.5 py-1 rounded-lg bg-emerald-600 text-white shadow-sm transition"
                    : "px-2.5 py-1 rounded-lg text-slate-600 hover:text-slate-900 transition";
            });
        }

        let toastTimer = null;
        function showToast(title, msg, type = "info") {
            const box = document.getElementById('toast-box');
            document.getElementById('toast-title').textContent = title;
            document.getElementById('toast-msg').textContent = msg;
            box.classList.remove('translate-y-28', 'opacity-0');
            clearTimeout(toastTimer);
            toastTimer = setTimeout(() => box.classList.add('translate-y-28', 'opacity-0'), 4200);
        }

        function openSetupModal() {
            const statusEl = document.getElementById('setup-url-status');
            const inputEl = document.getElementById('setup-url-input');
            if (SCRIPT_URL && SCRIPT_URL !== "YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL") {
                statusEl.textContent = "Aktif: " + SCRIPT_URL;
                inputEl.value = SCRIPT_URL;
            } else {
                statusEl.textContent = "Belum dikonfigurasi (YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL)";
                inputEl.value = "";
            }
            document.getElementById('setup-modal').classList.remove('hidden');
            lucide.createIcons();
        }

        function closeSetupModal() {
            document.getElementById('setup-modal').classList.add('hidden');
        }

        function saveScriptUrl() {
            const val = document.getElementById('setup-url-input').value.trim();
            if (!val.startsWith("https://script.google.com/")) {
                showToast("URL Tidak Sah", "Sila masukkan URL Web App yang bermula dengan https://script.google.com/...", "error");
                return;
            }
            SCRIPT_URL = val;
            localStorage.setItem('uthm_gs_script_url', val);
            openSetupModal();
            showToast("Disimpan", "URL Google Apps Script telah diaktifkan pada pelayar ini.", "success");
        }

        function copyAppsScript() {
            const code = document.getElementById('apps-script-snippet').innerText;
            const ta = document.createElement('textarea');
            ta.value = code;
            document.body.appendChild(ta);
            ta.select();
            document.execCommand('copy');
            document.body.removeChild(ta);
            showToast("Kod Disalin", "Kod Google Apps Script berjaya disalin ke papan keratan.", "success");
        }

        function downloadConfiguredHTML() {
            const urlToBake = document.getElementById('setup-url-input').value.trim() || SCRIPT_URL;
            let fullHTML = "<!DOCTYPE html>\n" + document.documentElement.outerHTML;
            if (urlToBake && urlToBake.startsWith("https://script.google.com/")) {
                fullHTML = fullHTML.replace(
                    /const DEFAULT_SCRIPT_URL = ".*?";/,
                    `const DEFAULT_SCRIPT_URL = "${urlToBake}";`
                );
            }
            const blob = new Blob([fullHTML], { type: "text/html;charset=utf-8" });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = "index.html";
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            showToast("Fail Dimuat Turun", "Fail index.html sedia untuk dimuat naik ke GitHub Pages!", "success");
        }

        // Inisialisasi Ikon & Semak Kemajuan Tersimpan
        window.addEventListener('DOMContentLoaded', () => {
            lucide.createIcons();
            checkResumeButton();
        });
    </script>
</body>
</html>
