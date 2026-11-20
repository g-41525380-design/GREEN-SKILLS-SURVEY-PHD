<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soal Selidik PhD UTHM | Kerangka Kemahiran Hijau TVET Elektronik</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Plus+Jakarta+Sans:wght@500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                    colors: {
                        uthm: {
                            navy: '#1a237e',
                            dark: '#0f172a',
                            red: '#d32f2f',
                            gold: '#f59e0b'
                        },
                        likert: {
                            1: '#ef4444', // Merah (Red)
                            2: '#facc15', // Kuning (Yellow)
                            3: '#f97316', // Oren (Orange)
                            4: '#84cc16', // Hijau Muda (Light Green)
                            5: '#15803d', // Hijau (Green)
                        }
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background: radial-gradient(circle at top right, #eef2ff 0%, #f8fafc 45%, #ecfdf5 100%);
            min-height: 100vh;
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.94);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(226, 232, 240, 0.9);
            box-shadow: 0 20px 40px -15px rgba(15, 23, 42, 0.08), 0 4px 12px -2px rgba(15, 23, 42, 0.03);
        }
        .slide-enter {
            animation: slideFadeIn 0.32s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }
        @keyframes slideFadeIn {
            from {
                opacity: 0;
                transform: translateY(14px) scale(0.99);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
    </style>
</head>
<body class="text-slate-800 antialiased selection:bg-indigo-100 selection:text-indigo-900 flex flex-col justify-between">

    <!-- Top Academic Header Bar -->
    <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md border-b border-slate-200/80 shadow-sm">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 py-3 flex flex-wrap items-center justify-between gap-3">
            <!-- UTHM Emblem & Title -->
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 sm:w-11 sm:h-11 rounded-xl bg-gradient-to-br from-[#1a237e] to-[#283593] flex items-center justify-center shadow-md shrink-0 relative overflow-hidden">
                    <!-- Custom Academic Crest SVG -->
                    <svg class="w-7 h-7 text-white" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M12 10H52V30C52 43.2548 43.0457 52.8 32 56C20.9543 52.8 12 43.2548 12 30V10Z" stroke="white" stroke-width="3.5" fill="#1e1b4b"/>
                        <circle cx="32" cy="27" r="11" fill="#dc2626"/>
                        <path d="M22 25L32 20L42 25L32 30L22 25Z" fill="white"/>
                        <path d="M22 29L32 34L42 29" stroke="white" stroke-width="2.5" stroke-linecap="round"/>
                        <path d="M21 43L32 38L43 43" stroke="#34d399" stroke-width="3" stroke-linecap="round"/>
                    </svg>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <span class="text-xs font-extrabold tracking-wider uppercase text-[#1a237e] bg-indigo-50 px-2 py-0.5 rounded-md border border-indigo-100">UTHM • FPTV</span>
                        <span class="hidden sm:inline-block text-xs font-medium text-emerald-700 bg-emerald-50 px-2 py-0.5 rounded-md border border-emerald-200">Kajian PhD TVET</span>
                    </div>
                    <h1 class="font-display font-bold text-sm sm:text-base text-slate-900 leading-tight mt-0.5 line-clamp-1">
                        Kerangka Kemahiran Hijau Teknologi Elektronik TVET
                    </h1>
                </div>
            </div>

            <!-- Controls: Language Toggle, Auto-Advance, Navigator, Researcher Info -->
            <div class="flex items-center gap-2">
                <!-- Language Filter -->
                <div class="inline-flex rounded-xl bg-slate-100 p-1 border border-slate-200 text-xs font-semibold" role="group">
                    <button type="button" onclick="setLangMode('both')" id="lang-both" class="px-2.5 py-1 rounded-lg bg-white text-[#1a237e] shadow-sm transition">BM+EN</button>
                    <button type="button" onclick="setLangMode('bm')" id="lang-bm" class="px-2.5 py-1 rounded-lg text-slate-600 hover:text-slate-900 transition">BM</button>
                    <button type="button" onclick="setLangMode('en')" id="lang-en" class="px-2.5 py-1 rounded-lg text-slate-600 hover:text-slate-900 transition">EN</button>
                </div>

                <!-- Question Map Button -->
                <button type="button" onclick="toggleDrawer(true)" id="btn-nav-drawer" class="hidden items-center gap-1.5 px-3 py-1.5 rounded-xl bg-slate-100 hover:bg-slate-200/80 text-slate-700 text-xs font-semibold border border-slate-200 transition" title="Senarai Soalan / Question Navigator">
                    <svg class="w-4 h-4 text-[#1a237e]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7"/></svg>
                    <span id="nav-counter-badge">0/0</span>
                </button>

                <!-- Researcher Info Button -->
                <button type="button" onclick="toggleInfoModal(true)" class="inline-flex items-center gap-1.5 px-2.5 sm:px-3 py-1.5 rounded-xl bg-indigo-50 hover:bg-indigo-100 text-[#1a237e] border border-indigo-200 text-xs font-semibold transition" title="Maklumat Penyelidik & Penyelia">
                    <svg class="w-4 h-4 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"/></svg>
                    <span class="hidden md:inline">Penyelidik & Penyelia</span>
                </button>

                <!-- Google Sheet Connection Settings Button -->
                <button type="button" onclick="toggleSheetModal(true)" id="btn-sheet-settings" class="inline-flex items-center gap-1.5 px-2.5 sm:px-3 py-1.5 rounded-xl bg-emerald-50 hover:bg-emerald-100 text-emerald-800 border border-emerald-200 text-xs font-semibold transition" title="Tetapan Sambungan Google Sheet">
                    <span id="sheet-status-dot" class="w-2 h-2 rounded-full bg-emerald-500 shrink-0"></span>
                    <span id="sheet-header-label" class="hidden lg:inline">Google Sheet Aktif</span>
                </button>
            </div>
        </div>

        <!-- Global Progress Bar (Visible during survey) -->
        <div id="progress-wrapper" class="hidden bg-slate-100 border-t border-slate-200/60">
            <div class="max-w-5xl mx-auto px-4 sm:px-6 py-1.5 flex items-center justify-between text-[11px] font-medium text-slate-600">
                <span id="progress-section-label" class="font-semibold text-[#1a237e] truncate">Seksyen A: Demografi</span>
                <div class="flex items-center gap-3 shrink-0">
                    <label class="hidden sm:inline-flex items-center gap-1.5 cursor-pointer select-none text-slate-500 hover:text-slate-800">
                        <input type="checkbox" id="auto-advance-toggle" checked class="rounded text-emerald-600 focus:ring-emerald-500 w-3.5 h-3.5">
                        <span>Auto-terus / Auto-next</span>
                    </label>
                    <span id="progress-percent-text" class="font-bold text-emerald-700">0% Selesai</span>
                </div>
            </div>
            <div class="w-full bg-slate-200 h-1.5 overflow-hidden">
                <div id="progress-bar-fill" class="bg-gradient-to-r from-[#1a237e] via-indigo-600 to-emerald-500 h-full transition-all duration-500 ease-out" style="width: 0%"></div>
            </div>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-grow flex items-center justify-center px-4 sm:px-6 py-6 sm:py-10">
        <div id="app-container" class="w-full max-w-3xl">
            <!-- Dynamic Screen Content Injected Here -->
        </div>
    </main>

    <!-- Footer -->
    <footer class="border-t border-slate-200/80 bg-white/80 backdrop-blur-sm py-4 px-4 text-xs text-slate-600">
        <div class="max-w-5xl mx-auto flex flex-col md:flex-row items-center justify-between gap-2 text-center md:text-left">
            <div>
                <p>© 2026 Penyelidikan PhD • <strong>Adib Farhan bin Zaime</strong> | Penyelia: <strong>Prof. Ts. Dr. Lai Chee Sern</strong></p>
                <p class="text-[11px] text-slate-500">Fakulti Pendidikan Teknikal & Vokasional (FPTV), <strong>Universiti Tun Hussein Onn Malaysia (UTHM)</strong></p>
            </div>
            <div class="flex flex-wrap items-center justify-center gap-3">
                <button type="button" onclick="toggleInfoModal(true)" class="text-[#1a237e] hover:underline font-semibold transition">Hubungi Penyelidik</button>
                <span class="text-slate-300">|</span>
                <button type="button" onclick="toggleSheetModal(true)" class="text-emerald-700 hover:underline font-semibold transition">Tetapan Google Sheet</button>
                <span class="text-slate-300">|</span>
                <button type="button" onclick="toggleResearcherTools(true)" class="text-slate-500 hover:text-[#1a237e] underline transition">Alat Penyelidik / Data</button>
                <span class="text-slate-300">|</span>
                <span id="save-status" class="text-emerald-600 font-medium flex items-center gap-1">
                    <span class="w-1.5 h-1.5 rounded-full bg-emerald-500"></span> Tersimpan Automatik
                </span>
            </div>
        </div>
    </footer>

    <!-- Question Navigator Drawer -->
    <div id="nav-drawer-overlay" class="fixed inset-0 z-50 hidden bg-slate-900/40 backdrop-blur-xs transition-opacity" onclick="toggleDrawer(false)">
        <div class="absolute right-0 top-0 bottom-0 w-full max-w-md bg-white shadow-2xl border-l border-slate-200 flex flex-col" onclick="event.stopPropagation()">
            <div class="p-4 border-b border-slate-200 flex items-center justify-between bg-slate-50">
                <div>
                    <h3 class="font-display font-bold text-slate-900 text-base">Peta Soalan / Question Navigator</h3>
                    <p class="text-xs text-slate-500">Klik mana-mana nombor untuk melompat terus ke soalan tersebut.</p>
                </div>
                <button onclick="toggleDrawer(false)" class="p-2 rounded-xl hover:bg-slate-200 text-slate-600">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
                </button>
            </div>
            <div class="p-3 bg-white border-b border-slate-100 flex flex-wrap gap-2 text-[11px] font-medium">
                <span class="inline-flex items-center gap-1"><span class="w-2.5 h-2.5 rounded-full bg-[#1a237e]"></span> Semasa</span>
                <span class="inline-flex items-center gap-1"><span class="w-2.5 h-2.5 rounded-full bg-emerald-500"></span> Dijawab</span>
                <span class="inline-flex items-center gap-1"><span class="w-2.5 h-2.5 rounded-full bg-slate-200"></span> Belum Dijawab</span>
            </div>
            <div id="drawer-questions-list" class="p-4 overflow-y-auto flex-grow space-y-5">
                <!-- Populated dynamically -->
            </div>
        </div>
    </div>

    <!-- Researcher & Supervisor Info Modal -->
    <div id="info-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/50 backdrop-blur-xs" onclick="toggleInfoModal(false)">
        <div class="bg-white rounded-3xl max-w-xl w-full p-6 sm:p-7 shadow-2xl border border-slate-200 slide-enter max-h-[90vh] overflow-y-auto" onclick="event.stopPropagation()">
            <div class="flex items-start justify-between gap-4 border-b border-slate-100 pb-4">
                <div>
                    <span class="text-xs font-bold uppercase tracking-wider text-emerald-700 bg-emerald-50 px-2.5 py-1 rounded-lg border border-emerald-200">Maklumat Penyelidikan • UTHM</span>
                    <h3 class="font-display font-bold text-lg text-slate-900 mt-2">Sebarang Pertanyaan / For Any Inquiries</h3>
                    <p class="text-xs text-slate-500 mt-0.5">Sila hubungi penyelidik atau penyelia utama melalui butiran rasmi di bawah:</p>
                </div>
                <button onclick="toggleInfoModal(false)" class="p-2 rounded-xl hover:bg-slate-100 text-slate-500">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
                </button>
            </div>
            <div class="mt-4 space-y-4 text-sm">
                <!-- Penyelidik / Pelajar PhD -->
                <div class="p-4 sm:p-5 rounded-2xl bg-slate-50 border border-slate-200">
                    <div class="flex items-center justify-between gap-2">
                        <span class="text-[11px] font-bold uppercase tracking-wider text-indigo-700 bg-indigo-100/80 px-2.5 py-0.5 rounded-md">1) Penyelidik / Calon PhD</span>
                        <span class="text-[11px] font-semibold text-slate-500">UTHM</span>
                    </div>
                    <p class="font-display font-bold text-slate-900 text-base sm:text-lg mt-2">Adib Farhan bin Zaime</p>
                    <p class="text-slate-600 text-xs mt-1 leading-relaxed">
                        Pelajar Separuh Masa Program Doktor Falsafah Pendidikan Teknik dan Vokasional (PhD in Technical and Vocational Education), Universiti Tun Hussein Onn Malaysia (UTHM)
                    </p>
                    <div class="mt-3 pt-3 border-t border-slate-200/80 flex flex-wrap gap-2 text-xs">
                        <a href="tel:+60136502508" class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-white border border-slate-200 hover:border-indigo-300 text-slate-800 font-semibold transition">
                            <span>📞</span> +60 13 650 2508
                        </a>
                        <a href="https://wa.me/60136502508" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-emerald-50 border border-emerald-200 hover:bg-emerald-100 text-emerald-800 font-semibold transition">
                            <span>💬</span> WhatsApp
                        </a>
                        <a href="mailto:adibfarhanzaime@gmail.com" class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-indigo-50 border border-indigo-200 hover:bg-indigo-100 text-[#1a237e] font-semibold transition">
                            <span>✉️</span> adibfarhanzaime@gmail.com
                        </a>
                    </div>
                </div>

                <!-- Penyelia Utama -->
                <div class="p-4 sm:p-5 rounded-2xl bg-indigo-50/50 border border-indigo-100">
                    <div class="flex items-center justify-between gap-2">
                        <span class="text-[11px] font-bold uppercase tracking-wider text-emerald-800 bg-emerald-100 px-2.5 py-0.5 rounded-md">2) Penyelia Utama / Supervisor</span>
                        <span class="text-[11px] font-semibold text-slate-500">FPTV • UTHM</span>
                    </div>
                    <p class="font-display font-bold text-slate-900 text-base sm:text-lg mt-2">Prof. Ts. Dr. Lai Chee Sern</p>
                    <p class="text-slate-600 text-xs mt-1 leading-relaxed">
                        Pensyarah Kanan / Senior Lecturer, Fakulti Pendidikan Teknikal & Vokasional (FPTV), Universiti Tun Hussein Onn Malaysia (UTHM)
                    </p>
                    <div class="mt-3 pt-3 border-t border-indigo-100 flex flex-wrap gap-2 text-xs">
                        <a href="tel:+60125768327" class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-white border border-indigo-200 hover:border-indigo-400 text-slate-800 font-semibold transition">
                            <span>📞</span> +60 12 576 8327
                        </a>
                        <a href="https://wa.me/60125768327" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-emerald-50 border border-emerald-200 hover:bg-emerald-100 text-emerald-800 font-semibold transition">
                            <span>💬</span> WhatsApp
                        </a>
                        <a href="mailto:lcsern@uthm.edu.my" class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-xl bg-white border border-indigo-200 hover:bg-indigo-100 text-[#1a237e] font-semibold transition">
                            <span>✉️</span> lcsern@uthm.edu.my
                        </a>
                    </div>
                </div>
            </div>
            <div class="mt-6 flex justify-end">
                <button onclick="toggleInfoModal(false)" class="px-5 py-2.5 rounded-xl bg-[#1a237e] hover:bg-indigo-900 text-white text-sm font-semibold transition">Tutup / Close</button>
            </div>
        </div>
    </div>

    <!-- Google Sheet Connection Modal -->
    <div id="sheet-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/50 backdrop-blur-xs" onclick="toggleSheetModal(false)">
        <div class="bg-white rounded-3xl max-w-2xl w-full p-6 sm:p-7 shadow-2xl border border-slate-200 slide-enter max-h-[92vh] overflow-y-auto" onclick="event.stopPropagation()">
            <div class="flex items-start justify-between gap-4 border-b border-slate-100 pb-4">
                <div>
                    <span class="text-xs font-bold uppercase tracking-wider text-emerald-700 bg-emerald-50 px-2.5 py-1 rounded-lg border border-emerald-200">Integrasi Pangkalan Data</span>
                    <h3 class="font-display font-bold text-lg text-slate-900 mt-2">Tetapan Sambungan Google Sheet (Apps Script)</h3>
                    <p class="text-xs text-slate-500 mt-0.5">Setiap jawapan responden akan dihantar terus ke baris baharu Google Sheet anda secara automatik.</p>
                </div>
                <button onclick="toggleSheetModal(false)" class="p-2 rounded-xl hover:bg-slate-100 text-slate-500">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
                </button>
            </div>

            <!-- Tabs: Konfigurasi URL vs Panduan Apps Script -->
            <div class="mt-4 flex gap-2 border-b border-slate-200 pb-2">
                <button type="button" onclick="switchSheetTab('config')" id="sheet-tab-btn-config" class="px-3.5 py-1.5 rounded-xl bg-[#1a237e] text-white text-xs font-bold transition">1. Konfigurasi Web App URL</button>
                <button type="button" onclick="switchSheetTab('guide')" id="sheet-tab-btn-guide" class="px-3.5 py-1.5 rounded-xl bg-slate-100 text-slate-700 hover:bg-slate-200 text-xs font-bold transition">2. Salin Kod Apps Script (Code.gs)</button>
            </div>

            <!-- Tab 1: Config URL -->
            <div id="sheet-tab-config" class="mt-4 space-y-4">
                <div class="p-3.5 rounded-2xl bg-slate-50 border border-slate-200 flex items-center justify-between gap-3">
                    <div class="text-xs">
                        <span class="text-slate-500 font-medium">Status Sambungan Semasa:</span>
                        <p id="sheet-modal-status-text" class="font-bold text-amber-700 mt-0.5">Belum Dikonfigurasi (Simpanan Tempatan & CSV Sahaja)</p>
                    </div>
                    <span id="sheet-modal-badge" class="px-2.5 py-1 rounded-lg bg-amber-100 text-amber-800 text-[11px] font-bold">Offline / Tempatan</span>
                </div>

                <div>
                    <label for="google-script-url-input" class="block text-xs font-bold text-slate-700 mb-1.5">
                        Google Apps Script Web App URL (<code class="text-indigo-700">https://script.google.com/macros/s/.../exec</code>):
                    </label>
                    <input type="url" id="google-script-url-input" placeholder="https://script.google.com/macros/s/AKfycbx.../exec"
                        class="w-full px-3.5 py-3 rounded-xl border-2 border-slate-200 focus:border-[#1a237e] focus:ring-4 focus:ring-indigo-100 outline-none text-xs sm:text-sm font-mono text-slate-800" />
                    <p class="text-[11px] text-slate-500 mt-1.5">
                        💡 <strong>Nota Domain MOE-DL:</strong> Memandangkan skrip ini dihoskan di bawah domain <code>moe-dl.edu.my</code>, sila pastikan tetapan <em>Who has access</em> semasa Deploy Web App dipilih sebagai <strong>Anyone (Sesiapa sahaja)</strong> supaya pensyarah/responden yang menggunakan e-mel peribadi atau tanpa log masuk MOE tetap dapat menghantar jawapan tanpa sekatan kebenaran.
                    </p>
                </div>

                <div class="flex flex-wrap items-center justify-between gap-2 pt-2">
                    <button type="button" onclick="testGoogleSheetConnection()" id="btn-test-sheet" class="px-4 py-2.5 rounded-xl bg-indigo-50 hover:bg-indigo-100 text-[#1a237e] border border-indigo-200 text-xs font-bold transition flex items-center gap-1.5">
                        <span>🔌</span> Uji Sambungan (Hantar Isyarat Ujian)
                    </button>
                    <div class="flex items-center gap-2">
                        <button type="button" onclick="clearGoogleSheetUrl()" class="px-3.5 py-2.5 rounded-xl bg-rose-50 hover:bg-rose-100 text-rose-700 text-xs font-semibold transition">
                            Padam URL
                        </button>
                        <button type="button" onclick="saveGoogleSheetUrl()" class="px-5 py-2.5 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-bold shadow-sm transition">
                            Simpan Tetapan URL
                        </button>
                    </div>
                </div>
            </div>

            <!-- Tab 2: Copy Apps Script Code Guide -->
            <div id="sheet-tab-guide" class="hidden mt-4 space-y-3">
                <ol class="list-decimal list-inside text-xs text-slate-700 space-y-1.5 bg-indigo-50/60 p-3.5 rounded-2xl border border-indigo-100">
                    <li>Buka Google Sheet anda &rarr; klik <strong>Extensions &gt; Apps Script</strong>.</li>
                    <li>Salin kod di bawah dan tampal ke dalam editor <code>Code.gs</code>, kemudian tekan <strong>Save</strong>.</li>
                    <li>Klik <strong>Deploy &gt; New deployment &gt; Web app</strong>.</li>
                    <li>Tetapkan <em>Execute as:</em> <strong>Me</strong> dan <em>Who has access:</em> <strong>Anyone</strong>, lalu klik <strong>Deploy</strong>.</li>
                    <li>Salin <strong>Web app URL</strong> yang terhasil dan tampal pada Tab 1 di sebelah.</li>
                </ol>
                <div class="relative">
                    <button type="button" onclick="copyAppsScriptSnippet()" class="absolute top-2.5 right-2.5 px-3 py-1.5 rounded-lg bg-[#1a237e] hover:bg-indigo-900 text-white text-[11px] font-bold shadow-sm transition">
                        📋 Salin Kod Apps Script
                    </button>
                    <textarea id="apps-script-code-preview" readonly rows="9" class="w-full p-3.5 pt-11 rounded-2xl bg-slate-900 text-emerald-300 font-mono text-[11px] leading-relaxed border border-slate-700 outline-none"></textarea>
                </div>
            </div>
        </div>
    </div>

    <!-- Researcher Tools Modal (Export / Demo / Reset) -->
    <div id="tools-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/50 backdrop-blur-xs" onclick="toggleResearcherTools(false)">
        <div class="bg-white rounded-3xl max-w-md w-full p-6 shadow-2xl border border-slate-200 slide-enter" onclick="event.stopPropagation()">
            <div class="flex items-center justify-between border-b border-slate-100 pb-3">
                <h3 class="font-display font-bold text-base text-slate-900">Panel Kawalan Penyelidik (PhD Tools)</h3>
                <button onclick="toggleResearcherTools(false)" class="p-1.5 rounded-xl hover:bg-slate-100 text-slate-500">✕</button>
            </div>
            <p class="text-xs text-slate-600 mt-3 leading-relaxed">
                Gunakan alatan di bawah untuk memuat turun data responden dalam format CSV (sedia untuk SPSS / SmartPLS / Excel), menguji aliran soal selidik, atau menetapkan semula borang.
            </p>
            <div class="mt-4 space-y-2.5">
                <button onclick="exportCSV(); toggleResearcherTools(false);" class="w-full py-2.5 px-4 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-sm font-semibold flex items-center justify-center gap-2 transition shadow-sm">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"/></svg>
                    Muat Turun Data CSV (SPSS / Excel)
                </button>
                <button onclick="fillDemoData(); toggleResearcherTools(false);" class="w-full py-2.5 px-4 rounded-xl bg-indigo-50 hover:bg-indigo-100 text-[#1a237e] border border-indigo-200 text-sm font-semibold flex items-center justify-center gap-2 transition">
                    <span>⚡</span> Isi Data Simulasi (Mod Ujian Pantas)
                </button>
                <button onclick="requestResetSurvey();" class="w-full py-2.5 px-4 rounded-xl bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 text-sm font-semibold flex items-center justify-center gap-2 transition">
                    <span>🗑️</span> Padam & Mula Semula Soal Selidik
                </button>
            </div>
            <div id="reset-confirm-box" class="hidden mt-3 p-3 rounded-xl bg-rose-50 border border-rose-200 text-xs text-rose-800">
                <p class="font-semibold mb-2">Adakah anda pasti mahu memadam semua jawapan semasa?</p>
                <div class="flex gap-2">
                    <button onclick="confirmResetSurvey()" class="px-3 py-1.5 bg-rose-600 text-white rounded-lg font-semibold">Ya, Padam</button>
                    <button onclick="document.getElementById('reset-confirm-box').classList.add('hidden')" class="px-3 py-1.5 bg-white border border-slate-300 rounded-lg font-semibold text-slate-700">Batal</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Custom Toast Notification -->
    <div id="toast-box" class="fixed bottom-5 left-1/2 -translate-x-1/2 z-50 hidden items-center gap-2 px-4 py-2.5 rounded-2xl bg-slate-900 text-white text-xs font-medium shadow-xl border border-slate-700">
        <span id="toast-icon">✅</span>
        <span id="toast-msg">Tindakan berjaya</span>
    </div>

    <script>
        // =========================================================================
        // 0. KONFIGURASI GOOGLE APPS SCRIPT (DISAMBUNGKAN SECARA KEKAL)
        // =========================================================================
        const DEFAULT_GOOGLE_SCRIPT_URL = "https://script.google.com/a/macros/moe-dl.edu.my/s/AKfycbyWuV7Ji6uGdOC9Jla6pXe5VjiQ7OmkRlCdyej9Xf1A2sak7UBf0fW_gi54EtKXf2PDGw/exec";
        const SHEET_URL_STORAGE_KEY = 'uthm_phd_google_script_url_v1';

        const APPS_SCRIPT_TEMPLATE_CODE = `const SHEET_NAME = "Data_Soal_Selidik";
const HEADERS = [
  "ID_Responden", "Tarikh_Masa_Hantar",
  "A1_Jantina", "A2_Umur", "A3_Pendidikan", "A4_Pengalaman_Mengajar", "A5_Subjek_Modul_Utama", "A6_Kolej_Vokasional",
  "BA_1_0", "BA_1_1", "BA_1_2", "BA_1_3", "BA_1_4", "BA_1_5", "BA_1_6",
  "BA_2_0", "BA_2_1", "BA_2_2", "BA_2_3", "BA_2_4", "BA_Terbuka",
  "BB_1_0", "BB_1_1", "BB_1_2", "BB_1_3", "BB_1_4",
  "BB_2_0", "BB_2_1", "BB_2_2", "BB_2_3", "BB_2_4",
  "BB_3_0", "BB_3_1", "BB_3_2", "BB_3_3", "BB_3_4", "BB_3_5",
  "BB_4_0", "BB_4_1", "BB_4_2", "BB_4_3", "BB_4_4", "BB_4_5", "BB_4_6", "BB_4_7",
  "BB_5_0", "BB_5_1", "BB_5_2", "BB_5_3", "BB_5_4", "BB_5_5",
  "BB_6_0", "BB_6_1", "BB_6_2", "BB_6_3", "BB_6_4", "BB_6_5",
  "BB_7_0", "BB_7_1", "BB_7_2", "BB_7_3", "BB_7_4", "BB_7_5", "BB_7_6",
  "BB_8_0", "BB_8_1", "BB_8_2", "BB_8_3", "BB_8_4", "BB_8_5", "BB_Terbuka",
  "BC_1_0", "BC_1_1", "BC_1_2", "BC_1_3", "BC_1_4", "BC_1_5",
  "BC_2_0", "BC_2_1", "BC_2_2", "BC_2_3", "BC_2_4", "BC_2_5", "BC_Terbuka",
  "Min_Bahagian_A_Pengetahuan", "Min_Bahagian_B_Kemahiran", "Min_Bahagian_C_Sikap_Nilai", "Min_Keseluruhan"
];

function doPost(e) {
  const lock = LockService.getScriptLock();
  lock.tryLock(15000);
  try {
    const ss = SpreadsheetApp.getActiveSpreadsheet();
    let sheet = ss.getSheetByName(SHEET_NAME) || ss.getSheets()[0];
    if (sheet.getLastRow() === 0) {
      sheet.appendRow(HEADERS);
      sheet.getRange(1, 1, 1, HEADERS.length).setFontWeight("bold").setBackground("#1a237e").setFontColor("#ffffff");
      sheet.setFrozenRows(1);
    }
    const data = JSON.parse(e.postData.contents || "{}");
    if (data._action === "TEST_CONNECTION") {
      return ContentService.createTextOutput(JSON.stringify({ status: "ok" })).setMimeType(ContentService.MimeType.JSON);
    }
    const row = HEADERS.map(k => data[k] !== undefined && data[k] !== null ? data[k] : "");
    sheet.appendRow(row);
    return ContentService.createTextOutput(JSON.stringify({ status: "success", id: data.ID_Responden })).setMimeType(ContentService.MimeType.JSON);
  } catch (err) {
    return ContentService.createTextOutput(JSON.stringify({ status: "error", message: err.toString() })).setMimeType(ContentService.MimeType.JSON);
  } finally {
    lock.releaseLock();
  }
}`;

        function getActiveScriptUrl() {
            const savedUrl = localStorage.getItem(SHEET_URL_STORAGE_KEY);
            if (savedUrl && savedUrl.trim() !== '') return savedUrl.trim();
            return (DEFAULT_GOOGLE_SCRIPT_URL || '').trim();
        }

        function updateSheetConnectionIndicator() {
            const url = getActiveScriptUrl();
            const dot = document.getElementById('sheet-status-dot');
            const headerLabel = document.getElementById('sheet-header-label');
            const modalText = document.getElementById('sheet-modal-status-text');
            const modalBadge = document.getElementById('sheet-modal-badge');

            if (url) {
                if (dot) dot.className = 'w-2 h-2 rounded-full bg-emerald-500 shrink-0';
                if (headerLabel) headerLabel.textContent = 'Google Sheet Aktif';
                if (modalText) {
                    modalText.className = 'font-bold text-emerald-700 mt-0.5 break-all';
                    modalText.textContent = 'Aktif & Disambungkan ke Google Apps Script (moe-dl.edu.my)';
                }
                if (modalBadge) {
                    modalBadge.className = 'px-2.5 py-1 rounded-lg bg-emerald-100 text-emerald-800 text-[11px] font-bold shrink-0';
                    modalBadge.textContent = '● Bersambung';
                }
            } else {
                if (dot) dot.className = 'w-2 h-2 rounded-full bg-amber-500 shrink-0';
                if (headerLabel) headerLabel.textContent = 'Google Sheet';
                if (modalText) {
                    modalText.className = 'font-bold text-amber-700 mt-0.5';
                    modalText.textContent = 'Belum Dikonfigurasi (Simpanan Tempatan & CSV Sahaja)';
                }
                if (modalBadge) {
                    modalBadge.className = 'px-2.5 py-1 rounded-lg bg-amber-100 text-amber-800 text-[11px] font-bold shrink-0';
                    modalBadge.textContent = 'Tempatan';
                }
            }
        }

        // =========================================================================
        // 1. COMPLETE SURVEY DATA STRUCTURE (ALL ITEMS FROM DOCX)
        // =========================================================================
        const SURVEY_ITEMS = [
            // --- SEKSYEN A: DEMOGRAFI ---
            {
                id: 'D1',
                section: 'Seksyen A',
                sectionTitleBm: 'Seksyen A: Demografi Responden',
                sectionTitleEn: 'Section A: Respondent Demographics',
                subConstructBm: 'Maklumat Latar Belakang',
                subConstructEn: 'Background Information',
                type: 'radio',
                required: true,
                bm: '1. Jantina',
                en: '1. Gender',
                options: [
                    { value: 'Lelaki / Male', bm: 'Lelaki', en: 'Male' },
                    { value: 'Perempuan / Female', bm: 'Perempuan', en: 'Female' }
                ]
            },
            {
                id: 'D2',
                section: 'Seksyen A',
                sectionTitleBm: 'Seksyen A: Demografi Responden',
                sectionTitleEn: 'Section A: Respondent Demographics',
                subConstructBm: 'Maklumat Latar Belakang',
                subConstructEn: 'Background Information',
                type: 'radio',
                required: true,
                bm: '2. Umur',
                en: '2. Age',
                options: [
                    { value: '23-32 tahun', bm: '23-32 tahun', en: '23-32 years old' },
                    { value: '33-42 tahun', bm: '33-42 tahun', en: '33-42 years old' },
                    { value: '43-52 tahun', bm: '43-52 tahun', en: '43-52 years old' },
                    { value: '53 tahun & ke atas', bm: '53 tahun & ke atas', en: '53 years old & above' }
                ]
            },
            {
                id: 'D3',
                section: 'Seksyen A',
                sectionTitleBm: 'Seksyen A: Demografi Responden',
                sectionTitleEn: 'Section A: Respondent Demographics',
                subConstructBm: 'Maklumat Latar Belakang',
                subConstructEn: 'Background Information',
                type: 'radio',
                required: true,
                bm: '3. Tahap Pendidikan Tertinggi',
                en: '3. Highest Education Level',
                options: [
                    { value: 'Diploma / DKM', bm: 'Diploma / Diploma Kemahiran Malaysia', en: 'Diploma / Malaysian Skills Diploma' },
                    { value: 'DLKM', bm: 'Diploma Lanjutan Kemahiran Malaysia', en: 'Malaysian Advanced Skills Diploma' },
                    { value: 'Sarjana Muda / Bachelor', bm: 'Sarjana Muda', en: 'Bachelor’s Degree' },
                    { value: 'Sarjana / Master', bm: 'Sarjana', en: 'Master’s Degree' },
                    { value: 'Doktor Falsafah / PhD', bm: 'Doktor Falsafah (PhD)', en: 'Doctor of Philosophy (PhD)' }
                ]
            },
            {
                id: 'D4',
                section: 'Seksyen A',
                sectionTitleBm: 'Seksyen A: Demografi Responden',
                sectionTitleEn: 'Section A: Respondent Demographics',
                subConstructBm: 'Maklumat Latar Belakang',
                subConstructEn: 'Background Information',
                type: 'radio',
                required: true,
                bm: '4. Pengalaman Mengajar',
                en: '4. Teaching Experience',
                options: [
                    { value: '0-5 tahun', bm: '0-5 tahun', en: '0-5 years' },
                    { value: '6-10 tahun', bm: '6-10 tahun', en: '6-10 years' },
                    { value: '11 tahun & ke atas', bm: '11 tahun & ke atas', en: '11 years & above' }
                ]
            },
            {
                id: 'D5',
                section: 'Seksyen A',
                sectionTitleBm: 'Seksyen A: Demografi Responden',
                sectionTitleEn: 'Section A: Respondent Demographics',
                subConstructBm: 'Maklumat Latar Belakang',
                subConstructEn: 'Background Information',
                type: 'text',
                required: true,
                bm: '5. Subjek atau Modul Utama yang Diajar',
                en: '5. Main Subjects or Modules Taught',
                placeholderBm: 'Contoh: Teknologi Elektronik, Sistem Kawalan, Reka Bentuk PCB...',
                placeholderEn: 'Example: Electronic Technology, Control Systems, PCB Design...'
            },
            {
                id: 'D6',
                section: 'Seksyen A',
                sectionTitleBm: 'Seksyen A: Demografi Responden',
                sectionTitleEn: 'Section A: Respondent Demographics',
                subConstructBm: 'Maklumat Latar Belakang',
                subConstructEn: 'Background Information',
                type: 'text',
                required: true,
                bm: '6. Nama Kolej Vokasional',
                en: '6. Vocational College Name',
                placeholderBm: 'Contoh: Kolej Vokasional Batu Pahat',
                placeholderEn: 'Example: Batu Pahat Vocational College'
            },

            // --- SEKSYEN B - BAHAGIAN A: ELEMEN PENGETAHUAN ---
            // Sub-construct 1.0
            {
                id: 'A_1.0', code: '1.0', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan Teknologi Hijau Elektronik',
                en: 'Knowledge of Green Electronic Technology'
            },
            {
                id: 'A_1.1', code: '1.1', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang teknologi hijau dalam bidang elektronik (seperti sistem solar fotovolta, penyongsang, dan pengurusan bateri).',
                en: 'Knowledge of green technology in the electronics field (such as solar photovoltaic systems, inverters, and battery management).'
            },
            {
                id: 'A_1.2', code: '1.2', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang pembangunan dan reka bentuk produk teknologi hijau dalam bidang elektronik.',
                en: 'Knowledge of green technology product development and design in electronics.'
            },
            {
                id: 'A_1.3', code: '1.3', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang aplikasi produk teknologi hijau dalam bidang elektronik (seperti ESP32, dan papan litar PCB bebas plumbum).',
                en: 'Knowledge of the application of green technology products in the field of electronics (such as ESP32 and lead-free PCBs).'
            },
            {
                id: 'A_1.4', code: '1.4', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang penyelenggaraan dan ujian kualiti bagi produk teknologi hijau elektronik.',
                en: 'Knowledge of maintenance and testing for green electronic products.'
            },
            {
                id: 'A_1.5', code: '1.5', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang penggunaan peralatan pengujian dan pengukuran teknologi hijau dalam bidang elektronik.',
                en: 'Knowledge of using green technology testing and measurement equipment in electronics.'
            },
            {
                id: 'A_1.6', code: '1.6', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '1.0 Pengetahuan Teknologi Hijau Elektronik',
                subConstructEn: '1.0 Knowledge of Green Electronic Technology',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang sistem dan seni bina teknologi hijau industri yang diguna pakai dalam bidang elektronik.',
                en: 'Knowledge of industry-applied green technology systems and architecture in electronics.'
            },
            // Sub-construct 2.0
            {
                id: 'A_2.0', code: '2.0', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
                subConstructEn: '2.0 Knowledge of Electronic Waste (E-Waste) and Waste Material Management',
                type: 'likert', required: true,
                bm: 'Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
                en: 'Knowledge of Electronic Waste (E-Waste) and Waste Material Management'
            },
            {
                id: 'A_2.1', code: '2.1', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
                subConstructEn: '2.0 Knowledge of Electronic Waste (E-Waste) and Waste Material Management',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang pengurusan dan sifat bahan berbahaya dalam sisa elektronik (seperti pateri plumbum, kadmium, dan elektrolit bateri).',
                en: 'Knowledge of management and characteristics of hazardous materials in e-waste (such as lead solder, cadmium, and battery electrolytes).'
            },
            {
                id: 'A_2.2', code: '2.2', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
                subConstructEn: '2.0 Knowledge of Electronic Waste (E-Waste) and Waste Material Management',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang kaedah pelupusan sisa pepejal dan komponen elektronik terpakai secara selamat.',
                en: 'Knowledge of safe disposal methods for solid waste and used electronic components.'
            },
            {
                id: 'A_2.3', code: '2.3', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
                subConstructEn: '2.0 Knowledge of Electronic Waste (E-Waste) and Waste Material Management',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang aplikasi prinsip 5R (reduce, reuse, recycle, recover & refuse) dalam pengurusan bahan bengkel elektronik.',
                en: 'Knowledge of applying 5R principles (reduce, reuse, recycle, recover & refuse) in managing electronics workshop materials.'
            },
            {
                id: 'A_2.4', code: '2.4', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: '2.0 Pengetahuan Pengurusan Sisa Elektronik dan Bahan Buangan',
                subConstructEn: '2.0 Knowledge of Electronic Waste (E-Waste) and Waste Material Management',
                type: 'likert', required: true,
                bm: 'Pengetahuan tentang pengasingan sisa bahan buangan dan komponen elektronik yang rosak.',
                en: 'Knowledge of segregation of waste materials and defective electronic components.'
            },
            {
                id: 'A_OPEN', code: 'Terbuka A', part: 'A',
                section: 'Bahagian A',
                sectionTitleBm: 'Seksyen B • Bahagian A: Elemen Pengetahuan',
                sectionTitleEn: 'Section B • Part A: Knowledge Element',
                subConstructBm: 'Soalan Terbuka Bahagian A (Pilihan)',
                subConstructEn: 'Open-ended Question Part A (Optional)',
                type: 'textarea', required: false,
                bm: 'Apakah elemen pengetahuan kemahiran hijau lain yang penting tetapi tidak tersenarai di atas?',
                en: 'What other green skills knowledge elements are important but not listed above?',
                placeholderBm: 'Nyatakan cadangan tambahan anda di sini (jika ada), atau klik Seterusnya untuk ke Bahagian B...',
                placeholderEn: 'State your additional suggestions here (if any), or click Next to proceed to Part B...'
            },

            // --- SEKSYEN B - BAHAGIAN B: ELEMEN KEMAHIRAN ---
            // Sub-construct 1.0
            {
                id: 'B_1.0', code: '1.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
                subConstructEn: '1.0 Electronic Waste (E-Waste) Management Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran Pengurusan Sisa Buangan Elektronik',
                en: 'Electronic Waste (E-Waste) Management Skills'
            },
            {
                id: 'B_1.1', code: '1.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
                subConstructEn: '1.0 Electronic Waste (E-Waste) Management Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengurangkan pembaziran bahan semasa proses pematerian dan pembuatan papan litar bercetak (PCB).',
                en: 'Skills in reducing material waste during soldering and PCB fabrication/assembly.'
            },
            {
                id: 'B_1.2', code: '1.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
                subConstructEn: '1.0 Electronic Waste (E-Waste) Management Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran menggunakan semula komponen elektronik yang masih berfungsi.',
                en: 'Skill in reusing functional electronic components.'
            },
            {
                id: 'B_1.3', code: '1.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
                subConstructEn: '1.0 Electronic Waste (E-Waste) Management Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengitar semula sisa logam dan komponen elektronik terpakai.',
                en: 'Skills in recycling scrap metal and used electronic components.'
            },
            {
                id: 'B_1.4', code: '1.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '1.0 Kemahiran Pengurusan Sisa Buangan Elektronik',
                subConstructEn: '1.0 Electronic Waste (E-Waste) Management Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran membaiki dan memulihkan peralatan elektronik yang rosak.',
                en: 'Skills in repairing and restoring damaged electronic equipment.'
            },
            // Sub-construct 2.0
            {
                id: 'B_2.0', code: '2.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
                subConstructEn: '2.0 Eco-Friendly Circuit and Electronic Device Design Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
                en: 'Eco-Friendly Circuit and Electronic Device Design Skills'
            },
            {
                id: 'B_2.1', code: '2.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
                subConstructEn: '2.0 Eco-Friendly Circuit and Electronic Device Design Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mereka bentuk litar elektronik berkecekapan tinggi dan berkuasa rendah (low-power design).',
                en: 'Skills in designing high-efficiency and low-power electronic circuits.'
            },
            {
                id: 'B_2.2', code: '2.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
                subConstructEn: '2.0 Eco-Friendly Circuit and Electronic Device Design Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mereka bentuk perkakasan elektronik mesra alam berteraskan perlindungan alam sekitar.',
                en: 'Skills in designing eco-friendly electronic hardware focused on environmental protection.'
            },
            {
                id: 'B_2.3', code: '2.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
                subConstructEn: '2.0 Eco-Friendly Circuit and Electronic Device Design Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mereka bentuk litar yang menekankan prinsip 5R (reduce, reuse, recycle, recover & refuse).',
                en: 'Skills in designing circuits that emphasize the 5R principles (reduce, reuse, recycle, recover, and refuse).'
            },
            {
                id: 'B_2.4', code: '2.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '2.0 Kemahiran Mereka Bentuk Litar dan Peranti Elektronik Mesra Alam',
                subConstructEn: '2.0 Eco-Friendly Circuit and Electronic Device Design Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengaplikasikan prinsip reka bentuk mampan dalam penghasilan produk elektronik.',
                en: 'Skills in applying design for sustainability principles in electronic product development.'
            },
            // Sub-construct 3.0
            {
                id: 'B_3.0', code: '3.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                subConstructEn: '3.0 Skills in the planning, management, and procurement of electronic equipment and components',
                type: 'likert', required: true,
                bm: 'Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                en: 'Skills in the planning, management, and procurement of electronic equipment and components.'
            },
            {
                id: 'B_3.1', code: '3.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                subConstructEn: '3.0 Skills in the planning, management, and procurement of electronic equipment and components',
                type: 'likert', required: true,
                bm: 'Kemahiran merancang projek elektronik berasaskan kelestarian alam sekitar.',
                en: 'Skills in planning environmentally sustainable electronic projects.'
            },
            {
                id: 'B_3.2', code: '3.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                subConstructEn: '3.0 Skills in the planning, management, and procurement of electronic equipment and components',
                type: 'likert', required: true,
                bm: 'Kemahiran memilih eko-bahan (seperti pateri bebas plumbum dan bahan PCB mesra alam).',
                en: 'Skills in selecting eco-materials (such as lead-free solder and eco-friendly PCB materials).'
            },
            {
                id: 'B_3.3', code: '3.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                subConstructEn: '3.0 Skills in the planning, management, and procurement of electronic equipment and components',
                type: 'likert', required: true,
                bm: 'Kemahiran pengurusan inventori komponen elektronik mesra alam (seperti penyimpanan berlabel, sistem FiFo dan kabinet pengering pintar).',
                en: 'Skills in eco-friendly electronic component inventory management (such as labeled storage, FiFo systems, and smart dry cabinets).'
            },
            {
                id: 'B_3.4', code: '3.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                subConstructEn: '3.0 Skills in the planning, management, and procurement of electronic equipment and components',
                type: 'likert', required: true,
                bm: 'Kemahiran perolehan mampan bagi peralatan elektronik (seperti kriteria pembungkusan hijau dan rantai bekalan mesra alam).',
                en: 'Skills in sustainable procurement for electronic equipment (such as green packaging criteria and eco-friendly supply chains).'
            },
            {
                id: 'B_3.5', code: '3.5', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '3.0 Kemahiran Perancangan, Pengurusan, dan Perolehan Alatan Komponen Elektronik',
                subConstructEn: '3.0 Skills in the planning, management, and procurement of electronic equipment and components',
                type: 'likert', required: true,
                bm: 'Kemahiran perolehan perkhidmatan penyelenggaraan elektronik mesra alam.',
                en: 'Skills in procuring eco-friendly electronic maintenance services.'
            },
            // Sub-construct 4.0
            {
                id: 'B_4.0', code: '4.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                en: 'Energy Saving and Electronic Power Efficiency Skills'
            },
            {
                id: 'B_4.1', code: '4.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengoptimumkan pengurusan tenaga dalam sistem dan peranti elektronik.',
                en: 'Skills in optimizing energy management in electronic systems and devices.'
            },
            {
                id: 'B_4.2', code: '4.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengaplikasikan peranti elektronik dalam sistem tenaga boleh baharu (seperti tenaga solar dan angin).',
                en: 'Skills in applying electronic devices to renewable energy systems (such as solar and wind energy).'
            },
            {
                id: 'B_4.3', code: '4.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran menganalisis kecekapan sistem pengurusan tenaga untuk mengurangkan pembaziran elektrik.',
                en: 'Skills in analyzing energy management system efficiency to minimize electrical waste.'
            },
            {
                id: 'B_4.4', code: '4.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengoptimumkan kualiti dan kecekapan kuasa litar.',
                en: 'Skills in optimizing circuit power quality and efficiency.'
            },
            {
                id: 'B_4.5', code: '4.5', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mereka bentuk sistem pengurusan haba litar bagi mengurangkan pelepasan haba.',
                en: 'Skills in designing circuit thermal management systems to reduce heat dissipation.'
            },
            {
                id: 'B_4.6', code: '4.6', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran kawalan dan pengurusan kualiti kuasa dalam sistem elektronik.',
                en: 'Skills in power quality control and management in electronic systems.'
            },
            {
                id: 'B_4.7', code: '4.7', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '4.0 Kemahiran Penjimatan Tenaga dan Kecekapan Kuasa Elektronik',
                subConstructEn: '4.0 Energy Saving and Electronic Power Efficiency Skills',
                type: 'likert', required: true,
                bm: 'Kemahiran mengintegrasikan sistem penuaian tenaga (seperti penderia piezoelektrik).',
                en: 'Skills in integrating energy harvesting systems (such as piezoelectric sensors).'
            },
            // Sub-construct 5.0
            {
                id: 'B_5.0', code: '5.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                subConstructEn: '5.0 Green Technology-Based Communication Skills in the Electronics Field',
                type: 'likert', required: true,
                bm: 'Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                en: 'Green Technology-Based Communication Skills in the Electronics Field'
            },
            {
                id: 'B_5.1', code: '5.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                subConstructEn: '5.0 Green Technology-Based Communication Skills in the Electronics Field',
                type: 'likert', required: true,
                bm: 'Kemahiran berkomunikasi secara digital tanpa kertas dalam pelaksanaan tugasan amali elektronik.',
                en: 'Skills in paperless digital communication during electronic practical tasks.'
            },
            {
                id: 'B_5.2', code: '5.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                subConstructEn: '5.0 Green Technology-Based Communication Skills in the Electronics Field',
                type: 'likert', required: true,
                bm: 'Kemahiran berkomunikasi menggunakan sistem ICT (Teknologi Maklumat dan Komunikasi) hijau (seperti e-mel).',
                en: 'Skills in communicating using green ICT (Information and Communications Technology) systems (such as email).'
            },
            {
                id: 'B_5.3', code: '5.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                subConstructEn: '5.0 Green Technology-Based Communication Skills in the Electronics Field',
                type: 'likert', required: true,
                bm: 'Kemahiran berkomunikasi dan mengawal peranti menggunakan sistem IoT (Internet Pelbagai Benda).',
                en: 'Skills in communicating and controlling devices using IoT (Internet of Things) systems.'
            },
            {
                id: 'B_5.4', code: '5.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                subConstructEn: '5.0 Green Technology-Based Communication Skills in the Electronics Field',
                type: 'likert', required: true,
                bm: 'Kemahiran mengaplikasikan platform komunikasi digital hibrid (seperti Google Meet dan Zoom) bagi mengurangkan pelepasan gas rumah hijau.',
                en: 'Skills in applying hybrid digital communication platforms, such as Google Meet and Zoom, to reduce greenhouse gas emissions.'
            },
            {
                id: 'B_5.5', code: '5.5', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '5.0 Kemahiran Komunikasi Berasaskan Teknologi Hijau Dalam Bidang Elektronik',
                subConstructEn: '5.0 Green Technology-Based Communication Skills in the Electronics Field',
                type: 'likert', required: true,
                bm: 'Kemahiran mengendalikan pemantauan data litar secara jarak jauh menggunakan aplikasi pengkomputeran awan mesra tenaga.',
                en: 'Skills in remote circuit data monitoring using energy-efficient cloud computing applications.'
            },
            // Sub-construct 6.0
            {
                id: 'B_6.0', code: '6.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                subConstructEn: '6.0 Teamwork Skills for Green Practices in Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                en: 'Teamwork Skills for Green Practices in Electronics'
            },
            {
                id: 'B_6.1', code: '6.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                subConstructEn: '6.0 Teamwork Skills for Green Practices in Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran kerja berpasukan memastikan setiap ahli menyumbang secara aktif kepada amalan hijau di makmal atau bengkel.',
                en: 'Skills in teamwork to ensure every member actively contributes to green practices in the laboratory or workshop.'
            },
            {
                id: 'B_6.2', code: '6.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                subConstructEn: '6.0 Teamwork Skills for Green Practices in Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran berkolaborasi dengan pihak luar/industri bagi menyokong aktiviti pencegahan pencemaran alam sekitar.',
                en: 'Skills in collaborating with external parties/industry to support environmental pollution prevention activities.'
            },
            {
                id: 'B_6.3', code: '6.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                subConstructEn: '6.0 Teamwork Skills for Green Practices in Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran perhubungan pasukan secara segerak (seperti persidangan video atau audio) bagi mencegah pencemaran alam sekitar.',
                en: 'Skills in synchronous team communication (such as video or audio conferencing) to prevent environmental pollution.'
            },
            {
                id: 'B_6.4', code: '6.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                subConstructEn: '6.0 Teamwork Skills for Green Practices in Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran memahami peranan ahli pasukan berasaskan keperluan teknikal bagi mencegah pencemaran alam sekitar.',
                en: 'Skills in understanding team members\' roles based on technical requirements to prevent environmental pollution.'
            },
            {
                id: 'B_6.5', code: '6.5', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '6.0 Kemahiran Kerja Berpasukan dalam Amalan Hijau Dalam Bidang Elektronik',
                subConstructEn: '6.0 Teamwork Skills for Green Practices in Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran mengkoordinasi peranan ahli pasukan bagi meminimumkan pembaziran komponen dan bahan amali.',
                en: 'Skills in coordinating team roles to minimize component and practical material waste.'
            },
            // Sub-construct 7.0
            {
                id: 'B_7.0', code: '7.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                en: 'Problem-Solving and Creative Thinking Skills in Green Electronics'
            },
            {
                id: 'B_7.1', code: '7.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran menyelesaikan masalah kegagalan litar yang mengambil kira pengurangan impak negatif alam sekitar.',
                en: 'Skills in solving circuit failure problems taking into account environmental impact reduction.'
            },
            {
                id: 'B_7.2', code: '7.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran berfikir secara kritis dalam mereka bentuk peranti elektronik mesra alam.',
                en: 'Critical thinking skills in designing eco-friendly electronic devices.'
            },
            {
                id: 'B_7.3', code: '7.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran berfikir secara strategik bagi mengurangkan jejak karbon (carbon footprint) produk elektronik.',
                en: 'Skills in strategic thinking to reduce the carbon footprint of electronic products.'
            },
            {
                id: 'B_7.4', code: '7.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran berfikir secara terbuka terhadap inovasi teknologi hijau baharu dalam bidang elektronik.',
                en: 'Skills in adopting an open-minded approach toward new green technology innovations in the electronics field.'
            },
            {
                id: 'B_7.5', code: '7.5', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran Berfikir Aras Tinggi (KBAT) dalam merancang penyelesaian kelestarian sistem elektronik.',
                en: 'Higher Order Thinking Skills (HOTS) in planning electronic system sustainability solutions.'
            },
            {
                id: 'B_7.6', code: '7.6', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '7.0 Kemahiran Menyelesaikan Masalah dan Berfikiran Kreatif dalam Elektronik Hijau',
                subConstructEn: '7.0 Problem-Solving and Creative Thinking Skills in Green Electronics',
                type: 'likert', required: true,
                bm: 'Kemahiran berfikir secara strategik bagi mengurangkan jejak karbon (carbon footprint) produk elektronik (Penilaian Lanjutan).',
                en: 'Skills in strategic thinking to reduce the carbon footprint of electronic products (Extended Assessment).'
            },
            // Sub-construct 8.0
            {
                id: 'B_8.0', code: '8.0', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                subConstructEn: '8.0 Biodiversity and Ecosystem Protection Skills through Electronic Applications',
                type: 'likert', required: true,
                bm: 'Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                en: 'Biodiversity and Ecosystem Protection Skills through Electronic Applications'
            },
            {
                id: 'B_8.1', code: '8.1', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                subConstructEn: '8.0 Biodiversity and Ecosystem Protection Skills through Electronic Applications',
                type: 'likert', required: true,
                bm: 'Kemahiran melindungi alam sekitar melalui penggunaan peralatan dan peranti pengawasan elektronik yang sesuai haruslah diterapkan dalam kurikulum Program Teknologi Elektronik TVET.',
                en: 'Environmental protection skills through the appropriate use of electronic monitoring equipment and devices should be incorporated into the TVET Electronic Technology Program curriculum.'
            },
            {
                id: 'B_8.2', code: '8.2', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                subConstructEn: '8.0 Biodiversity and Ecosystem Protection Skills through Electronic Applications',
                type: 'likert', required: true,
                bm: 'Kemahiran pemantauan elektronik bagi memulihara biodiversiti haruslah diterapkan dalam kurikulum Program Teknologi Elektronik TVET.',
                en: 'Electronic monitoring skills to conserve biodiversity should be incorporated into the TVET Electronic Technology Program curriculum.'
            },
            {
                id: 'B_8.3', code: '8.3', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                subConstructEn: '8.0 Biodiversity and Ecosystem Protection Skills through Electronic Applications',
                type: 'likert', required: true,
                bm: 'Kemahiran mengaplikasikan penderia (sensors) dan peranti elektronik bagi pemantauan kualiti alam sekitar/ekosistem.',
                en: 'Skills in applying sensors and electronic devices for environmental/ecosystem quality monitoring.'
            },
            {
                id: 'B_8.4', code: '8.4', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                subConstructEn: '8.0 Biodiversity and Ecosystem Protection Skills through Electronic Applications',
                type: 'likert', required: true,
                bm: 'Kemahiran mengaplikasikan sistem elektronik hijau (seperti solar) bagi memulihara landskap alam sekitar.',
                en: 'Skills in applying green electronic systems (such as solar) to conserve environmental landscapes.'
            },
            {
                id: 'B_8.5', code: '8.5', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: '8.0 Kemahiran Perlindungan Biodiversiti dan Ekosistem melalui Aplikasi Elektronik',
                subConstructEn: '8.0 Biodiversity and Ecosystem Protection Skills through Electronic Applications',
                type: 'likert', required: true,
                bm: 'Kemahiran menyelenggara sistem dan peranti pemantauan elektronik hijau.',
                en: 'Skills in maintaining green electronic monitoring systems and devices.'
            },
            {
                id: 'B_OPEN', code: 'Terbuka B', part: 'B',
                section: 'Bahagian B',
                sectionTitleBm: 'Seksyen B • Bahagian B: Elemen Kemahiran',
                sectionTitleEn: 'Section B • Part B: Skill Elements',
                subConstructBm: 'Soalan Terbuka Bahagian B (Pilihan)',
                subConstructEn: 'Open-ended Question Part B (Optional)',
                type: 'textarea', required: false,
                bm: 'Apakah elemen kemahiran praktikal hijau lain yang penting tetapi tidak tersenarai di atas?',
                en: 'What other practical green skill elements are important but not listed above?',
                placeholderBm: 'Nyatakan cadangan tambahan anda di sini (jika ada), atau klik Seterusnya untuk ke Bahagian C...',
                placeholderEn: 'State your additional suggestions here (if any), or click Next to proceed to Part C...'
            },

            // --- SEKSYEN B - BAHAGIAN C: ELEMEN SIKAP DAN NILAI ---
            // Sub-construct 1.0
            {
                id: 'C_1.0', code: '1.0', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
                subConstructEn: '1.0 Environmental Awareness in the Field of Electronics',
                type: 'likert', required: true,
                bm: 'Kesedaran Alam Sekitar dalam Bidang Elektronik',
                en: 'Environmental Awareness in the Field of Electronics'
            },
            {
                id: 'C_1.1', code: '1.1', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
                subConstructEn: '1.0 Environmental Awareness in the Field of Electronics',
                type: 'likert', required: true,
                bm: 'Kesedaran terhadap kepentingan melindungi alam sekitar di tempat kerja atau bengkel elektronik.',
                en: 'Awareness of the importance of environmental protection in the workplace or electronics workshop.'
            },
            {
                id: 'C_1.2', code: '1.2', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
                subConstructEn: '1.0 Environmental Awareness in the Field of Electronics',
                type: 'likert', required: true,
                bm: 'Kesedaran terhadap dasar, perundangan, dan standard piawaian hijau industri elektronik.',
                en: 'Awareness of green policies, regulations, and industry standards in electronics.'
            },
            {
                id: 'C_1.3', code: '1.3', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
                subConstructEn: '1.0 Environmental Awareness in the Field of Electronics',
                type: 'likert', required: true,
                bm: 'Kesedaran terhadap impak pengurangan sisa buangan elektronik (e-waste) kepada alam sekitar.',
                en: 'Awareness of the impact of electronic waste (e-waste) reduction on the environment.'
            },
            {
                id: 'C_1.4', code: '1.4', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
                subConstructEn: '1.0 Environmental Awareness in the Field of Electronics',
                type: 'likert', required: true,
                bm: 'Kesedaran terhadap amalan hijau dalam proses pembuatan dan perkhidmatan elektronik.',
                en: 'Awareness of green practices in electronic manufacturing and service processes.'
            },
            {
                id: 'C_1.5', code: '1.5', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '1.0 Kesedaran Alam Sekitar dalam Bidang Elektronik',
                subConstructEn: '1.0 Environmental Awareness in the Field of Electronics',
                type: 'likert', required: true,
                bm: 'Kesedaran terhadap penggunaan sumber tenaga boleh baharu dalam pengoperasian sistem elektronik.',
                en: 'Awareness of using renewable energy sources in electronic system operations.'
            },
            // Sub-construct 2.0
            {
                id: 'C_2.0', code: '2.0', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
                subConstructEn: '2.0 Positive Values and Green Culture in the Electronics Industry',
                type: 'likert', required: true,
                bm: 'Nilai Positif & Budaya Hijau Industri Elektronik',
                en: 'Positive Values and Green Culture in the Electronics Industry'
            },
            {
                id: 'C_2.1', code: '2.1', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
                subConstructEn: '2.0 Positive Values and Green Culture in the Electronics Industry',
                type: 'likert', required: true,
                bm: 'Nilai amalan penjimatan tenaga elektrik (seperti mematikan peralatan dan suis utama apabila tidak digunakan).',
                en: 'Values of electrical energy conservation practices (such as switching off equipment and main switches when not in use).'
            },
            {
                id: 'C_2.2', code: '2.2', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
                subConstructEn: '2.0 Positive Values and Green Culture in the Electronics Industry',
                type: 'likert', required: true,
                bm: 'Nilai amalan 5R (reduce, reuse, recycle, recover & refuse) terhadap perkakasan elektronik.',
                en: 'Values of the 5R practices (reduce, reuse, recycle, recover, and refuse) regarding electronic hardware.'
            },
            {
                id: 'C_2.3', code: '2.3', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
                subConstructEn: '2.0 Positive Values and Green Culture in the Electronics Industry',
                type: 'likert', required: true,
                bm: 'Nilai komitmen terhadap pengurusan selamat sisa toksik (seperti asid punaran) dan komponen berbahaya (seperti bateri litium atau kapasitor elektrolit).',
                en: 'Values of commitment to safe management of toxic waste (such as etching acid) and hazardous components (such as lithium batteries or electrolytic capacitors).'
            },
            {
                id: 'C_2.4', code: '2.4', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
                subConstructEn: '2.0 Positive Values and Green Culture in the Electronics Industry',
                type: 'likert', required: true,
                bm: 'Nilai keutamaan terhadap pemuliharaan sumber melalui kecekapan reka bentuk litar.',
                en: 'Values of prioritizing resource conservation through circuit design efficiency.'
            },
            {
                id: 'C_2.5', code: '2.5', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: '2.0 Nilai Positif & Budaya Hijau Industri Elektronik',
                subConstructEn: '2.0 Positive Values and Green Culture in the Electronics Industry',
                type: 'likert', required: true,
                bm: 'Nilai pembudayaan amalan dan etika hijau dalam kerjaya bidang elektronik.',
                en: 'Values of cultivating green practices and ethics in electronic careers.'
            },
            {
                id: 'C_OPEN', code: 'Terbuka C', part: 'C',
                section: 'Bahagian C',
                sectionTitleBm: 'Seksyen B • Bahagian C: Elemen Sikap dan Nilai',
                sectionTitleEn: 'Section B • Part C: Attitude and Value Elements',
                subConstructBm: 'Soalan Terbuka Bahagian C (Pilihan)',
                subConstructEn: 'Open-ended Question Part C (Optional)',
                type: 'textarea', required: false,
                bm: 'Apakah elemen sikap dan nilai hijau lain yang penting tetapi tidak tersenarai di atas?',
                en: 'What other green attitudes and values elements are important but not listed above?',
                placeholderBm: 'Nyatakan cadangan tambahan anda di sini (jika ada), kemudian klik Hantar Soal Selidik...',
                placeholderEn: 'State your additional suggestions here (if any), then click Submit Survey...'
            }
        ];

        // =========================================================================
        // 2. COLOR-CODED 5-POINT LIKERT SCALE CONFIGURATION
        // 1: Merah | 2: Kuning | 3: Oren | 4: Hijau Muda | 5: Hijau
        // =========================================================================
        const LIKERT_SCALE = [
            {
                value: 1,
                code: 'Stp',
                bm: 'Sangat Tidak Penting',
                en: 'Not at all important',
                colorName: 'Merah',
                bgClass: 'bg-red-500 hover:bg-red-600 text-white border-red-600',
                softClass: 'bg-red-50 hover:bg-red-100/90 text-red-950 border-red-300',
                badgeClass: 'bg-red-500 text-white',
                ringClass: 'ring-red-400',
                hex: '#ef4444'
            },
            {
                value: 2,
                code: 'Tp',
                bm: 'Tidak Penting',
                en: 'Slightly important',
                colorName: 'Kuning',
                bgClass: 'bg-yellow-400 hover:bg-yellow-500 text-slate-950 border-yellow-500',
                softClass: 'bg-yellow-50 hover:bg-yellow-100/90 text-yellow-950 border-yellow-300',
                badgeClass: 'bg-yellow-400 text-slate-950',
                ringClass: 'ring-yellow-400',
                hex: '#facc15'
            },
            {
                value: 3,
                code: 'Hp',
                bm: 'Hampir Penting',
                en: 'Somewhat important',
                colorName: 'Oren',
                bgClass: 'bg-orange-500 hover:bg-orange-600 text-white border-orange-600',
                softClass: 'bg-orange-50 hover:bg-orange-100/90 text-orange-950 border-orange-300',
                badgeClass: 'bg-orange-500 text-white',
                ringClass: 'ring-orange-400',
                hex: '#f97316'
            },
            {
                id: 4,
                value: 4,
                code: 'P',
                bm: 'Penting',
                en: 'Important',
                colorName: 'Hijau Muda',
                bgClass: 'bg-lime-500 hover:bg-lime-600 text-slate-950 border-lime-600',
                softClass: 'bg-lime-50 hover:bg-lime-100/90 text-lime-950 border-lime-300',
                badgeClass: 'bg-lime-500 text-slate-950',
                ringClass: 'ring-lime-400',
                hex: '#84cc16'
            },
            {
                value: 5,
                code: 'Sp',
                bm: 'Sangat Penting',
                en: 'Strongly important',
                colorName: 'Hijau',
                bgClass: 'bg-emerald-700 hover:bg-emerald-800 text-white border-emerald-800',
                softClass: 'bg-emerald-50 hover:bg-emerald-100/90 text-emerald-950 border-emerald-300',
                badgeClass: 'bg-emerald-700 text-white',
                ringClass: 'ring-emerald-500',
                hex: '#047857'
            }
        ];

        // =========================================================================
        // 3. STATE MANAGEMENT & LOCALSTORAGE PERSISTENCE
        // =========================================================================
        const STORAGE_KEY = 'uthm_phd_green_skills_survey_v1';
        let state = {
            screen: 'intro', // 'intro' | 'survey' | 'complete'
            currentIndex: 0,
            langMode: 'both', // 'both' | 'bm' | 'en'
            answers: {},
            respondentId: null,
            submittedAt: null,
            sheetSyncStatus: 'idle', // 'idle' | 'sending' | 'synced' | 'error' | 'unconfigured'
            sheetSyncMessage: ''
        };
        let autoAdvanceTimer = null;

        function loadState() {
            try {
                const saved = localStorage.getItem(STORAGE_KEY);
                if (saved) {
                    const parsed = JSON.parse(saved);
                    state = { ...state, ...parsed };
                }
            } catch (e) {
                console.warn('Gagal memuatkan simpanan tempatan:', e);
            }
        }

        function saveState() {
            try {
                localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
                const statusEl = document.getElementById('save-status');
                if (statusEl) {
                    statusEl.innerHTML = `<span class="w-1.5 h-1.5 rounded-full bg-emerald-500 animate-ping"></span> Disimpan (${new Date().toLocaleTimeString('ms-MY', {hour: '2-digit', minute:'2-digit'})})`;
                }
            } catch (e) {
                console.warn('Gagal menyimpan data:', e);
            }
        }

        // =========================================================================
        // 4. BILINGUAL TEXT HELPER
        // =========================================================================
        function biText(bm, en, bmClass = 'text-slate-900 font-semibold', enClass = 'text-slate-500 italic text-sm mt-1') {
            if (state.langMode === 'bm') {
                return `<div class="${bmClass}">${bm}</div>`;
            }
            if (state.langMode === 'en') {
                return `<div class="${bmClass}">${en}</div>`;
            }
            return `
                <div class="${bmClass}">${bm}</div>
                <div class="${enClass}">${en}</div>
            `;
        }

        function setLangMode(mode) {
            state.langMode = mode;
            ['both', 'bm', 'en'].forEach(m => {
                const btn = document.getElementById(`lang-${m}`);
                if (m === mode) {
                    btn.className = 'px-2.5 py-1 rounded-lg bg-white text-[#1a237e] shadow-sm transition';
                } else {
                    btn.className = 'px-2.5 py-1 rounded-lg text-slate-600 hover:text-slate-900 transition';
                }
            });
            saveState();
            render();
        }

        // =========================================================================
        // 5. NAVIGATION & FLOW LOGIC
        // =========================================================================
        function startSurvey() {
            state.screen = 'survey';
            saveState();
            render();
        }

        function goToQuestion(idx) {
            if (autoAdvanceTimer) clearTimeout(autoAdvanceTimer);
            if (idx >= 0 && idx < SURVEY_ITEMS.length) {
                state.screen = 'survey';
                state.currentIndex = idx;
                saveState();
                render();
                toggleDrawer(false);
            }
        }

        function prevQuestion() {
            if (autoAdvanceTimer) clearTimeout(autoAdvanceTimer);
            if (state.currentIndex > 0) {
                state.currentIndex--;
                saveState();
                render();
            } else {
                state.screen = 'intro';
                saveState();
                render();
            }
        }

        function nextQuestion() {
            if (autoAdvanceTimer) clearTimeout(autoAdvanceTimer);
            const item = SURVEY_ITEMS[state.currentIndex];
            const val = state.answers[item.id];

            if (item.required && (val === undefined || val === null || String(val).trim() === '')) {
                showToast('⚠️ Sila lengkapkan soalan ini sebelum meneruskan.');
                const card = document.getElementById('question-card');
                if (card) {
                    card.classList.add('ring-2', 'ring-rose-400');
                    setTimeout(() => card.classList.remove('ring-2', 'ring-rose-400'), 700);
                }
                return;
            }

            if (state.currentIndex < SURVEY_ITEMS.length - 1) {
                state.currentIndex++;
                saveState();
                render();
            } else {
                finishSurvey();
            }
        }

        function selectOption(itemId, value, shouldAutoAdvance = true) {
            state.answers[itemId] = value;
            saveState();
            render();

            const autoToggle = document.getElementById('auto-advance-toggle');
            const isAuto = autoToggle ? autoToggle.checked : true;

            if (shouldAutoAdvance && isAuto) {
                if (autoAdvanceTimer) clearTimeout(autoAdvanceTimer);
                autoAdvanceTimer = setTimeout(() => {
                    if (state.currentIndex < SURVEY_ITEMS.length - 1) {
                        state.currentIndex++;
                        saveState();
                        render();
                    }
                }, 360);
            }
        }

        function handleTextInput(itemId, value) {
            state.answers[itemId] = value;
            saveState();
        }

        function finishSurvey() {
            // Check if any required question is missed
            const firstUnanswered = SURVEY_ITEMS.findIndex(item => {
                if (!item.required) return false;
                const v = state.answers[item.id];
                return v === undefined || v === null || String(v).trim() === '';
            });

            if (firstUnanswered !== -1) {
                showToast(`⚠️ Masih ada soalan wajib yang belum dijawab (Soalan #${firstUnanswered + 1}).`);
                goToQuestion(firstUnanswered);
                return;
            }

            if (!state.respondentId) {
                const datePart = new Date().toISOString().slice(0, 10).replace(/-/g, '');
                const randPart = Math.random().toString(36).substring(2, 6).toUpperCase();
                state.respondentId = `R-${datePart}-${randPart}`;
            }

            state.screen = 'complete';
            state.submittedAt = new Date().toISOString();
            saveState();
            render();

            // Automatically transmit to Google Sheet if URL is configured
            submitToGoogleSheet();
        }

        // =========================================================================
        // 5B. GOOGLE SHEET PAYLOAD BUILDER & SUBMISSION
        // =========================================================================
        function buildGoogleSheetPayload() {
            const calcMean = (partCode) => {
                const items = SURVEY_ITEMS.filter(i => i.part === partCode && i.type === 'likert');
                const vals = items.map(i => Number(state.answers[i.id])).filter(v => !isNaN(v) && v > 0);
                if (!vals.length) return '';
                return Number((vals.reduce((a, b) => a + b, 0) / vals.length).toFixed(2));
            };

            const allLikert = SURVEY_ITEMS.filter(i => i.type === 'likert')
                .map(i => Number(state.answers[i.id])).filter(v => !isNaN(v) && v > 0);
            const overallMean = allLikert.length
                ? Number((allLikert.reduce((a, b) => a + b, 0) / allLikert.length).toFixed(2))
                : '';

            const payload = {
                ID_Responden: state.respondentId || `R-${Date.now()}`,
                Tarikh_Masa_Hantar: state.submittedAt || new Date().toISOString(),
                A1_Jantina: state.answers['D1'] || '',
                A2_Umur: state.answers['D2'] || '',
                A3_Pendidikan: state.answers['D3'] || '',
                A4_Pengalaman_Mengajar: state.answers['D4'] || '',
                A5_Subjek_Modul_Utama: state.answers['D5'] || '',
                A6_Kolej_Vokasional: state.answers['D6'] || ''
            };

            // Map every Seksyen B item to exact Google Sheet column key (e.g. A_1.0 -> BA_1_0, A_OPEN -> BA_Terbuka)
            SURVEY_ITEMS.filter(i => i.part).forEach(item => {
                let colKey = '';
                if (item.id.endsWith('_OPEN')) {
                    colKey = `B${item.part}_Terbuka`;
                } else {
                    colKey = 'B' + item.id.replace('.', '_');
                }
                const rawVal = state.answers[item.id];
                payload[colKey] = item.type === 'likert' && rawVal !== undefined ? Number(rawVal) : (rawVal || '');
            });

            payload.Min_Bahagian_A_Pengetahuan = calcMean('A');
            payload.Min_Bahagian_B_Kemahiran = calcMean('B');
            payload.Min_Bahagian_C_Sikap_Nilai = calcMean('C');
            payload.Min_Keseluruhan = overallMean;

            return payload;
        }

        async function submitToGoogleSheet(isManualRetry = false) {
            const scriptUrl = getActiveScriptUrl();
            if (!scriptUrl) {
                state.sheetSyncStatus = 'unconfigured';
                state.sheetSyncMessage = 'URL Google Apps Script belum ditetapkan. Sila gunakan butang Muat Turun CSV atau tetapkan URL Google Sheet.';
                saveState();
                if (state.screen === 'complete') render();
                return;
            }

            state.sheetSyncStatus = 'sending';
            state.sheetSyncMessage = 'Menghantar data ke Google Sheet...';
            if (state.screen === 'complete') render();

            const payload = buildGoogleSheetPayload();

            try {
                // Using no-cors + text/plain avoids Google Apps Script CORS preflight issues reliably
                await fetch(scriptUrl, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: {
                        'Content-Type': 'text/plain;charset=utf-8'
                    },
                    body: JSON.stringify(payload)
                });

                state.sheetSyncStatus = 'synced';
                state.sheetSyncMessage = `Berjaya direkodkan ke Google Sheet! (ID: ${payload.ID_Responden})`;
                saveState();
                if (state.screen === 'complete') render();
                if (isManualRetry) showToast('✅ Data berjaya dihantar semula ke Google Sheet!');
            } catch (err) {
                console.error('Ralat penghantaran Google Sheet:', err);
                state.sheetSyncStatus = 'error';
                state.sheetSyncMessage = 'Gagal menghubungi Google Sheet. Sila semak sambungan internet atau muat turun fail CSV sebagai sandaran.';
                saveState();
                if (state.screen === 'complete') render();
                showToast('⚠️ Ralat menghantar ke Google Sheet.');
            }
        }

        // =========================================================================
        // 6. RENDERING VIEWS (INTRO / QUESTION CARD / COMPLETION DASHBOARD)
        // =========================================================================
        function updateHeaderProgress() {
            const progWrap = document.getElementById('progress-wrapper');
            const navBtn = document.getElementById('btn-nav-drawer');

            if (state.screen !== 'survey') {
                progWrap.classList.add('hidden');
                navBtn.classList.add('hidden');
                navBtn.classList.remove('inline-flex');
                return;
            }

            progWrap.classList.remove('hidden');
            navBtn.classList.remove('hidden');
            navBtn.classList.add('inline-flex');

            const total = SURVEY_ITEMS.length;
            const answeredCount = SURVEY_ITEMS.filter(it => {
                const v = state.answers[it.id];
                return v !== undefined && v !== null && String(v).trim() !== '';
            }).length;

            const pct = Math.round((answeredCount / total) * 100);
            const currentItem = SURVEY_ITEMS[state.currentIndex];

            document.getElementById('nav-counter-badge').textContent = `${state.currentIndex + 1}/${total}`;
            document.getElementById('progress-section-label').textContent =
                state.langMode === 'en' ? currentItem.sectionTitleEn : currentItem.sectionTitleBm;
            document.getElementById('progress-percent-text').textContent = `${pct}% Selesai (${answeredCount}/${total})`;
            document.getElementById('progress-bar-fill').style.width = `${Math.max(4, pct)}%`;
        }

        function renderIntro() {
            const hasSavedProgress = Object.keys(state.answers).length > 0;

            return `
                <div class="glass-card rounded-3xl p-6 sm:p-10 slide-enter">
                    <!-- Institutional Banner -->
                    <div class="flex flex-wrap items-center justify-between gap-3 pb-6 border-b border-slate-200/80">
                        <div class="flex items-center gap-3">
                            <div class="w-12 h-12 rounded-2xl bg-[#1a237e] text-white flex items-center justify-center font-display font-extrabold text-lg shadow-md">
                                UTHM
                            </div>
                            <div>
                                <p class="text-xs font-bold uppercase tracking-wider text-emerald-700">Universiti Tun Hussein Onn Malaysia</p>
                                <p class="text-xs text-slate-500">Fakulti Pendidikan Teknikal & Vokasional (FPTV)</p>
                            </div>
                        </div>
                    </div>

                    <!-- Research Title -->
                    <div class="mt-6">
                        <h2 class="font-display font-extrabold text-xl sm:text-2xl text-slate-900 leading-snug">
                            PEMBANGUNAN KERANGKA KEMAHIRAN HIJAU UNTUK KURIKULUM PROGRAM TEKNOLOGI ELEKTRONIK TVET: DALAM MEMENUHI KEPERLUAN EKONOMI HIJAU
                        </h2>
                        <p class="font-display font-semibold text-sm sm:text-base text-indigo-800/85 mt-2 leading-snug">
                            DEVELOPMENT OF A GREEN SKILLS FRAMEWORK FOR THE TVET ELECTRONIC TECHNOLOGY PROGRAMME CURRICULUM: MEETING THE NEEDS OF THE GREEN ECONOMY
                        </p>
                    </div>

                    <!-- Welcome Letter & Study Context -->
                    <div class="mt-6 space-y-4 text-sm text-slate-700 leading-relaxed bg-slate-50/90 p-5 sm:p-6 rounded-2xl border border-slate-200/80">
                        <p class="font-semibold text-slate-900">Kepada Tuan/Puan yang dihormati / Dear Sir/Madam,</p>
                        <p>
                            Saya, <strong>Adib Farhan bin Zaime</strong> merupakan pelajar separuh masa bagi program <strong>Doktor Falsafah Pendidikan Teknik dan Vokasional di Universiti Tun Hussein Onn Malaysia (UTHM)</strong>. Di sini, saya memohon kerjasama dan sokongan daripada pihak tuan/puan untuk menjalankan kajian penyelidikan ini bagi meneroka, membangunkan, dan mengesahkan kerangka kemahiran hijau sebagai nilai tambah untuk kurikulum <strong>Program Teknologi Elektronik TVET di Kolej Vokasional Malaysia</strong>.
                        </p>
                        <p class="text-xs text-slate-500 italic">
                            I am Adib Farhan bin Zaime, a part-time student candidate for Doctor of Philosophy (PhD) in Technical and Vocational Education at Universiti Tun Hussein Onn Malaysia (UTHM). I am writing to seek your kind cooperation and support in conducting this research study to explore, develop, and validate a green skills framework as an added value for the TVET Electronic Technology Programme curriculum at Malaysian Vocational Colleges.
                        </p>

                        <!-- Definition Highlight Box -->
                        <div class="p-4 rounded-xl bg-emerald-50/90 border border-emerald-200 text-emerald-950">
                            <p class="text-xs font-bold uppercase tracking-wider text-emerald-800 mb-1">🌱 Definisi Kemahiran Hijau / Definition of Green Skills</p>
                            <p class="text-xs sm:text-sm">
                                Kemahiran hijau adalah satu set kemahiran yang merangkumi <strong>kemahiran teknikal, pengetahuan, nilai, dan sikap</strong> yang diperlukan dalam pekerjaan hijau untuk menyokong ekonomi, sosial, dan alam sekitar yang mampan melalui aktiviti seperti industri, perniagaan, dan komuniti.
                            </p>
                            <p class="text-[11px] text-emerald-800/85 italic mt-1">
                                Green skills refer to a set of skills encompassing technical skills, knowledge, values, and attitudes required in green jobs to support economic, social, and environmental sustainability through activities across industries, businesses, and communities.
                            </p>
                        </div>
                    </div>

                    <!-- Direct Researcher & Supervisor Info Section on Landing Page -->
                    <div class="mt-6">
                        <div class="flex items-center justify-between mb-2.5">
                            <p class="text-xs font-bold uppercase tracking-wider text-slate-600">
                                Sebarang Pertanyaan Bolehlah Hubungi / For Any Inquiries, Please Contact:
                            </p>
                        </div>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-3.5">
                            <!-- Card 1: Penyelidik -->
                            <div class="p-4 rounded-2xl bg-white border border-slate-200 shadow-xs flex flex-col justify-between">
                                <div>
                                    <span class="inline-block text-[10px] font-bold uppercase tracking-wider text-indigo-700 bg-indigo-50 px-2 py-0.5 rounded-md border border-indigo-100">
                                        1) Penyelidik / Pelajar PhD
                                    </span>
                                    <h3 class="font-display font-bold text-base text-slate-900 mt-1.5">Adib Farhan bin Zaime</h3>
                                    <p class="text-xs text-slate-500 mt-0.5 leading-snug">
                                        Pelajar Separuh Masa Program Doktor Falsafah Pendidikan Teknik dan Vokasional (PhD), Universiti Tun Hussein Onn Malaysia (UTHM)
                                    </p>
                                </div>
                                <div class="mt-3 pt-2.5 border-t border-slate-100 flex flex-wrap items-center gap-2 text-xs">
                                    <a href="tel:+60136502508" class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg bg-slate-50 hover:bg-slate-100 text-slate-700 font-semibold border border-slate-200 transition">
                                        <span>📞</span> +60 13 650 2508
                                    </a>
                                    <a href="https://wa.me/60136502508" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg bg-emerald-50 hover:bg-emerald-100 text-emerald-700 font-semibold border border-emerald-200 transition">
                                        <span>💬</span> WhatsApp
                                    </a>
                                    <a href="mailto:adibfarhanzaime@gmail.com" class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg bg-indigo-50 hover:bg-indigo-100 text-[#1a237e] font-semibold border border-indigo-100 transition break-all">
                                        <span>✉️</span> adibfarhanzaime@gmail.com
                                    </a>
                                </div>
                            </div>

                            <!-- Card 2: Penyelia Utama -->
                            <div class="p-4 rounded-2xl bg-white border border-slate-200 shadow-xs flex flex-col justify-between">
                                <div>
                                    <span class="inline-block text-[10px] font-bold uppercase tracking-wider text-emerald-800 bg-emerald-50 px-2 py-0.5 rounded-md border border-emerald-200">
                                        2) Penyelia Utama / Supervisor
                                    </span>
                                    <h3 class="font-display font-bold text-base text-slate-900 mt-1.5">Prof. Ts. Dr. Lai Chee Sern</h3>
                                    <p class="text-xs text-slate-500 mt-0.5 leading-snug">
                                        Pensyarah Kanan / Senior Lecturer, Fakulti Pendidikan Teknikal & Vokasional (FPTV), Universiti Tun Hussein Onn Malaysia (UTHM)
                                    </p>
                                </div>
                                <div class="mt-3 pt-2.5 border-t border-slate-100 flex flex-wrap items-center gap-2 text-xs">
                                    <a href="tel:+60125768327" class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg bg-slate-50 hover:bg-slate-100 text-slate-700 font-semibold border border-slate-200 transition">
                                        <span>📞</span> +60 12 576 8327
                                    </a>
                                    <a href="https://wa.me/60125768327" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg bg-emerald-50 hover:bg-emerald-100 text-emerald-700 font-semibold border border-emerald-200 transition">
                                        <span>💬</span> WhatsApp
                                    </a>
                                    <a href="mailto:lcsern@uthm.edu.my" class="inline-flex items-center gap-1 px-2.5 py-1 rounded-lg bg-indigo-50 hover:bg-indigo-100 text-[#1a237e] font-semibold border border-indigo-100 transition break-all">
                                        <span>✉️</span> lcsern@uthm.edu.my
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 5-Color Likert Legend Preview -->
                    <div class="mt-6">
                        <p class="text-xs font-bold uppercase tracking-wider text-slate-500 mb-2.5">Panduan Skala Penilaian 5-Tahap (5-Point Color Likert Scale):</p>
                        <div class="grid grid-cols-2 sm:grid-cols-5 gap-2">
                            ${LIKERT_SCALE.map(s => `
                                <div class="p-2.5 rounded-xl border ${s.softClass} flex flex-col items-center text-center">
                                    <span class="w-7 h-7 rounded-lg ${s.badgeClass} font-bold text-sm flex items-center justify-center shadow-xs mb-1">${s.value}</span>
                                    <span class="text-[11px] font-bold leading-tight">${s.bm}</span>
                                    <span class="text-[10px] opacity-75 leading-tight mt-0.5">${s.en}</span>
                                </div>
                            `).join('')}
                        </div>
                    </div>

                    <!-- Action Buttons -->
                    <div class="mt-8 pt-5 border-t border-slate-200/80 flex flex-col sm:flex-row items-center justify-between gap-4">
                        <div class="text-xs text-slate-500">
                            🔒 Segala jawapan adalah <strong>sulit</strong> dan digunakan untuk tujuan akademik sahaja.
                        </div>
                        <button type="button" onclick="startSurvey()" class="w-full sm:w-auto px-7 py-3.5 rounded-2xl bg-gradient-to-r from-[#1a237e] to-indigo-700 hover:from-indigo-900 hover:to-[#1a237e] text-white font-display font-bold text-sm sm:text-base shadow-lg shadow-indigo-900/20 flex items-center justify-center gap-2.5 transition transform active:scale-[0.99]">
                            <span>${hasSavedProgress ? 'Sambung Soal Selidik / Continue Survey' : 'Mula Soal Selidik / Start Survey'}</span>
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
                        </button>
                    </div>
                </div>
            `;
        }

        function renderQuestionCard() {
            const idx = state.currentIndex;
            const total = SURVEY_ITEMS.length;
            const item = SURVEY_ITEMS[idx];
            const currentVal = state.answers[item.id];
            const isLast = idx === total - 1;

            let inputHtml = '';

            if (item.type === 'radio') {
                inputHtml = `
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 mt-6">
                        ${item.options.map((opt, oIdx) => {
                            const selected = currentVal === opt.value;
                            return `
                                <button type="button" onclick="selectOption('${item.id}', '${opt.value.replace(/'/g, "\\'")}', true)"
                                    class="group text-left p-4 rounded-2xl border-2 transition-all duration-150 flex items-center justify-between gap-3 ${
                                        selected
                                        ? 'border-[#1a237e] bg-indigo-50/90 shadow-md ring-2 ring-indigo-200'
                                        : 'border-slate-200 bg-white hover:border-indigo-300 hover:bg-slate-50'
                                    }">
                                    <div>
                                        ${biText(
                                            opt.bm,
                                            opt.en,
                                            selected ? 'font-bold text-[#1a237e] text-base' : 'font-semibold text-slate-800 text-base',
                                            'text-xs text-slate-500 mt-0.5'
                                        )}
                                    </div>
                                    <span class="w-7 h-7 rounded-full flex items-center justify-center text-xs font-bold shrink-0 transition ${
                                        selected
                                        ? 'bg-[#1a237e] text-white'
                                        : 'bg-slate-100 text-slate-500 group-hover:bg-indigo-100 group-hover:text-[#1a237e]'
                                    }">
                                        ${selected ? '✓' : String.fromCharCode(65 + oIdx)}
                                    </span>
                                </button>
                            `;
                        }).join('')}
                    </div>
                `;
            } else if (item.type === 'text') {
                const ph = state.langMode === 'en' ? item.placeholderEn : item.placeholderBm;
                inputHtml = `
                    <div class="mt-6">
                        <input type="text" id="active-text-input"
                            value="${(currentVal || '').replace(/"/g, '&quot;')}"
                            oninput="handleTextInput('${item.id}', this.value)"
                            onkeydown="if(event.key==='Enter'){ event.preventDefault(); nextQuestion(); }"
                            placeholder="${ph}"
                            class="w-full px-4 py-4 rounded-2xl border-2 border-slate-200 focus:border-[#1a237e] focus:ring-4 focus:ring-indigo-100 outline-none text-base font-medium text-slate-900 bg-white transition"
                        />
                        <p class="text-xs text-slate-400 mt-2">Tekan <kbd class="px-1.5 py-0.5 bg-slate-100 border border-slate-300 rounded text-slate-600 font-mono">Enter</kbd> atau klik <strong>Seterusnya</strong> selepas menaip.</p>
                    </div>
                `;
            } else if (item.type === 'textarea') {
                const ph = state.langMode === 'en' ? item.placeholderEn : item.placeholderBm;
                inputHtml = `
                    <div class="mt-6">
                        <textarea id="active-text-input" rows="4"
                            oninput="handleTextInput('${item.id}', this.value)"
                            placeholder="${ph}"
                            class="w-full px-4 py-3.5 rounded-2xl border-2 border-slate-200 focus:border-[#1a237e] focus:ring-4 focus:ring-indigo-100 outline-none text-sm sm:text-base text-slate-900 bg-white transition"
                        >${currentVal || ''}</textarea>
                        <p class="text-xs text-slate-500 mt-2">💡 Soalan terbuka ini adalah pilihan (optional). Anda boleh membiarkannya kosong jika tiada cadangan tambahan.</p>
                    </div>
                `;
            } else if (item.type === 'likert') {
                inputHtml = `
                    <div class="mt-6">
                        <div class="flex items-center justify-between text-xs font-semibold text-slate-500 mb-3">
                            <span>Pilih tahap kepentingan (Skala 1 – 5):</span>
                            <span class="hidden sm:inline text-slate-400">Kekunci pantas: 1, 2, 3, 4, 5</span>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-5 gap-2.5">
                            ${LIKERT_SCALE.map(scale => {
                                const isSelected = Number(currentVal) === scale.value;
                                return `
                                    <button type="button" onclick="selectOption('${item.id}', ${scale.value}, true)"
                                        class="group relative p-3.5 sm:p-4 rounded-2xl border-2 transition-all duration-150 flex sm:flex-col items-center justify-between sm:justify-center text-left sm:text-center gap-3 ${
                                            isSelected
                                            ? `${scale.bgClass} shadow-lg scale-[1.02] ring-4 ${scale.ringClass}/40`
                                            : `${scale.softClass} hover:scale-[1.01]`
                                        }">
                                        <div class="flex items-center gap-3 sm:flex-col sm:gap-1.5">
                                            <span class="w-9 h-9 sm:w-10 sm:h-10 rounded-xl flex items-center justify-center font-display font-extrabold text-base sm:text-lg shadow-xs transition ${
                                                isSelected
                                                ? 'bg-white/25 text-current backdrop-blur-xs'
                                                : `${scale.badgeClass}`
                                            }">
                                                ${scale.value}
                                            </span>
                                            <div>
                                                <div class="text-xs sm:text-[13px] font-bold leading-tight">${scale.bm}</div>
                                                <div class="text-[11px] opacity-80 leading-tight mt-0.5">${scale.en}</div>
                                            </div>
                                        </div>
                                        <span class="text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded-md ${
                                            isSelected ? 'bg-black/15' : 'bg-white/70 text-slate-600'
                                        }">
                                            ${scale.code} • ${scale.colorName}
                                        </span>
                                    </button>
                                `;
                            }).join('')}
                        </div>
                    </div>
                `;
            }

            return `
                <div id="question-card" class="glass-card rounded-3xl p-6 sm:p-9 slide-enter transition-all">
                    <!-- Top Breadcrumb & Item Number -->
                    <div class="flex flex-wrap items-center justify-between gap-2 pb-4 border-b border-slate-200/80">
                        <div class="flex items-center gap-2">
                            <span class="px-2.5 py-1 rounded-lg bg-[#1a237e] text-white text-xs font-bold tracking-wide">
                                Soalan ${idx + 1} / ${total}
                            </span>
                            ${item.code ? `
                                <span class="px-2.5 py-1 rounded-lg bg-emerald-50 text-emerald-800 border border-emerald-200 text-xs font-bold">
                                    Item ${item.code}
                                </span>
                            ` : ''}
                        </div>
                        <span class="text-xs font-semibold text-slate-500">
                            ${state.langMode === 'en' ? item.sectionTitleEn : item.sectionTitleBm}
                        </span>
                    </div>

                    <!-- Sub-Construct Context Pill -->
                    <div class="mt-4 p-3 rounded-xl bg-indigo-50/70 border border-indigo-100/90">
                        <p class="text-[11px] font-bold uppercase tracking-wider text-indigo-700">Konstruk / Sub-Domain:</p>
                        ${biText(
                            item.subConstructBm,
                            item.subConstructEn,
                            'text-xs sm:text-sm font-bold text-slate-800 mt-0.5',
                            'text-xs text-slate-500 italic'
                        )}
                    </div>

                    <!-- Main Question Prompt -->
                    <div class="mt-5">
                        ${biText(
                            item.bm,
                            item.en,
                            'font-display font-bold text-lg sm:text-xl text-slate-900 leading-snug',
                            'text-sm sm:text-base text-slate-600 italic mt-2 leading-snug'
                        )}
                    </div>

                    <!-- Interactive Input Area -->
                    ${inputHtml}

                    <!-- Navigation Footer -->
                    <div class="mt-8 pt-5 border-t border-slate-200/80 flex items-center justify-between gap-3">
                        <button type="button" onclick="prevQuestion()" class="px-4 sm:px-5 py-2.5 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold text-sm flex items-center gap-2 transition">
                            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"/></svg>
                            <span>Sebelumnya</span>
                        </button>

                        <button type="button" onclick="nextQuestion()" class="px-6 sm:px-7 py-2.5 rounded-xl ${
                            isLast
                            ? 'bg-emerald-600 hover:bg-emerald-700 shadow-emerald-600/20'
                            : 'bg-[#1a237e] hover:bg-indigo-900 shadow-indigo-900/20'
                        } text-white font-display font-bold text-sm shadow-md flex items-center gap-2 transition">
                            <span>${isLast ? 'Hantar Jawapan / Submit Response' : 'Seterusnya / Next'}</span>
                            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/></svg>
                        </button>
                    </div>
                </div>
            `;
        }

        function renderCompleteScreen() {
            // Calculate mean scores per Part (A, B, C)
            const calcPartStats = (partCode) => {
                const items = SURVEY_ITEMS.filter(i => i.part === partCode && i.type === 'likert');
                const vals = items.map(i => Number(state.answers[i.id])).filter(v => !isNaN(v) && v > 0);
                const sum = vals.reduce((a, b) => a + b, 0);
                const mean = vals.length ? (sum / vals.length).toFixed(2) : '0.00';
                return { count: vals.length, total: items.length, mean };
            };

            const statA = calcPartStats('A');
            const statB = calcPartStats('B');
            const statC = calcPartStats('C');

            // Distribution across 1-5 colors
            const likertItems = SURVEY_ITEMS.filter(i => i.type === 'likert');
            const dist = [1, 2, 3, 4, 5].map(score => {
                const count = likertItems.filter(i => Number(state.answers[i.id]) === score).length;
                const pct = likertItems.length ? Math.round((count / likertItems.length) * 100) : 0;
                return { score, count, pct, meta: LIKERT_SCALE[score - 1] };
            });

            // Google Sheet Sync Status Banner
            let syncBannerHtml = '';
            if (state.sheetSyncStatus === 'sending') {
                syncBannerHtml = `
                    <div class="mt-6 p-4 rounded-2xl bg-indigo-50 border border-indigo-200 flex items-center justify-between gap-3">
                        <div class="flex items-center gap-3 text-xs sm:text-sm font-semibold text-indigo-900">
                            <span class="w-4 h-4 border-2 border-indigo-600 border-t-transparent rounded-full animate-spin shrink-0"></span>
                            <span>Menghantar data ke Google Sheet...</span>
                        </div>
                    </div>
                `;
            } else if (state.sheetSyncStatus === 'synced') {
                syncBannerHtml = `
                    <div class="mt-6 p-4 rounded-2xl bg-emerald-50 border border-emerald-200 flex flex-wrap items-center justify-between gap-3">
                        <div class="flex items-center gap-2.5 text-xs sm:text-sm font-bold text-emerald-900">
                            <span class="text-base">✅</span>
                            <span>${state.sheetSyncMessage || 'Berjaya direkodkan ke Google Sheet!'}</span>
                        </div>
                        <button type="button" onclick="submitToGoogleSheet(true)" class="px-3 py-1.5 rounded-xl bg-white hover:bg-emerald-100 text-emerald-800 border border-emerald-300 text-xs font-semibold transition">
                            Hantar Semula
                        </button>
                    </div>
                `;
            } else if (state.sheetSyncStatus === 'error') {
                syncBannerHtml = `
                    <div class="mt-6 p-4 rounded-2xl bg-rose-50 border border-rose-200 flex flex-wrap items-center justify-between gap-3">
                        <div class="flex items-center gap-2.5 text-xs sm:text-sm font-semibold text-rose-900">
                            <span class="text-base">⚠️</span>
                            <span>${state.sheetSyncMessage}</span>
                        </div>
                        <button type="button" onclick="submitToGoogleSheet(true)" class="px-3.5 py-1.5 rounded-xl bg-rose-600 hover:bg-rose-700 text-white text-xs font-bold transition">
                            Cuba Hantar Semula
                        </button>
                    </div>
                `;
            } else {
                syncBannerHtml = `
                    <div class="mt-6 p-4 rounded-2xl bg-amber-50 border border-amber-200 flex flex-wrap items-center justify-between gap-3">
                        <div class="text-xs text-amber-900">
                            <p class="font-bold">ℹ️ Sambungan Google Sheet Belum Dikonfigurasi</p>
                            <p class="mt-0.5 text-amber-800">Jawapan anda disimpan secara tempatan. Penyelidik boleh menetapkan URL Google Apps Script untuk penghantaran automatik.</p>
                        </div>
                        <button type="button" onclick="toggleSheetModal(true)" class="px-3.5 py-1.5 rounded-xl bg-amber-600 hover:bg-amber-700 text-white text-xs font-bold transition shrink-0">
                            Tetapkan Google Sheet
                        </button>
                    </div>
                `;
            }

            return `
                <div class="glass-card rounded-3xl p-6 sm:p-10 slide-enter">
                    <div class="text-center max-w-xl mx-auto">
                        <div class="w-16 h-16 rounded-2xl bg-emerald-100 text-emerald-700 flex items-center justify-center mx-auto mb-4 shadow-inner">
                            <svg class="w-9 h-9" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M5 13l4 4L19 7"/></svg>
                        </div>
                        <span class="px-3 py-1 rounded-full bg-emerald-50 text-emerald-700 border border-emerald-200 text-xs font-bold uppercase tracking-wider">
                            Penghantaran Selesai • Completed
                        </span>
                        <h2 class="font-display font-extrabold text-2xl sm:text-3xl text-slate-900 mt-3">
                            Terima Kasih Atas Kesudian Tuan/Puan!
                        </h2>
                        <p class="text-sm text-slate-600 mt-2">
                            Thank you for taking the time to complete this PhD research survey. Maklum balas kepakaran anda amat bermakna dalam membangunkan Kerangka Kemahiran Hijau Teknologi Elektronik TVET di Malaysia.
                        </p>
                    </div>

                    ${syncBannerHtml}

                    <!-- Construct Mean Summary Cards -->
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-3.5 mt-6">
            `;
        }

        function render() {
            updateHeaderProgress();
            const container = document.getElementById('app-container');
            if (state.screen === 'intro') {
                container.innerHTML = renderIntro();
            } else if (state.screen === 'survey') {
                container.innerHTML = renderQuestionCard();
                const textEl = document.getElementById('active-text-input');
                if (textEl) textEl.focus();
            } else {
                container.innerHTML = renderCompleteScreen();
            }
        }

        // =========================================================================
        // 7. QUESTION DRAWER, MODALS, DEMO & CSV EXPORT
        // =========================================================================
        function toggleDrawer(show) {
            const overlay = document.getElementById('nav-drawer-overlay');
            if (!show) {
                overlay.classList.add('hidden');
                return;
            }
            overlay.classList.remove('hidden');

            const groups = [
                { title: 'Seksyen A: Demografi (6 Soalan)', items: SURVEY_ITEMS.map((it, idx) => ({ it, idx })).filter(x => x.it.section === 'Seksyen A') },
                { title: 'Bahagian A: Elemen Pengetahuan', items: SURVEY_ITEMS.map((it, idx) => ({ it, idx })).filter(x => x.it.section === 'Bahagian A') },
                { title: 'Bahagian B: Elemen Kemahiran', items: SURVEY_ITEMS.map((it, idx) => ({ it, idx })).filter(x => x.it.section === 'Bahagian B') },
                { title: 'Bahagian C: Elemen Sikap & Nilai', items: SURVEY_ITEMS.map((it, idx) => ({ it, idx })).filter(x => x.it.section === 'Bahagian C') }
            ];

            const listEl = document.getElementById('drawer-questions-list');
            listEl.innerHTML = groups.map(g => `
                <div>
                    <h4 class="text-xs font-bold uppercase tracking-wider text-slate-500 mb-2">${g.title}</h4>
                    <div class="grid grid-cols-5 gap-1.5">
                        ${g.items.map(({ it, idx }) => {
                            const val = state.answers[it.id];
                            const isAnswered = val !== undefined && val !== null && String(val).trim() !== '';
                            const isCurrent = state.currentIndex === idx && state.screen === 'survey';
                            let cls = 'bg-slate-100 text-slate-600 hover:bg-slate-200';
                            if (isCurrent) cls = 'bg-[#1a237e] text-white ring-2 ring-indigo-300 font-bold';
                            else if (isAnswered) cls = 'bg-emerald-100 text-emerald-900 border border-emerald-300 font-semibold';

                            return `
                                <button type="button" onclick="goToQuestion(${idx})" class="py-2 px-1 rounded-xl text-xs transition truncate ${cls}" title="${it.bm}">
                                    ${it.code || (idx + 1)}
                                </button>
                            `;
                        }).join('')}
                    </div>
                </div>
            `).join('');
        }

        function toggleInfoModal(show) {
            const modal = document.getElementById('info-modal');
            modal.classList.toggle('hidden', !show);
            modal.classList.toggle('flex', show);
        }

        function toggleSheetModal(show) {
            const modal = document.getElementById('sheet-modal');
            modal.classList.toggle('hidden', !show);
            modal.classList.toggle('flex', show);
            if (show) {
                const inputEl = document.getElementById('google-script-url-input');
                if (inputEl) inputEl.value = getActiveScriptUrl();
                const codePreview = document.getElementById('apps-script-code-preview');
                if (codePreview) codePreview.value = APPS_SCRIPT_TEMPLATE_CODE;
                updateSheetConnectionIndicator();
                switchSheetTab('config');
            }
        }

        function switchSheetTab(tabName) {
            const cfgDiv = document.getElementById('sheet-tab-config');
            const guideDiv = document.getElementById('sheet-tab-guide');
            const btnCfg = document.getElementById('sheet-tab-btn-config');
            const btnGuide = document.getElementById('sheet-tab-btn-guide');

            if (tabName === 'config') {
                cfgDiv.classList.remove('hidden');
                guideDiv.classList.add('hidden');
                btnCfg.className = 'px-3.5 py-1.5 rounded-xl bg-[#1a237e] text-white text-xs font-bold transition';
                btnGuide.className = 'px-3.5 py-1.5 rounded-xl bg-slate-100 text-slate-700 hover:bg-slate-200 text-xs font-bold transition';
            } else {
                cfgDiv.classList.add('hidden');
                guideDiv.classList.remove('hidden');
                btnGuide.className = 'px-3.5 py-1.5 rounded-xl bg-[#1a237e] text-white text-xs font-bold transition';
                btnCfg.className = 'px-3.5 py-1.5 rounded-xl bg-slate-100 text-slate-700 hover:bg-slate-200 text-xs font-bold transition';
            }
        }

        function saveGoogleSheetUrl() {
            const inputEl = document.getElementById('google-script-url-input');
            const val = inputEl ? inputEl.value.trim() : '';
            if (val && !val.startsWith('https://script.google.com/')) {
                showToast('⚠️ Sila pastikan URL bermula dengan https://script.google.com/...');
                return;
            }
            if (val) {
                localStorage.setItem(SHEET_URL_STORAGE_KEY, val);
                showToast('✅ URL Google Sheet berjaya disimpan!');
            } else {
                localStorage.removeItem(SHEET_URL_STORAGE_KEY);
                showToast('ℹ️ URL Google Sheet dikosongkan.');
            }
            updateSheetConnectionIndicator();
            if (state.screen === 'complete') render();
        }

        function clearGoogleSheetUrl() {
            localStorage.removeItem(SHEET_URL_STORAGE_KEY);
            const inputEl = document.getElementById('google-script-url-input');
            if (inputEl) inputEl.value = DEFAULT_GOOGLE_SCRIPT_URL;
            updateSheetConnectionIndicator();
            showToast('ℹ️ Tetapan dipulihkan kepada URL lalai penyelidik.');
        }

        async function testGoogleSheetConnection() {
            const inputEl = document.getElementById('google-script-url-input');
            const url = inputEl ? inputEl.value.trim() : getActiveScriptUrl();
            if (!url) {
                showToast('⚠️ Sila masukkan Web App URL terlebih dahulu.');
                return;
            }

            const btn = document.getElementById('btn-test-sheet');
            const origHtml = btn.innerHTML;
            btn.disabled = true;
            btn.innerHTML = '<span>⏳</span> Menguji sambungan...';

            try {
                await fetch(url, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: { 'Content-Type': 'text/plain;charset=utf-8' },
                    body: JSON.stringify({ _action: 'TEST_CONNECTION', timestamp: new Date().toISOString() })
                });
                localStorage.setItem(SHEET_URL_STORAGE_KEY, url);
                updateSheetConnectionIndicator();
                showToast('✅ Isyarat ujian berjaya dihantar ke Google Apps Script!');
            } catch (e) {
                showToast('⚠️ Gagal menyambung ke URL tersebut. Semak semula pautan Web App.');
            } finally {
                btn.disabled = false;
                btn.innerHTML = origHtml;
            }
        }

        function copyAppsScriptSnippet() {
            const temp = document.createElement('textarea');
            temp.value = APPS_SCRIPT_TEMPLATE_CODE;
            document.body.appendChild(temp);
            temp.select();
            document.execCommand('copy');
            document.body.removeChild(temp);
            showToast('📋 Kod Google Apps Script disalin ke papan keratan!');
        }

        function toggleResearcherTools(show) {
            const modal = document.getElementById('tools-modal');
            document.getElementById('reset-confirm-box').classList.add('hidden');
            modal.classList.toggle('hidden', !show);
            modal.classList.toggle('flex', show);
        }

        function requestResetSurvey() {
            document.getElementById('reset-confirm-box').classList.remove('hidden');
        }

        function confirmResetSurvey() {
            localStorage.removeItem(STORAGE_KEY);
            state = {
                screen: 'intro',
                currentIndex: 0,
                langMode: state.langMode,
                answers: {},
                respondentId: null,
                submittedAt: null,
                sheetSyncStatus: 'idle',
                sheetSyncMessage: ''
            };
            toggleResearcherTools(false);
            render();
            showToast('🗑️ Borang soal selidik telah ditetapkan semula.');
        }

        function fillDemoData() {
            state.answers['D1'] = 'Lelaki / Male';
            state.answers['D2'] = '33-42 tahun';
            state.answers['D3'] = 'Sarjana / Master';
            state.answers['D4'] = '6-10 tahun';
            state.answers['D5'] = 'Teknologi Elektronik & Sistem Kawalan';
            state.answers['D6'] = 'Kolej Vokasional Batu Pahat';

            SURVEY_ITEMS.forEach(item => {
                if (item.type === 'likert') {
                    // Realistic PhD expert ratings skewed towards 4 and 5
                    const pool = [4, 4, 5, 5, 5, 3];
                    state.answers[item.id] = pool[Math.floor(Math.random() * pool.length)];
                } else if (item.type === 'textarea') {
                    state.answers[item.id] = 'Integrasi simulasi litar hijau dan audit tenaga bengkel.';
                }
            });
            const datePart = new Date().toISOString().slice(0, 10).replace(/-/g, '');
            const randPart = Math.random().toString(36).substring(2, 6).toUpperCase();
            state.respondentId = `R-${datePart}-${randPart}`;
            state.screen = 'complete';
            state.submittedAt = new Date().toISOString();
            saveState();
            render();
            submitToGoogleSheet();
            showToast('⚡ Data simulasi berjaya diisi untuk ujian analisis!');
        }

        function exportCSV() {
            const payload = buildGoogleSheetPayload();
            const headers = Object.keys(payload);
            const row = headers.map(k => {
                const val = payload[k] !== undefined && payload[k] !== null ? String(payload[k]) : '';
                return `"${val.replace(/"/g, '""')}"`;
            });

            const csvContent = '\uFEFF' + headers.join(',') + '\n' + row.join(',');
            const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            link.href = url;
            link.download = `UTHM_PhD_GreenSkills_TVET_${new Date().toISOString().slice(0, 10)}.csv`;
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
            URL.revokeObjectURL(url);
            showToast('📥 Fail CSV berjaya dimuat turun!');
        }

        function copySummaryJSON() {
            const text = JSON.stringify({
                study: 'UTHM PhD - Green Skills Framework TVET Electronics',
                timestamp: state.submittedAt || new Date().toISOString(),
                responses: state.answers
            }, null, 2);

            const tempArea = document.createElement('textarea');
            tempArea.value = text;
            document.body.appendChild(tempArea);
            tempArea.select();
            document.execCommand('copy');
            document.body.removeChild(tempArea);
            showToast('📋 Rekod jawapan disalin ke papan keratan!');
        }

        function showToast(msg) {
            const box = document.getElementById('toast-box');
            document.getElementById('toast-msg').textContent = msg;
            box.classList.remove('hidden');
            box.classList.add('flex');
            clearTimeout(window._toastTimer);
            window._toastTimer = setTimeout(() => {
                box.classList.add('hidden');
                box.classList.remove('flex');
            }, 3000);
        }

        // =========================================================================
        // 8. KEYBOARD SHORTCUTS (1-5 FOR LIKERT, ARROWS FOR NAVIGATION)
        // =========================================================================
        document.addEventListener('keydown', (e) => {
            if (state.screen !== 'survey') return;
            const activeTag = document.activeElement ? document.activeElement.tagName.toLowerCase() : '';
            if (activeTag === 'input' || activeTag === 'textarea') return;

            const currentItem = SURVEY_ITEMS[state.currentIndex];
            if (currentItem.type === 'likert' && ['1', '2', '3', '4', '5'].includes(e.key)) {
                selectOption(currentItem.id, Number(e.key), true);
            } else if (e.key === 'ArrowRight') {
                nextQuestion();
            } else if (e.key === 'ArrowLeft') {
                prevQuestion();
            }
        });

        // Initialize on Window Load
        window.onload = function () {
            loadState();
            updateSheetConnectionIndicator();
            setLangMode(state.langMode || 'both');
        };
    </script>
</body>
</html>
