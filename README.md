<!-- ... existing code ... -->
      <!-- Persistent Action Buttons -->
      <div class="flex items-center gap-2 sm:gap-3">
        <!-- Quick Nav Drawer Trigger (Visible during survey) -->
        <button id="navDrawerBtn" onclick="toggleNavDrawer(true)" class="hidden items-center gap-1.5 px-3 py-2 rounded-xl text-xs sm:text-sm font-semibold text-slate-700 bg-slate-100 hover:bg-slate-200 transition border border-slate-200">
          <svg class="w-4 h-4 text-uthmPurple" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h10" />
          </svg>
          <span class="hidden md:inline">Senarai Soalan</span>
          <span id="navBadgeCount" class="px-1.5 py-0.5 text-[11px] rounded-md bg-uthmPurple text-white font-bold">0/77</span>
        </button>

        <!-- Persistent Researcher & Supervisor Info Button -->
        <button onclick="toggleResearcherModal(true)" class="flex items-center gap-2 px-3 sm:px-4 py-2 rounded-xl text-xs sm:text-sm font-semibold text-white bg-uthmPurple hover:bg-uthmPurpleLight shadow-sm transition">
          <svg class="w-4 h-4 text-emerald-300 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
          </svg>
          <span class="hidden sm:inline">Maklumat Penyelidik & Penyelia</span>
          <span class="sm:hidden">Penyelidik</span>
        </button>

        <!-- Admin / Researcher Dashboard Trigger -->
        <button onclick="openAdminGate()" class="flex items-center gap-1.5 px-3 sm:px-3.5 py-2 rounded-xl text-xs sm:text-sm font-bold text-emerald-950 bg-emerald-100 hover:bg-emerald-200 border border-emerald-300 shadow-sm transition" title="Panel Admin Penyelidik">
          <svg class="w-4 h-4 text-emerald-700 shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 17v-2m3 2v-4m3 4v-6m2 10H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
          </svg>
          <span class="hidden md:inline">Panel Admin</span>
        </button>
      </div>
    </div>
<!-- ... existing code ... -->
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

            <!-- Cloud Sync Status Banner -->
            <div id="cloudSyncStatus" class="mt-4 inline-flex items-center gap-2.5 px-4 py-2 rounded-2xl bg-slate-100 border border-slate-200 text-xs sm:text-sm font-semibold text-slate-700">
              <span id="cloudSyncSpinner" class="w-4 h-4 border-2 border-uthmPurple border-t-transparent rounded-full animate-spin"></span>
              <span id="cloudSyncText">Menyimpan jawapan anda ke pangkalan data penyelidikan...</span>
            </div>
          </div>

          <!-- Respondent Profile Summary Strip -->
<!-- ... existing code ... -->
          <!-- Footer Review / Reset Actions -->
          <div class="flex flex-wrap items-center justify-between gap-3 pt-2">
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

    <!-- ========================================================= -->
    <!-- VIEW 4: RESEARCHER ADMIN DASHBOARD (LIVE CLOUD DATA)      -->
    <!-- ========================================================= -->
    <section id="adminDashboardView" class="hidden max-w-6xl w-full mx-auto space-y-6 animate-slide-right">
      <!-- Admin Header Card -->
      <div class="bg-white rounded-3xl shadow-xl border border-slate-200 overflow-hidden">
        <div class="h-2.5 w-full bg-gradient-to-r from-uthmPurple via-emeraldGreen to-uthmRed"></div>
        <div class="p-6 sm:p-8">
          <div class="flex flex-col lg:flex-row lg:items-center justify-between gap-4 pb-6 border-b border-slate-200">
            <div>
              <div class="flex items-center gap-2 mb-1">
                <span class="px-2.5 py-0.5 rounded-full bg-emerald-100 text-emerald-800 text-xs font-extrabold uppercase tracking-wider flex items-center gap-1.5">
                  <span class="w-2 h-2 rounded-full bg-emerald-600 animate-ping"></span>
                  Paparan Langsung (Live)
                </span>
                <span class="text-xs font-semibold text-slate-500">Penyelidik: Adib Farhan bin Zaime</span>
              </div>
              <h2 class="text-2xl sm:text-3xl font-extrabold text-uthmPurple tracking-tight">
                Panel Admin & Analisis Data Responden
              </h2>
              <p class="text-xs sm:text-sm text-slate-500 mt-1">
                Pemantauan masa nyata bagi semua responden yang telah melengkapkan soal selidik PhD UTHM.
              </p>
            </div>

            <div class="flex flex-wrap items-center gap-2.5">
              <button onclick="downloadAllAdminCSV()" class="px-4 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-xs sm:text-sm font-bold shadow-md transition flex items-center gap-2">
                <span>⬇️</span>
                <span>Muat Turun Semua Data (CSV untuk SPSS)</span>
              </button>
              <button onclick="exitAdminDashboard()" class="px-4 py-3 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 text-xs sm:text-sm font-bold border border-slate-300 transition">
                ← Kembali ke Portal
              </button>
            </div>
          </div>

          <!-- Top KPI Summary Cards -->
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 mt-6">
            <div class="p-5 rounded-2xl bg-gradient-to-br from-uthmPurple to-uthmPurpleLight text-white shadow-md">
              <p class="text-xs font-semibold text-purple-200 uppercase tracking-wider">Jumlah Responden</p>
              <div class="flex items-baseline gap-2 mt-2">
                <span id="adminTotalRespondents" class="text-4xl font-extrabold">0</span>
                <span class="text-xs text-purple-200">orang pendidik TVET</span>
              </div>
              <p id="adminLastUpdated" class="text-[11px] text-purple-200 mt-2">Menunggu penyegerakan...</p>
            </div>

            <div class="p-5 rounded-2xl bg-purple-50 border border-purple-200">
              <p class="text-xs font-bold text-uthmPurple uppercase tracking-wider">Min Keseluruhan Bhg A</p>
              <p class="text-[11px] text-slate-500">Elemen Pengetahuan (10 Item)</p>
              <div class="flex items-baseline gap-2 mt-2">
                <span id="adminAvgMeanA" class="text-3xl font-extrabold text-uthmPurple">0.00</span>
                <span class="text-xs text-slate-500">/ 5.00</span>
              </div>
              <p id="adminInterpA" class="text-xs font-semibold text-emerald-700 mt-1">-</p>
            </div>

            <div class="p-5 rounded-2xl bg-emerald-50 border border-emerald-200">
              <p class="text-xs font-bold text-emerald-800 uppercase tracking-wider">Min Keseluruhan Bhg B</p>
              <p class="text-[11px] text-slate-500">Elemen Kemahiran (46 Item)</p>
              <div class="flex items-baseline gap-2 mt-2">
                <span id="adminAvgMeanB" class="text-3xl font-extrabold text-emerald-700">0.00</span>
                <span class="text-xs text-slate-500">/ 5.00</span>
              </div>
              <p id="adminInterpB" class="text-xs font-semibold text-emerald-700 mt-1">-</p>
            </div>

            <div class="p-5 rounded-2xl bg-amber-50 border border-amber-200">
              <p class="text-xs font-bold text-amber-800 uppercase tracking-wider">Min Keseluruhan Bhg C</p>
              <p class="text-[11px] text-slate-500">Elemen Sikap & Nilai (12 Item)</p>
              <div class="flex items-baseline gap-2 mt-2">
                <span id="adminAvgMeanC" class="text-3xl font-extrabold text-amber-700">0.00</span>
                <span class="text-xs text-slate-500">/ 5.00</span>
              </div>
              <p id="adminInterpC" class="text-xs font-semibold text-emerald-700 mt-1">-</p>
            </div>
          </div>

          <!-- Demographic Breakdown Grid -->
          <div class="mt-8">
            <h3 class="text-sm font-extrabold text-slate-800 uppercase tracking-wider mb-3 flex items-center gap-2">
              <span>📈</span> Taburan Demografi Responden
            </h3>
            <div id="adminDemographicsGrid" class="grid grid-cols-1 md:grid-cols-3 gap-4">
              <!-- Populated dynamically -->
            </div>
          </div>
        </div>
      </div>

      <!-- Individual Submissions Table Card -->
      <div class="bg-white rounded-3xl shadow-xl border border-slate-200 overflow-hidden">
        <div class="p-6 sm:p-8">
          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-5">
            <div>
              <h3 class="text-lg font-extrabold text-uthmPurple">Senarai Penyerahan Responden Individu</h3>
              <p class="text-xs text-slate-500">Klik "Lihat Jawapan" untuk menyemak skor penuh setiap item dan ulasan terbuka responden.</p>
            </div>
            <div class="relative w-full sm:w-72">
              <input
                type="text"
                id="adminSearchInput"
                oninput="renderAdminTable()"
                placeholder="Cari Kolej Vokasional, subjek, jantina..."
                class="w-full pl-9 pr-4 py-2.5 rounded-xl border border-slate-300 text-xs sm:text-sm focus:border-uthmPurple focus:ring-2 focus:ring-purple-100 outline-none"
              />
              <span class="absolute left-3 top-2.5 text-slate-400 text-sm">🔍</span>
            </div>
          </div>

          <div class="overflow-x-auto rounded-2xl border border-slate-200">
            <table class="w-full text-left border-collapse text-xs sm:text-sm">
              <thead>
                <tr class="bg-slate-100 text-slate-700 border-b border-slate-200">
                  <th class="py-3.5 px-4 font-bold">Bil</th>
                  <th class="py-3.5 px-4 font-bold">Tarikh & Masa</th>
                  <th class="py-3.5 px-4 font-bold">Kolej Vokasional</th>
                  <th class="py-3.5 px-4 font-bold">Subjek / Modul</th>
                  <th class="py-3.5 px-4 font-bold">Pengalaman</th>
                  <th class="py-3.5 px-4 font-bold text-center">Min A</th>
                  <th class="py-3.5 px-4 font-bold text-center">Min B</th>
                  <th class="py-3.5 px-4 font-bold text-center">Min C</th>
                  <th class="py-3.5 px-4 font-bold text-right">Tindakan</th>
                </tr>
              </thead>
              <tbody id="adminSubmissionsTbody" class="divide-y divide-slate-200">
                <tr>
                  <td colspan="9" class="py-8 text-center text-slate-500">Memuatkan rekod responden daripada awan...</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>

      <!-- Open-Ended Qualitative Insights Card -->
      <div class="bg-white rounded-3xl shadow-xl border border-slate-200 overflow-hidden">
        <div class="p-6 sm:p-8">
          <h3 class="text-lg font-extrabold text-uthmPurple mb-1">Cadangan & Pandangan Terbuka Responden (Bahagian A, B & C)</h3>
          <p class="text-xs text-slate-500 mb-5">Himpunan cadangan elemen tambahan daripada pakar dan pendidik TVET.</p>
          <div id="adminOpenEndedList" class="space-y-3">
            <p class="text-xs text-slate-500 italic">Tiada ulasan terbuka direkodkan setakat ini.</p>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ========================================================= -->
  <!-- MODAL 1: MAKLUMAT PENYELIDIK & PENYELIA                   -->
  <!-- ========================================================= -->
<!-- ... existing code ... -->
      <div class="p-4 bg-slate-50 border-t border-slate-200 flex items-center justify-between text-xs">
        <div class="flex items-center gap-3">
          <span class="flex items-center gap-1"><span class="w-2.5 h-2.5 rounded-full bg-emerald-500"></span> Dijawab</span>
          <span class="flex items-center gap-1"><span class="w-2.5 h-2.5 rounded-full bg-slate-300"></span> Belum</span>
        </div>
        <button onclick="finishSurveyEarlyCheck()" class="px-4 py-2 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white font-bold transition">
          Lihat Ringkasan / Hantar
        </button>
      </div>
    </div>
  </div>

  <!-- ========================================================= -->
  <!-- MODAL 3: ADMIN PASSCODE GATE                              -->
  <!-- ========================================================= -->
  <div id="adminGateModal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/70 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-md w-full shadow-2xl border border-slate-200 overflow-hidden animate-slide-right">
      <div class="px-6 py-4 bg-uthmPurple text-white flex items-center justify-between">
        <div class="flex items-center gap-2">
          <span>🔐</span>
          <h3 class="font-bold text-base">Akses Panel Admin Penyelidik</h3>
        </div>
        <button onclick="closeAdminGate()" class="w-8 h-8 rounded-lg bg-white/10 hover:bg-white/20 flex items-center justify-center text-white">✕</button>
      </div>
      <div class="p-6 space-y-4">
        <p class="text-xs sm:text-sm text-slate-600 leading-relaxed">
          Sila masukkan kod laluan penyelidik untuk melihat jawapan responden secara langsung dan memuat turun fail data SPSS.
        </p>
        <div class="p-3 rounded-xl bg-amber-50 border border-amber-200 text-xs text-amber-900">
          <strong>Nota Penyelidik:</strong> Kod laluan lalai ialah <code class="px-1.5 py-0.5 rounded bg-amber-200/70 font-mono font-bold">UTHM2026</code>
        </div>
        <div>
          <label for="adminPasscodeInput" class="block text-xs font-bold text-slate-700 mb-1.5">Kod Laluan (Passcode)</label>
          <input
            type="password"
            id="adminPasscodeInput"
            placeholder="Masukkan kod laluan..."
            onkeydown="if(event.key==='Enter') verifyAdminPasscode()"
            class="w-full px-4 py-3 rounded-xl border-2 border-slate-300 focus:border-uthmPurple outline-none text-sm font-semibold"
          />
          <p id="adminPasscodeError" class="hidden text-xs font-semibold text-red-600 mt-1.5">❌ Kod laluan tidak sah. Sila cuba lagi.</p>
        </div>
        <div class="flex justify-end gap-2 pt-2">
          <button onclick="closeAdminGate()" class="px-4 py-2.5 rounded-xl text-xs font-semibold text-slate-600 bg-slate-100 hover:bg-slate-200">Batal</button>
          <button onclick="verifyAdminPasscode()" class="px-5 py-2.5 rounded-xl text-xs font-bold text-white bg-uthmPurple hover:bg-uthmPurpleLight shadow">Buka Dashboard</button>
        </div>
      </div>
    </div>
  </div>

  <!-- ========================================================= -->
  <!-- MODAL 4: INDIVIDUAL RESPONDENT DETAIL VIEW                -->
  <!-- ========================================================= -->
  <div id="respondentDetailModal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-900/70 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-3xl w-full shadow-2xl border border-slate-200 overflow-hidden animate-slide-right">
      <div class="px-6 py-4 bg-uthmPurple text-white flex items-center justify-between">
        <div>
          <h3 class="font-bold text-base">Perincian Jawapan Responden</h3>
          <p id="detailModalSubtitle" class="text-xs text-purple-200">Rekod Penyerahan</p>
        </div>
        <button onclick="closeRespondentDetail()" class="w-8 h-8 rounded-lg bg-white/10 hover:bg-white/20 flex items-center justify-center text-white">✕</button>
      </div>
      <div id="respondentDetailBody" class="p-6 max-h-[75vh] overflow-y-auto space-y-5 text-xs sm:text-sm">
        <!-- Populated dynamically -->
      </div>
      <div class="px-6 py-3.5 bg-slate-50 border-t border-slate-200 flex justify-end">
        <button onclick="closeRespondentDetail()" class="px-5 py-2 rounded-xl bg-uthmPurple text-white text-xs font-bold hover:bg-uthmPurpleLight">Tutup</button>
      </div>
    </div>
  </div>

  <!-- ========================================================= -->
  <!-- FIREBASE CLOUD FIRESTORE & ADMIN SYNC MODULE              -->
  <!-- ========================================================= -->
  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
    import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
    import { getFirestore, collection, doc, setDoc, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

    const appId = typeof __app_id !== 'undefined' ? __app_id : 'uthm-phd-green-skills-portal';
    let db = null;
    let auth = null;
    let currentUser = null;
    let adminUnsubscribe = null;

    async function initCloudBackend() {
      try {
        if (typeof __firebase_config === 'undefined') {
          console.warn('Firebase config not found in environment.');
          return;
        }
        const firebaseConfig = JSON.parse(__firebase_config);
        const app = initializeApp(firebaseConfig);
        auth = getAuth(app);
        db = getFirestore(app);

        onAuthStateChanged(auth, (user) => {
          currentUser = user;
        });

        if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
          await signInWithCustomToken(auth, __initial_auth_token);
        } else {
          await signInAnonymously(auth);
        }
      } catch (err) {
        console.error('Cloud initialization error:', err);
      }
    }

    // Save completed survey response to public Firestore collection so Researcher Admin can view all submissions
    window.syncResponseToCloud = async function(submissionPayload) {
      const statusEl = document.getElementById('cloudSyncStatus');
      const spinnerEl = document.getElementById('cloudSyncSpinner');
      const textEl = document.getElementById('cloudSyncText');

      if (!db) {
        if (spinnerEl) spinnerEl.classList.add('hidden');
        if (textEl) textEl.textContent = '⚠️ Mod luar talian: Sila muat turun fail CSV di bawah untuk dihantar kepada penyelidik.';
        return;
      }

      try {
        if (!auth.currentUser) {
          if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
            await signInWithCustomToken(auth, __initial_auth_token);
          } else {
            await signInAnonymously(auth);
          }
        }
        const user = auth.currentUser;
        if (!user) throw new Error('Authentication required');

        // Use persistent submission ID per session so reviewing/re-submitting updates cleanly without duplicates
        let submissionId = sessionStorage.getItem('uthm_submission_doc_id');
        if (!submissionId) {
          submissionId = `resp_${Date.now()}_${user.uid.slice(0, 6)}`;
          sessionStorage.setItem('uthm_submission_doc_id', submissionId);
        }

        const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'survey_responses', submissionId);
        await setDoc(docRef, {
          ...submissionPayload,
          submissionId,
          uid: user.uid,
          submittedAt: new Date().toISOString()
        });

        if (statusEl) {
          statusEl.className = 'mt-4 inline-flex items-center gap-2.5 px-4 py-2 rounded-2xl bg-emerald-50 border border-emerald-300 text-xs sm:text-sm font-bold text-emerald-800';
        }
        if (spinnerEl) spinnerEl.classList.add('hidden');
        if (textEl) textEl.textContent = '✅ Jawapan anda telah berjaya disimpan ke pangkalan data awan penyelidik!';
      } catch (error) {
        console.error('Firestore save error:', error);
        if (statusEl) {
          statusEl.className = 'mt-4 inline-flex items-center gap-2.5 px-4 py-2 rounded-2xl bg-amber-50 border border-amber-300 text-xs sm:text-sm font-semibold text-amber-800';
        }
        if (spinnerEl) spinnerEl.classList.add('hidden');
        if (textEl) textEl.textContent = '⚠️ Ralat sambungan awan. Sila muat turun fail CSV di bawah sebagai sandaran.';
      }
    };

    // Subscribe to real-time submissions for the Researcher Admin Dashboard
    window.subscribeAdminData = async function() {
      if (!db) return;
      try {
        if (!auth.currentUser) {
          if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
            await signInWithCustomToken(auth, __initial_auth_token);
          } else {
            await signInAnonymously(auth);
          }
        }
        if (!auth.currentUser) return;

        if (adminUnsubscribe) adminUnsubscribe();

        const colRef = collection(db, 'artifacts', appId, 'public', 'data', 'survey_responses');
        adminUnsubscribe = onSnapshot(
          colRef,
          (snapshot) => {
            const records = [];
            snapshot.forEach((docSnap) => {
              records.push({ id: docSnap.id, ...docSnap.data() });
            });
            // Sort newest first in memory (Rule 2: no orderBy in query)
            records.sort((a, b) => new Date(b.submittedAt || 0) - new Date(a.submittedAt || 0));
            window.adminRecordsCache = records;
            window.updateAdminDashboardUI(records);
          },
          (error) => {
            console.error('Admin snapshot error:', error);
          }
        );
      } catch (err) {
        console.error('Subscribe admin error:', err);
      }
    };

    window.unsubscribeAdminData = function() {
      if (adminUnsubscribe) {
        adminUnsubscribe();
        adminUnsubscribe = null;
      }
    };

    initCloudBackend();
  </script>

  <!-- ========================================================= -->
  <!-- JAVASCRIPT APPLICATION LOGIC & FULL QUESTIONNAIRE DATA    -->
  <!-- ========================================================= -->
<!-- ... existing code ... -->
    // Application State
    const STORAGE_KEY = 'uthm_phd_green_skills_responses_v1';
    const ADMIN_PASSCODE = 'UTHM2026';
    let currentIndex = 0;
    let responses = {};
    let autoAdvanceTimer = null;
    window.adminRecordsCache = [];

    // Initialize on load
    window.addEventListener('DOMContentLoaded', () => {
<!-- ... existing code ... -->
    function goHome() {
      document.getElementById('landingView').classList.remove('hidden');
      document.getElementById('surveyView').classList.add('hidden');
      document.getElementById('completionView').classList.add('hidden');
      document.getElementById('adminDashboardView').classList.add('hidden');
      document.getElementById('topProgressContainer').classList.add('hidden');
      document.getElementById('navDrawerBtn').classList.add('hidden');
      document.getElementById('navDrawerBtn').classList.remove('flex');
      if (Object.keys(responses).length > 0) {
        document.getElementById('resumeBtn').classList.remove('hidden');
      }
    }

    function startSurvey(resume = false) {
      if (!resume) {
        currentIndex = 0;
        sessionStorage.removeItem('uthm_submission_doc_id');
      }
      document.getElementById('landingView').classList.add('hidden');
      document.getElementById('completionView').classList.add('hidden');
      document.getElementById('adminDashboardView').classList.add('hidden');
      document.getElementById('surveyView').classList.remove('hidden');
      document.getElementById('topProgressContainer').classList.remove('hidden');
      document.getElementById('navDrawerBtn').classList.remove('hidden');
      document.getElementById('navDrawerBtn').classList.add('flex');
      renderQuestion('right');
    }
<!-- ... existing code ... -->
    function setupKeyboardShortcuts() {
      window.addEventListener('keydown', (e) => {
        const surveyVisible = !document.getElementById('surveyView').classList.contains('hidden');
        const modalOpen = !document.getElementById('researcherModal').classList.contains('hidden') ||
                          !document.getElementById('navDrawerModal').classList.contains('hidden') ||
                          !document.getElementById('adminGateModal').classList.contains('hidden') ||
                          !document.getElementById('respondentDetailModal').classList.contains('hidden');

        if (!surveyVisible || modalOpen) return;
<!-- ... existing code ... -->
    function showCompletionScreen() {
      document.getElementById('landingView').classList.add('hidden');
      document.getElementById('surveyView').classList.add('hidden');
      document.getElementById('adminDashboardView').classList.add('hidden');
      document.getElementById('topProgressContainer').classList.add('hidden');
      document.getElementById('completionView').classList.remove('hidden');

      // Populate Respondent Profile Strip
<!-- ... existing code ... -->
      document.getElementById('partCCountBadge').textContent = `${statsC.answered}/${statsC.total} item`;
      document.getElementById('meanPartC').textContent = statsC.mean;
      document.getElementById('interpPartC').textContent = statsC.interp;

      // Reset sync status visual before pushing to Cloud Firestore
      const statusEl = document.getElementById('cloudSyncStatus');
      const spinnerEl = document.getElementById('cloudSyncSpinner');
      const textEl = document.getElementById('cloudSyncText');
      if (statusEl) {
        statusEl.className = 'mt-4 inline-flex items-center gap-2.5 px-4 py-2 rounded-2xl bg-slate-100 border border-slate-200 text-xs sm:text-sm font-semibold text-slate-700';
      }
      if (spinnerEl) spinnerEl.classList.remove('hidden');
      if (textEl) textEl.textContent = 'Menyimpan jawapan anda ke pangkalan data penyelidikan...';

      if (typeof window.syncResponseToCloud === 'function') {
        window.syncResponseToCloud({
          responses: { ...responses },
          stats: {
            meanA: statsA.mean,
            meanB: statsB.mean,
            meanC: statsC.mean
          }
        });
      }
    }

    function reviewAnswers() {
      currentIndex = 0;
      startSurvey(true);
    }

    function resetSurveyConfirm() {
      responses = {};
      currentIndex = 0;
      localStorage.removeItem(STORAGE_KEY);
      sessionStorage.removeItem('uthm_submission_doc_id');
      document.getElementById('resumeBtn').classList.add('hidden');
      goHome();
    }

    // ==================== ADMIN GATE & DASHBOARD LOGIC ====================
    function openAdminGate() {
      if (sessionStorage.getItem('uthm_admin_unlocked') === 'true') {
        enterAdminDashboard();
        return;
      }
      const modal = document.getElementById('adminGateModal');
      const input = document.getElementById('adminPasscodeInput');
      const err = document.getElementById('adminPasscodeError');
      input.value = '';
      err.classList.add('hidden');
      modal.classList.remove('hidden');
      modal.classList.add('flex');
      setTimeout(() => input.focus(), 80);
    }

    function closeAdminGate() {
      const modal = document.getElementById('adminGateModal');
      modal.classList.add('hidden');
      modal.classList.remove('flex');
    }

    function verifyAdminPasscode() {
      const inputVal = document.getElementById('adminPasscodeInput').value.trim();
      if (inputVal === ADMIN_PASSCODE) {
        sessionStorage.setItem('uthm_admin_unlocked', 'true');
        closeAdminGate();
        enterAdminDashboard();
      } else {
        document.getElementById('adminPasscodeError').classList.remove('hidden');
      }
    }

    function enterAdminDashboard() {
      document.getElementById('landingView').classList.add('hidden');
      document.getElementById('surveyView').classList.add('hidden');
      document.getElementById('completionView').classList.add('hidden');
      document.getElementById('topProgressContainer').classList.add('hidden');
      document.getElementById('navDrawerBtn').classList.add('hidden');
      document.getElementById('navDrawerBtn').classList.remove('flex');
      document.getElementById('adminDashboardView').classList.remove('hidden');

      if (typeof window.subscribeAdminData === 'function') {
        window.subscribeAdminData();
      }
    }

    function exitAdminDashboard() {
      if (typeof window.unsubscribeAdminData === 'function') {
        window.unsubscribeAdminData();
      }
      goHome();
    }

    function getMeanInterpretation(meanVal) {
      const m = Number(meanVal);
      if (!m || m <= 0) return '-';
      if (m >= 4.21) return 'Sangat Tinggi (Sangat Penting)';
      if (m >= 3.41) return 'Tinggi (Penting)';
      if (m >= 2.61) return 'Sederhana (Hampir Penting)';
      if (m >= 1.81) return 'Rendah (Tidak Penting)';
      return 'Sangat Rendah';
    }

    window.updateAdminDashboardUI = function(records) {
      const total = records.length;
      document.getElementById('adminTotalRespondents').textContent = total;
      document.getElementById('adminLastUpdated').textContent = `Dikemas kini: ${new Date().toLocaleTimeString('ms-MY')}`;

      let sumA = 0, countA = 0;
      let sumB = 0, countB = 0;
      let sumC = 0, countC = 0;

      const demoCounts = {
        D1: {},
        D3: {},
        D4: {}
      };

      records.forEach(rec => {
        const s = rec.stats || {};
        if (Number(s.meanA) > 0) { sumA += Number(s.meanA); countA++; }
        if (Number(s.meanB) > 0) { sumB += Number(s.meanB); countB++; }
        if (Number(s.meanC) > 0) { sumC += Number(s.meanC); countC++; }

        const r = rec.responses || {};
        if (r.D1) demoCounts.D1[r.D1] = (demoCounts.D1[r.D1] || 0) + 1;
        if (r.D3) demoCounts.D3[r.D3] = (demoCounts.D3[r.D3] || 0) + 1;
        if (r.D4) demoCounts.D4[r.D4] = (demoCounts.D4[r.D4] || 0) + 1;
      });

      const avgA = countA ? (sumA / countA).toFixed(2) : '0.00';
      const avgB = countB ? (sumB / countB).toFixed(2) : '0.00';
      const avgC = countC ? (sumC / countC).toFixed(2) : '0.00';

      document.getElementById('adminAvgMeanA').textContent = avgA;
      document.getElementById('adminInterpA').textContent = getMeanInterpretation(avgA);

      document.getElementById('adminAvgMeanB').textContent = avgB;
      document.getElementById('adminInterpB').textContent = getMeanInterpretation(avgB);

      document.getElementById('adminAvgMeanC').textContent = avgC;
      document.getElementById('adminInterpC').textContent = getMeanInterpretation(avgC);

      // Render Demographic Cards
      const demoGrid = document.getElementById('adminDemographicsGrid');
      const demoGroups = [
        { title: 'Jantina Responden', data: demoCounts.D1 },
        { title: 'Tahap Pendidikan', data: demoCounts.D3 },
        { title: 'Pengalaman Mengajar', data: demoCounts.D4 }
      ];

      demoGrid.innerHTML = demoGroups.map(group => {
        const entries = Object.entries(group.data);
        const rowsHtml = entries.length
          ? entries.map(([label, cnt]) => {
              const pct = total > 0 ? Math.round((cnt / total) * 100) : 0;
              return `
                <div class="space-y-1">
                  <div class="flex justify-between text-xs">
                    <span class="font-medium text-slate-700 truncate pr-2">${label}</span>
                    <span class="font-bold text-uthmPurple shrink-0">${cnt} (${pct}%)</span>
                  </div>
                  <div class="w-full h-1.5 bg-slate-200 rounded-full overflow-hidden">
                    <div class="h-full bg-uthmPurple rounded-full" style="width: ${pct}%"></div>
                  </div>
                </div>
              `;
            }).join('')
          : '<p class="text-xs text-slate-400 italic">Tiada data</p>';

        return `
          <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200 space-y-2.5">
            <h4 class="text-xs font-extrabold text-slate-800 uppercase">${group.title}</h4>
            ${rowsHtml}
          </div>
        `;
      }).join('');

      renderAdminTable();
      renderAdminOpenEnded(records);
    };

    function renderAdminTable() {
      const tbody = document.getElementById('adminSubmissionsTbody');
      const keyword = (document.getElementById('adminSearchInput')?.value || '').toLowerCase().trim();
      const records = window.adminRecordsCache || [];

      const filtered = records.filter(rec => {
        if (!keyword) return true;
        const r = rec.responses || {};
        const searchable = `${r.D1 || ''} ${r.D3 || ''} ${r.D4 || ''} ${r.D5 || ''} ${r.D6 || ''}`.toLowerCase();
        return searchable.includes(keyword);
      });

      if (filtered.length === 0) {
        tbody.innerHTML = `
          <tr>
            <td colspan="9" class="py-8 text-center text-slate-500">
              ${records.length === 0 ? 'Belum ada responden yang menghantar soal selidik.' : 'Tiada rekod sepadan dengan carian anda.'}
            </td>
          </tr>
        `;
        return;
      }

      tbody.innerHTML = filtered.map((rec, index) => {
        const r = rec.responses || {};
        const s = rec.stats || {};
        const dateStr = rec.submittedAt
          ? new Date(rec.submittedAt).toLocaleString('ms-MY', { dateStyle: 'medium', timeStyle: 'short' })
          : '-';

        return `
          <tr class="hover:bg-purple-50/40 transition">
            <td class="py-3 px-4 font-bold text-slate-600">${index + 1}</td>
            <td class="py-3 px-4 text-slate-600 whitespace-nowrap">${dateStr}</td>
            <td class="py-3 px-4 font-bold text-slate-900">${r.D6 || '-'}</td>
            <td class="py-3 px-4 text-slate-700 max-w-[200px] truncate" title="${r.D5 || ''}">${r.D5 || '-'}</td>
            <td class="py-3 px-4 text-slate-600 whitespace-nowrap">${r.D4 || '-'}</td>
            <td class="py-3 px-4 text-center font-extrabold text-uthmPurple">${s.meanA || '0.00'}</td>
            <td class="py-3 px-4 text-center font-extrabold text-emerald-700">${s.meanB || '0.00'}</td>
            <td class="py-3 px-4 text-center font-extrabold text-amber-700">${s.meanC || '0.00'}</td>
            <td class="py-3 px-4 text-right whitespace-nowrap">
              <button onclick="openRespondentDetail('${rec.id}')" class="px-3 py-1.5 rounded-lg bg-uthmPurple hover:bg-uthmPurpleLight text-white text-xs font-bold transition">
                Lihat Jawapan
              </button>
            </td>
          </tr>
        `;
      }).join('');
    }

    function renderAdminOpenEnded(records) {
      const container = document.getElementById('adminOpenEndedList');
      const items = [];

      records.forEach(rec => {
        const r = rec.responses || {};
        const kv = r.D6 || 'Responden';
        if (r.A_OPEN && r.A_OPEN.trim()) {
          items.push({ part: 'Bahagian A (Pengetahuan)', kv, text: r.A_OPEN.trim() });
        }
        if (r.B_OPEN && r.B_OPEN.trim()) {
          items.push({ part: 'Bahagian B (Kemahiran)', kv, text: r.B_OPEN.trim() });
        }
        if (r.C_OPEN && r.C_OPEN.trim()) {
          items.push({ part: 'Bahagian C (Sikap & Nilai)', kv, text: r.C_OPEN.trim() });
        }
      });

      if (items.length === 0) {
        container.innerHTML = '<p class="text-xs text-slate-500 italic">Tiada ulasan terbuka direkodkan setakat ini.</p>';
        return;
      }

      container.innerHTML = items.map(item => `
        <div class="p-4 rounded-2xl bg-slate-50 border border-slate-200">
          <div class="flex flex-wrap items-center justify-between gap-2 mb-1">
            <span class="text-[11px] font-extrabold uppercase px-2 py-0.5 rounded bg-purple-100 text-uthmPurple">${item.part}</span>
            <span class="text-xs font-semibold text-slate-500">${item.kv}</span>
          </div>
          <p class="text-xs sm:text-sm text-slate-800 leading-relaxed">"${item.text}"</p>
        </div>
      `).join('');
    }

    function openRespondentDetail(docId) {
      const rec = (window.adminRecordsCache || []).find(item => item.id === docId);
      if (!rec) return;

      const r = rec.responses || {};
      const s = rec.stats || {};
      document.getElementById('detailModalSubtitle').textContent = `${r.D6 || 'Kolej Vokasional'} • ${new Date(rec.submittedAt || Date.now()).toLocaleString('ms-MY')}`;

      const body = document.getElementById('respondentDetailBody');
      const itemsHtml = QUESTIONS.map(q => {
        const ans = r[q.id] !== undefined && r[q.id] !== '' ? r[q.id] : '-';
        let badgeClass = 'bg-slate-100 text-slate-700';
        if (q.type === 'likert') {
          const n = Number(ans);
          if (n === 1) badgeClass = 'bg-red-100 text-red-800 border border-red-300';
          else if (n === 2) badgeClass = 'bg-orange-100 text-orange-800 border border-orange-300';
          else if (n === 3) badgeClass = 'bg-yellow-100 text-yellow-800 border border-yellow-300';
          else if (n === 4) badgeClass = 'bg-lime-100 text-lime-800 border border-lime-300';
          else if (n === 5) badgeClass = 'bg-green-100 text-green-800 border border-green-300';
        }
        return `
          <div class="py-2.5 border-b border-slate-100 flex items-start justify-between gap-4">
            <div>
              <span class="text-[11px] font-bold text-uthmPurple">${q.section} [${q.code}]</span>
              <p class="text-slate-800 font-medium">${q.textMs}</p>
            </div>
            <span class="px-3 py-1 rounded-lg font-extrabold text-xs shrink-0 ${badgeClass}">${ans}</span>
          </div>
        `;
      }).join('');

      body.innerHTML = `
        <div class="grid grid-cols-3 gap-3 p-3.5 rounded-2xl bg-slate-50 border border-slate-200 text-center">
          <div><span class="text-[11px] text-slate-500 block">Min Bhg A</span><strong class="text-base text-uthmPurple">${s.meanA || '0.00'}</strong></div>
          <div><span class="text-[11px] text-slate-500 block">Min Bhg B</span><strong class="text-base text-emerald-700">${s.meanB || '0.00'}</strong></div>
          <div><span class="text-[11px] text-slate-500 block">Min Bhg C</span><strong class="text-base text-amber-700">${s.meanC || '0.00'}</strong></div>
        </div>
        <div class="divide-y divide-slate-100">${itemsHtml}</div>
      `;

      const modal = document.getElementById('respondentDetailModal');
      modal.classList.remove('hidden');
      modal.classList.add('flex');
    }

    function closeRespondentDetail() {
      const modal = document.getElementById('respondentDetailModal');
      modal.classList.add('hidden');
      modal.classList.remove('flex');
    }

    // ==================== NAVIGATION DRAWER & RESEARCHER MODAL HELPERS ====================
    function toggleNavDrawer(show) {
      const modal = document.getElementById('navDrawerModal');
      if (!modal) return;
      if (show) {
        if (typeof renderNavDrawerGrid === 'function') {
          renderNavDrawerGrid();
        }
        modal.classList.remove('hidden');
        modal.classList.add('flex');
      } else {
        modal.classList.add('hidden');
        modal.classList.remove('flex');
      }
    }

    function toggleResearcherModal(show) {
      const modal = document.getElementById('researcherModal');
      if (!modal) return;
      if (show) {
        modal.classList.remove('hidden');
        modal.classList.add('flex');
      } else {
        modal.classList.add('hidden');
        modal.classList.remove('flex');
      }
    }

    function finishSurveyEarlyCheck() {
      toggleNavDrawer(false);
      showCompletionScreen();
    }

    // Expose all inline onclick handlers explicitly on window to prevent ReferenceErrors
    window.toggleNavDrawer = toggleNavDrawer;
    window.toggleResearcherModal = toggleResearcherModal;
    window.finishSurveyEarlyCheck = finishSurveyEarlyCheck;
    window.openAdminGate = openAdminGate;
    window.closeAdminGate = closeAdminGate;
    window.verifyAdminPasscode = verifyAdminPasscode;
    window.enterAdminDashboard = enterAdminDashboard;
    window.exitAdminDashboard = exitAdminDashboard;
    window.renderAdminTable = renderAdminTable;
    window.openRespondentDetail = openRespondentDetail;
    window.closeRespondentDetail = closeRespondentDetail;
    window.downloadAllAdminCSV = downloadAllAdminCSV;
    window.goHome = goHome;
    window.startSurvey = startSurvey;
    window.reviewAnswers = reviewAnswers;
    window.resetSurveyConfirm = resetSurveyConfirm;

    function downloadAllAdminCSV() {
      const records = window.adminRecordsCache || [];
      if (records.length === 0) return;

      const headers = ['ID_Rekod', 'Tarikh_Hantar'];
      QUESTIONS.forEach(q => {
        headers.push(`"${q.id}_${q.code}"`);
      });
      headers.push('Min_Bahagian_A', 'Min_Bahagian_B', 'Min_Bahagian_C');

      const csvRows = [headers.join(',')];

      records.forEach(rec => {
        const r = rec.responses || {};
        const s = rec.stats || {};
        const row = [
          `"${rec.id || ''}"`,
          `"${rec.submittedAt || ''}"`
        ];

        QUESTIONS.forEach(q => {
          const val = r[q.id] !== undefined && r[q.id] !== null ? String(r[q.id]) : '';
          row.push(`"${val.replace(/"/g, '""')}"`);
        });

        row.push(s.meanA || '', s.meanB || '', s.meanC || '');
        csvRows.push(row.join(','));
      });

      const csvContent = '\uFEFF' + csvRows.join('\n');
      const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url;
      a.download = `Semua_Data_Responden_PhD_UTHM_${Date.now()}.csv`;
      document.body.appendChild(a);
      a.click();
      document.body.removeChild(a);
      URL.revokeObjectURL(url);
    }

    // ==================== EXPORT FUNCTIONS (CSV / JSON / CLIPBOARD) ====================
<!-- ... existing code ... -->
