<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kalkulator Raport MDTA Asysyifa Al-Musri'</title>
  
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts: Plus Jakarta Sans untuk tampilan modern -->
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  
  <style>
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      background-color: #F8FAFC;
      background-image: radial-gradient(#E2E8F0 1px, transparent 1px);
      background-size: 24px 24px;
    }
    
    /* Smooth Scrollbar */
    ::-webkit-scrollbar { width: 8px; height: 8px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
    ::-webkit-scrollbar-thumb:hover { background: #94a3b8; }

    @keyframes slideUpFade {
      from { opacity: 0; transform: translateY(12px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .animate-slideUp {
      animation: slideUpFade 0.5s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }
    
    /* Hilangkan panah pada input number */
    input[type=number]::-webkit-inner-spin-button, 
    input[type=number]::-webkit-outer-spin-button { 
      -webkit-appearance: none; margin: 0; 
    }

    /* Print Styles yang dioptimalkan */
    @media print {
      body { background: white !important; }
      header, .no-print, button, form, .modal { display: none !important; }
      .print-full-width { 
        width: 100% !important; max-width: 100% !important; 
        border: none !important; box-shadow: none !important; margin: 0 !important; padding: 0 !important;
      }
      .print-table th { background-color: #f1f5f9 !important; -webkit-print-color-adjust: exact; }
    }
  </style>
</head>
<body class="text-slate-800 antialiased min-h-screen pb-20 overflow-x-hidden relative">

  <div class="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-indigo-400/20 rounded-full blur-[120px] -z-10 pointer-events-none"></div>
  <div class="absolute top-[20%] right-[-5%] w-[30%] h-[30%] bg-blue-400/20 rounded-full blur-[100px] -z-10 pointer-events-none"></div>

  <header class="sticky top-4 z-40 mx-4 lg:mx-auto max-w-7xl transition-all duration-300">
    <div class="bg-white/80 backdrop-blur-xl border border-white/40 shadow-sm shadow-slate-200/50 rounded-2xl px-5 py-3.5 flex items-center justify-between">
      <div class="flex items-center space-x-3 sm:space-x-4">
        <!-- Logo MDTA dengan efek mix-blend untuk menyamarkan background putih -->
        <img src="IMG-20260530-WA0020.jpg" alt="Logo MDTA Asy Syifa Al Musri" class="w-12 h-12 sm:w-14 sm:h-14 object-contain mix-blend-multiply transition-transform hover:scale-105" onerror="this.onerror=null; this.src='https://placehold.co/100x100/1e1b4b/ffffff?text=MDTA';" />
        
        <div>
          <h1 class="text-base sm:text-lg font-extrabold tracking-tight text-slate-900 leading-tight">MDTA Asy Syifa</h1>
          <p class="text-[10px] sm:text-[11px] text-indigo-600 font-bold tracking-wider uppercase">Sistem Kalkulasi Raport</p>
        </div>
      </div>
      <div class="no-print hidden sm:flex items-center space-x-3">
        <div class="flex items-center px-3 py-1.5 bg-slate-100 rounded-lg border border-slate-200/60">
          <span class="relative flex h-2.5 w-2.5 mr-2">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-indigo-400 opacity-75"></span>
            <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-indigo-500"></span>
          </span>
          <span class="text-xs font-semibold text-slate-600">Sistem Aktif</span>
        </div>
      </div>
    </div>
  </header>

  <div id="notification-toast" class="fixed bottom-8 right-8 z-50 flex items-start space-x-3 px-4 py-4 rounded-2xl shadow-2xl bg-white border border-slate-100 hidden transition-all duration-300 transform max-w-sm w-full">
    <div id="toast-icon-container" class="mt-0.5 p-1.5 rounded-full flex-shrink-0">
      <!-- Icon dinamis -->
    </div>
    <div class="flex-1">
      <h4 id="notification-title" class="text-sm font-bold text-slate-900">Pemberitahuan</h4>
      <p id="notification-text" class="text-xs text-slate-500 font-medium mt-0.5 leading-relaxed"></p>
    </div>
  </div>

  <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 space-y-8 print-full-width animate-slideUp">

    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 no-print">
      
      <!-- KARTU UTAMA RUMUS AKTIF -->
      <div class="lg:col-span-2 bg-slate-900 rounded-[2rem] p-8 relative overflow-hidden shadow-xl shadow-slate-900/10 flex flex-col justify-between group border border-slate-800">
        <!-- Mesh Gradient Background -->
        <div class="absolute inset-0 bg-gradient-to-br from-indigo-600/40 via-purple-600/20 to-blue-600/40 opacity-50 group-hover:opacity-70 transition-opacity duration-700"></div>
        <div class="absolute -top-24 -right-24 w-96 h-96 bg-indigo-500/30 blur-[80px] rounded-full"></div>
        
        <div class="relative z-10 space-y-4 max-w-lg">
          <div class="inline-flex items-center px-3 py-1.5 rounded-xl bg-white/10 backdrop-blur-md border border-white/10 text-xs font-semibold text-indigo-100">
            <svg class="w-4 h-4 mr-2 text-indigo-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>
            Kalkulasi Real-time
          </div>
          <h2 class="text-3xl font-extrabold text-white tracking-tight leading-tight">Penentuan Nilai Akhir <br/><span class="text-transparent bg-clip-text bg-gradient-to-r from-indigo-300 to-blue-200">Berdasarkan Bobot</span></h2>
          <p class="text-sm text-slate-300 font-medium leading-relaxed">
            Sistem otomatis menghitung nilai akhir santri berdasarkan indikator yang Anda sesuaikan. Pastikan akumulasi bobot selalu berada di angka 100%.
          </p>
        </div>

        <div class="relative z-10 mt-8 pt-5 border-t border-white/10 grid grid-cols-2 sm:grid-cols-4 gap-4">
          <div class="bg-white/5 backdrop-blur-sm rounded-xl p-3 border border-white/5 text-center">
            <p class="text-[10px] text-slate-400 font-bold uppercase tracking-wider mb-1">Harian</p>
            <p class="text-lg font-black text-white"><span id="info-weight-harian">40</span>%</p>
          </div>
          <div id="info-badge-uts" class="hidden bg-white/5 backdrop-blur-sm rounded-xl p-3 border border-white/5 text-center flex-col justify-center">
            <p class="text-[10px] text-amber-400/80 font-bold uppercase tracking-wider mb-1">UTS</p>
            <p class="text-lg font-black text-amber-100"><span id="info-weight-uts">0</span>%</p>
          </div>
          <div class="bg-white/5 backdrop-blur-sm rounded-xl p-3 border border-white/5 text-center">
            <p class="text-[10px] text-slate-400 font-bold uppercase tracking-wider mb-1">UAS</p>
            <p class="text-lg font-black text-white"><span id="info-weight-uas">40</span>%</p>
          </div>
          <div class="bg-white/5 backdrop-blur-sm rounded-xl p-3 border border-white/5 text-center">
            <p class="text-[10px] text-slate-400 font-bold uppercase tracking-wider mb-1">Kehadiran</p>
            <p class="text-lg font-black text-white"><span id="info-weight-kehadiran">20</span>%</p>
          </div>
        </div>
      </div>

      <div class="bg-white p-7 rounded-[2rem] border border-slate-200/60 shadow-lg shadow-slate-200/40 space-y-6">
        <div class="flex items-center space-x-3">
          <div class="p-2 bg-indigo-50 rounded-xl text-indigo-600"><svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6V4m0 2a2 2 0 100 4m0-4a2 2 0 110 4m-6 8a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4m6 6v10m6-2a2 2 0 100-4m0 4a2 2 0 110-4m0 4v2m0-6V4" /></svg></div>
          <h3 class="font-extrabold text-slate-900 text-sm uppercase tracking-wider">Konfigurasi</h3>
        </div>

        <div class="space-y-4">
          <!-- Skema Penilaian -->
          <div class="space-y-2">
            <div class="flex justify-between items-center">
              <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider">Skema Evaluasi</label>
            </div>
            <div class="flex p-1 bg-slate-100/80 rounded-xl border border-slate-200/50">
              <button type="button" onclick="setGradingScheme('scheme1')" id="btn-scheme-1" class="flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 bg-white text-indigo-700 shadow-sm border border-slate-200/50">Tanpa UTS</button>
              <button type="button" onclick="setGradingScheme('scheme2')" id="btn-scheme-2" class="flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 text-slate-500 hover:text-slate-800">Ada UTS</button>
            </div>
          </div>

          <!-- Skema Absensi -->
          <div class="space-y-2">
            <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider">Format Absensi</label>
            <div class="flex p-1 bg-slate-100/80 rounded-xl border border-slate-200/50">
              <button type="button" onclick="setAttendanceMode('direct')" id="btn-mode-direct" class="flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 bg-white text-indigo-700 shadow-sm border border-slate-200/50">Skor (0-100)</button>
              <button type="button" onclick="setAttendanceMode('meetings')" id="btn-mode-meetings" class="flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 text-slate-500 hover:text-slate-800">Total Hari</button>
            </div>
          </div>

          <div id="container-total-meetings" class="hidden space-y-1.5 animate-slideUp">
            <label class="text-[10px] font-bold text-indigo-600 uppercase tracking-wider">Max Pertemuan (Hari)</label>
            <input type="number" id="weight-total-meetings" value="20" min="1" oninput="handleTotalMeetingsChange(this.value)" class="w-full px-4 py-2.5 bg-indigo-50/50 border border-indigo-100 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-sm font-bold text-slate-800" />
          </div>
        </div>

        <!-- Input Bobot -->
        <div class="pt-5 border-t border-slate-100 space-y-3">
          <div class="flex items-center justify-between">
            <span class="text-[11px] font-bold text-slate-500 uppercase tracking-wider">Distribusi Bobot</span>
            <span id="weight-sum-badge" class="px-2.5 py-1 rounded-lg text-xs font-bold bg-indigo-50 text-indigo-700 border border-indigo-100">Total: 100%</span>
          </div>

          <div id="weight-grid-container" class="grid grid-cols-3 gap-2.5">
            <div class="space-y-1">
              <label class="text-[10px] font-bold text-slate-400 block text-center">Harian</label>
              <div class="relative">
                <input type="number" id="weight-harian" value="40" oninput="handleWeightUpdate()" class="w-full pl-2 pr-6 py-2 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-center font-bold text-sm text-slate-800" />
                <span class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold text-slate-400">%</span>
              </div>
            </div>
            <div id="container-weight-uts" class="space-y-1 hidden">
              <label class="text-[10px] font-bold text-slate-400 block text-center">UTS</label>
              <div class="relative">
                <input type="number" id="weight-uts" value="0" oninput="handleWeightUpdate()" class="w-full pl-2 pr-6 py-2 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-center font-bold text-sm text-slate-800" />
                <span class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold text-slate-400">%</span>
              </div>
            </div>
            <div class="space-y-1">
              <label class="text-[10px] font-bold text-slate-400 block text-center">UAS</label>
              <div class="relative">
                <input type="number" id="weight-uas" value="40" oninput="handleWeightUpdate()" class="w-full pl-2 pr-6 py-2 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-center font-bold text-sm text-slate-800" />
                <span class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold text-slate-400">%</span>
              </div>
            </div>
            <div class="space-y-1">
              <label class="text-[10px] font-bold text-slate-400 block text-center">Absen</label>
              <div class="relative">
                <input type="number" id="weight-kehadiran" value="20" oninput="handleWeightUpdate()" class="w-full pl-2 pr-6 py-2 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-center font-bold text-sm text-slate-800" />
                <span class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold text-slate-400">%</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-5 no-print">
      <div class="bg-white p-5 rounded-2xl border border-slate-200/60 shadow-sm flex items-center space-x-4">
        <div class="w-12 h-12 rounded-full bg-blue-50 text-blue-600 flex items-center justify-center">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" /></svg>
        </div>
        <div>
          <p class="text-[11px] font-bold text-slate-400 uppercase tracking-wider">Rata-Rata Kelas</p>
          <h4 id="stat-average" class="text-2xl font-black text-slate-800 mt-0.5">0.0</h4>
        </div>
      </div>

      <div class="bg-white p-5 rounded-2xl border border-slate-200/60 shadow-sm flex items-center space-x-4">
        <div class="w-12 h-12 rounded-full bg-emerald-50 text-emerald-600 flex items-center justify-center">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.957 11.957 0 01-5.618 3.03A12.006 12.006 0 002 12c0 5.589 4.316 10.158 9.8 11.144a11.93 11.93 0 002.4 0C19.684 22.158 24 17.589 24 12a12.006 12.006 0 00-3.618-6.016z" /></svg>
        </div>
        <div>
          <p class="text-[11px] font-bold text-slate-400 uppercase tracking-wider">Nilai Tertinggi</p>
          <h4 id="stat-highest" class="text-2xl font-black text-slate-800 mt-0.5">0.0</h4>
        </div>
      </div>

      <div class="bg-white p-5 rounded-2xl border border-slate-200/60 shadow-sm flex items-center space-x-4">
        <div class="w-12 h-12 rounded-full bg-purple-50 text-purple-600 flex items-center justify-center">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" /></svg>
        </div>
        <div>
          <p class="text-[11px] font-bold text-slate-400 uppercase tracking-wider">Total Santri</p>
          <h4 id="stat-total" class="text-2xl font-black text-slate-800 mt-0.5">0</h4>
        </div>
      </div>
    </div>

    <div id="weight-warning-banner" class="bg-rose-50 border border-rose-200 p-4 rounded-2xl text-rose-800 hidden no-print">
      <div class="flex items-start space-x-3">
        <svg class="w-5 h-5 flex-shrink-0 mt-0.5 text-rose-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" /></svg>
        <div>
          <h4 class="font-bold text-sm">Akumulasi Bobot Tidak Valid</h4>
          <p class="text-xs mt-1 font-medium">Persentase total bobot harus tepat 100%. Silakan sesuaikan panel konfigurasi di atas.</p>
        </div>
      </div>
    </div>

    <div class="grid grid-cols-1 xl:grid-cols-4 gap-8 items-start">
      
      <!-- FORM INPUT KIRI -->
      <div class="bg-white p-6 rounded-[2rem] border border-slate-200/60 shadow-lg shadow-slate-200/40 xl:sticky xl:top-28 no-print">
        <div class="mb-6">
          <h3 class="font-extrabold text-slate-900 text-lg">Input Data</h3>
          <p class="text-xs text-slate-500 mt-1 font-medium">Tambahkan nilai santri secara manual.</p>
        </div>

        <form id="add-student-form" onsubmit="handleAddStudent(event)" class="space-y-4">
          <div class="space-y-1.5">
            <label class="text-[11px] font-bold text-slate-500 uppercase tracking-wider">Nama Lengkap</label>
            <input type="text" id="student-name" placeholder="Contoh: Muhammad Raihan" class="w-full px-4 py-3 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-sm font-semibold" required />
          </div>

          <div id="form-grid-container" class="grid grid-cols-2 gap-3">
            <div class="space-y-1.5">
              <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider">Harian</label>
              <input type="number" id="grade-harian" min="0" max="100" placeholder="0-100" class="w-full px-3 py-2.5 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-sm font-bold text-center" required />
            </div>
            <div id="container-input-uts" class="space-y-1.5 hidden">
              <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider">UTS</label>
              <input type="number" id="grade-uts" min="0" max="100" placeholder="0-100" class="w-full px-3 py-2.5 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-sm font-bold text-center" />
            </div>
            <div class="space-y-1.5">
              <label class="text-[10px] font-bold text-slate-500 uppercase tracking-wider">UAS</label>
              <input type="number" id="grade-uas" min="0" max="100" placeholder="0-100" class="w-full px-3 py-2.5 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-sm font-bold text-center" required />
            </div>
            <div class="space-y-1.5">
              <label id="label-attendance-input" class="text-[10px] font-bold text-slate-500 uppercase tracking-wider">Absen</label>
              <input type="number" id="grade-kehadiran" min="0" max="100" placeholder="0-100" class="w-full px-3 py-2.5 bg-slate-50 border border-slate-200 rounded-xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 focus:border-indigo-400 transition-all text-sm font-bold text-center" required />
            </div>
          </div>

          <button type="submit" class="w-full mt-6 flex items-center justify-center space-x-2 py-3.5 bg-slate-900 hover:bg-indigo-600 text-white rounded-xl font-bold text-sm shadow-lg shadow-slate-900/20 hover:shadow-indigo-600/30 transform active:scale-[0.98] transition-all duration-300">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" /></svg>
            <span>Tambahkan</span>
          </button>
        </form>
      </div>

      <div class="xl:col-span-3 bg-white rounded-[2rem] border border-slate-200/60 shadow-lg shadow-slate-200/40 overflow-hidden print-full-width flex flex-col min-h-[500px]">
        <div class="px-6 py-5 border-b border-slate-100 flex flex-col sm:flex-row sm:items-center sm:justify-between gap-4">
          <div>
            <h3 class="font-extrabold text-slate-900 text-lg">Lembar Penilaian</h3>
          </div>
          <div class="flex flex-wrap items-center gap-2 no-print">
            <button onclick="openBulkModal()" class="px-3.5 py-2 text-[11px] font-bold text-slate-600 bg-slate-50 border border-slate-200 hover:bg-slate-100 hover:text-indigo-600 rounded-lg transition-all flex items-center space-x-1.5">
              <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" /></svg>
              <span>Impor Teks</span>
            </button>
            <button onclick="openExportModal()" class="px-3.5 py-2 text-[11px] font-bold text-slate-600 bg-slate-50 border border-slate-200 hover:bg-slate-100 hover:text-indigo-600 rounded-lg transition-all flex items-center space-x-1.5">
              <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"/></svg>
              <span>Ekspor</span>
            </button>
            <button onclick="triggerConfirmDialog('Hapus semua data santri secara permanen?', clearAllData)" class="px-3.5 py-2 text-[11px] font-bold text-rose-600 bg-rose-50 border border-rose-100 hover:bg-rose-100 rounded-lg transition-all">
              Kosongkan
            </button>
          </div>
        </div>

        <div class="overflow-x-auto flex-1 print-table">
          <table class="w-full text-left border-collapse min-w-[750px]">
            <thead>
              <tr class="border-b border-slate-200 bg-slate-50/50 text-[10px] font-bold text-slate-500 uppercase tracking-wider">
                <th class="px-5 py-4 w-12 text-center">No</th>
                <th class="px-4 py-4 min-w-[180px]">Nama Lengkap</th>
                <th class="px-2 py-4 text-center w-20">Harian</th>
                <th id="header-col-uts" class="px-2 py-4 text-center w-20 hidden text-indigo-600">UTS</th>
                <th class="px-2 py-4 text-center w-20">UAS</th>
                <th class="px-2 py-4 text-center w-20" id="header-kehadiran-col">Absen</th>
                <th class="px-4 py-4 text-center w-24 bg-indigo-50/30 text-indigo-800">Nilai Akhir</th>
                <th class="px-4 py-4 text-center w-24">Predikat</th>
                <th class="px-4 py-4 text-right w-16 no-print">Aksi</th>
              </tr>
            </thead>
            <tbody id="students-table-body" class="divide-y divide-slate-100 text-sm">
              <!-- Baris data JS -->
            </tbody>
          </table>
          
          <div id="empty-state" class="py-24 text-center space-y-4 hidden flex-col items-center justify-center">
            <div class="w-16 h-16 bg-slate-100 rounded-2xl flex items-center justify-center text-slate-300 transform rotate-3">
              <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 13V6a2 2 0 00-2-2H6a2 2 0 00-2 2v7m16 0v5a2 2 0 01-2 2H6a2 2 0 01-2-2v-5m16 0h-2.586a1 1 0 00-.707.293l-2.414 2.414a1 1 0 01-.707.293h-3.172a1 1 0 01-.707-.293l-2.414-2.414A1 1 0 006.586 13H4" /></svg>
            </div>
            <div>
              <h5 class="font-extrabold text-slate-700 text-base">Belum Ada Data</h5>
              <p class="text-sm text-slate-400 mt-1">Tambahkan santri di panel kiri atau impor data.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>

  <!-- MODAL IMPOR -->
  <div id="bulk-modal" class="fixed inset-0 z-50 flex items-center justify-center bg-slate-900/40 backdrop-blur-sm p-4 hidden modal">
    <div class="bg-white w-full max-w-lg rounded-[2rem] shadow-2xl border border-slate-100 overflow-hidden transform transition-all duration-300 scale-95 opacity-0" id="bulk-modal-content">
      <div class="px-6 py-5 border-b border-slate-100 flex items-center justify-between bg-slate-50/50">
        <h3 class="font-extrabold text-slate-900 text-lg">Impor Data Massal</h3>
        <button onclick="closeBulkModal()" class="text-slate-400 hover:text-slate-700 bg-slate-100 hover:bg-slate-200 p-1.5 rounded-full transition-colors"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg></button>
      </div>
      <div class="p-6 space-y-4">
        <div class="bg-indigo-50/50 p-4 rounded-2xl border border-indigo-100/50">
          <h4 class="text-xs font-bold text-indigo-900 mb-1">Panduan Format Teks</h4>
          <p id="bulk-format-helper" class="text-[11px] text-indigo-700/70 font-medium leading-relaxed"></p>
        </div>
        <textarea id="bulk-input-text" rows="6" placeholder="Ketik atau tempel data di sini..." class="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl focus:bg-white focus:outline-none focus:ring-2 focus:ring-indigo-500/20 text-xs font-mono leading-relaxed resize-none"></textarea>
        <div class="flex justify-end space-x-3 pt-2">
          <button onclick="closeBulkModal()" class="px-5 py-2.5 text-xs font-bold text-slate-600 bg-slate-100 hover:bg-slate-200 rounded-xl transition-colors">Batal</button>
          <button onclick="handleBulkTextParse()" class="px-6 py-2.5 bg-indigo-600 hover:bg-indigo-700 text-white text-xs font-bold rounded-xl shadow-md transition-colors">Proses Data</button>
        </div>
      </div>
    </div>
  </div>

  <!-- MODAL EKSPOR -->
  <div id="export-modal" class="fixed inset-0 z-50 flex items-center justify-center bg-slate-900/40 backdrop-blur-sm p-4 hidden modal">
    <div class="bg-white w-full max-w-sm rounded-[2rem] shadow-2xl border border-slate-100 overflow-hidden transform transition-all duration-300 scale-95 opacity-0" id="export-modal-content">
      <div class="px-6 py-5 border-b border-slate-100 flex items-center justify-between">
        <h3 class="font-extrabold text-slate-900 text-lg">Ekspor Laporan</h3>
        <button onclick="closeExportModal()" class="text-slate-400 hover:text-slate-700 bg-slate-100 hover:bg-slate-200 p-1.5 rounded-full transition-colors"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg></button>
      </div>
      <div class="p-6 space-y-3">
        <button onclick="copyWhatsAppReport()" class="w-full flex items-center justify-between px-5 py-3.5 bg-emerald-50 text-emerald-700 rounded-2xl hover:bg-emerald-100 border border-emerald-200/60 transition-all group">
          <div class="flex items-center space-x-3">
            <div class="p-2 bg-emerald-100 rounded-lg group-hover:bg-emerald-200"><svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51a12.8 12.8 0 0 0-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413Z"/></svg></div>
            <span class="font-bold text-sm">Salin ke WhatsApp</span>
          </div>
        </button>
        <button onclick="downloadCSV()" class="w-full flex items-center justify-between px-5 py-3.5 bg-blue-50 text-blue-700 rounded-2xl hover:bg-blue-100 border border-blue-200/60 transition-all group">
          <div class="flex items-center space-x-3">
            <div class="p-2 bg-blue-100 rounded-lg group-hover:bg-blue-200"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"/></svg></div>
            <span class="font-bold text-sm">Unduh File Excel (.csv)</span>
          </div>
        </button>
        <button onclick="executePrint()" class="w-full flex items-center justify-between px-5 py-3.5 bg-slate-50 text-slate-700 rounded-2xl hover:bg-slate-100 border border-slate-200/60 transition-all group">
          <div class="flex items-center space-x-3">
            <div class="p-2 bg-slate-200 rounded-lg group-hover:bg-slate-300"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 17h2a2 2 0 002-2v-5a2 2 0 00-2-2H5a2 2 0 00-2 2v5a2 2 0 002 2h2m2 4h10a2 2 0 002-2v-4a2 2 0 00-2-2H9a2 2 0 00-2 2v4a2 2 0 002 2zm8-12V5a2 2 0 00-2-2H9a2 2 0 00-2 2v4h10z"/></svg></div>
            <span class="font-bold text-sm">Cetak PDF / Dokumen</span>
          </div>
        </button>
      </div>
    </div>
  </div>

  <!-- MODAL KONFIRMASI -->
  <div id="confirm-modal" class="fixed inset-0 z-50 flex items-center justify-center bg-slate-900/40 backdrop-blur-sm p-4 hidden modal">
    <div class="bg-white w-full max-w-sm rounded-[2rem] shadow-2xl border border-slate-100 overflow-hidden transform transition-all duration-300 scale-95 opacity-0" id="confirm-modal-content">
      <div class="p-8 text-center space-y-5">
        <div class="inline-flex p-4 bg-rose-50 text-rose-600 rounded-full">
          <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" /></svg>
        </div>
        <div>
          <h3 class="font-extrabold text-slate-900 text-lg">Konfirmasi</h3>
          <p id="confirm-modal-text" class="text-sm text-slate-500 font-medium mt-1"></p>
        </div>
        <div class="flex justify-center space-x-3 pt-2">
          <button onclick="closeConfirmModal()" class="px-5 py-2.5 text-xs font-bold text-slate-600 bg-slate-100 hover:bg-slate-200 rounded-xl transition-colors">Batal</button>
          <button id="btn-confirm-action" class="px-6 py-2.5 bg-rose-600 hover:bg-rose-700 text-white text-xs font-bold rounded-xl shadow-md transition-colors">Ya, Lanjutkan</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // State Aplikasi
    let students = [
      { id: '1', name: "Ahmad Fauzi", harian: 85, uts: 80, uas: 80, kehadiran: 95 },
      { id: '2', name: "Siti Aminah", harian: 90, uts: 88, uas: 85, kehadiran: 100 }
    ];

    let activeScheme = 'scheme1';
    let attendanceMode = 'direct'; 
    let totalMeetings = 20;

    let weights = { harian: 40, uts: 0, uas: 40, kehadiran: 20 };
    let activeConfirmCallback = null;

    window.onload = function() {
      syncInputsWithState();
      renderApp();
    };

    function syncInputsWithState() {
      document.getElementById('weight-harian').value = weights.harian;
      document.getElementById('weight-uts').value = weights.uts;
      document.getElementById('weight-uas').value = weights.uas;
      document.getElementById('weight-kehadiran').value = weights.kehadiran;
      document.getElementById('weight-total-meetings').value = totalMeetings;
      updateWeightTexts();
    }

    function isWeightValid() {
      return (weights.harian + weights.uts + weights.uas + weights.kehadiran) === 100;
    }

    function getKehadiranScore(value) {
      if (attendanceMode === 'meetings') {
        return Math.min(100, parseFloat(((parseFloat(value) || 0) / totalMeetings) * 100).toFixed(1));
      }
      return parseFloat(value) || 0;
    }

    function calculateSingleGradeValue(st) {
      if (!isWeightValid()) return 0;
      const h = parseFloat(st.harian) || 0;
      const ut = (activeScheme === 'scheme2') ? (parseFloat(st.uts) || 0) : 0;
      const ua = parseFloat(st.uas) || 0;
      const k = getKehadiranScore(st.kehadiran);

      return parseFloat((((h * weights.harian) + (ut * weights.uts) + (ua * weights.uas) + (k * weights.kehadiran)) / 100).toFixed(1));
    }

    function getGradeLetterInfo(score) {
      if (!isWeightValid()) return { letter: "-", color: "text-slate-400 bg-slate-100" };
      if (score >= 85) return { letter: "A", color: "text-indigo-700 bg-indigo-50 border-indigo-200" };
      if (score >= 75) return { letter: "B", color: "text-emerald-700 bg-emerald-50 border-emerald-200" };
      if (score >= 65) return { letter: "C", color: "text-amber-700 bg-amber-50 border-amber-200" };
      if (score >= 50) return { letter: "D", color: "text-orange-700 bg-orange-50 border-orange-200" };
      return { letter: "E", color: "text-rose-700 bg-rose-50 border-rose-200" };
    }

    // --- STREAMING_CHUNK:Event Handlers Interaksi... ---
    function setGradingScheme(scheme) {
      activeScheme = scheme;
      const btn1 = document.getElementById('btn-scheme-1');
      const btn2 = document.getElementById('btn-scheme-2');
      const els = {
        utsInputs: document.getElementById('container-input-uts'),
        utsWeights: document.getElementById('container-weight-uts'),
        infoBadgeUts: document.getElementById('info-badge-uts'),
        headerColUts: document.getElementById('header-col-uts'),
        gridContainer: document.getElementById('weight-grid-container'),
        formGrid: document.getElementById('form-grid-container')
      };

      const activeBtnClass = "flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 bg-white text-indigo-700 shadow-sm border border-slate-200/50";
      const inactiveBtnClass = "flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 text-slate-500 hover:text-slate-800";

      if (scheme === 'scheme1') {
        btn1.className = activeBtnClass; btn2.className = inactiveBtnClass;
        els.utsInputs.classList.add('hidden'); els.utsWeights.classList.add('hidden');
        els.infoBadgeUts.classList.add('hidden'); els.infoBadgeUts.classList.remove('flex');
        els.headerColUts.classList.add('hidden');
        els.gridContainer.classList.replace('grid-cols-4', 'grid-cols-3');
        els.formGrid.classList.replace('grid-cols-2', 'grid-cols-2'); // keep 2 cols layout
        weights = { harian: 40, uts: 0, uas: 40, kehadiran: 20 };
      } else {
        btn2.className = activeBtnClass; btn1.className = inactiveBtnClass;
        els.utsInputs.classList.remove('hidden'); els.utsWeights.classList.remove('hidden');
        els.infoBadgeUts.classList.remove('hidden'); els.infoBadgeUts.classList.add('flex');
        els.headerColUts.classList.remove('hidden');
        els.gridContainer.classList.replace('grid-cols-3', 'grid-cols-4');
        weights = { harian: 20, uts: 30, uas: 30, kehadiran: 20 };
      }
      
      syncInputsWithState(); handleWeightUpdate(); renderApp();
    }

    function setAttendanceMode(mode) {
      attendanceMode = mode;
      const btnDirect = document.getElementById('btn-mode-direct');
      const btnMeetings = document.getElementById('btn-mode-meetings');
      const activeBtnClass = "flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 bg-white text-indigo-700 shadow-sm border border-slate-200/50";
      const inactiveBtnClass = "flex-1 py-2 px-2 text-xs font-bold rounded-lg transition-all duration-200 text-slate-500 hover:text-slate-800";
      
      const attendanceInput = document.getElementById('grade-kehadiran');

      if (mode === 'direct') {
        btnDirect.className = activeBtnClass; btnMeetings.className = inactiveBtnClass;
        document.getElementById('container-total-meetings').classList.add('hidden');
        document.getElementById('label-attendance-input').innerText = "Absen (0-100)";
        attendanceInput.placeholder = "0-100"; attendanceInput.max = 100;
      } else {
        btnMeetings.className = activeBtnClass; btnDirect.className = inactiveBtnClass;
        document.getElementById('container-total-meetings').classList.remove('hidden');
        document.getElementById('label-attendance-input').innerText = `Absen (Max ${totalMeetings})`;
        attendanceInput.placeholder = `0-${totalMeetings}`; attendanceInput.max = totalMeetings;
      }
      renderApp();
    }

    function handleTotalMeetingsChange(value) {
      totalMeetings = parseInt(value) || 20;
      if (attendanceMode === 'meetings') {
        document.getElementById('label-attendance-input').innerText = `Absen (Max ${totalMeetings})`;
        document.getElementById('grade-kehadiran').max = totalMeetings;
        document.getElementById('grade-kehadiran').placeholder = `0-${totalMeetings}`;
      }
      renderApp();
    }

    function updateWeightTexts() {
      document.getElementById('info-weight-harian').innerText = weights.harian;
      document.getElementById('info-weight-uts').innerText = weights.uts;
      document.getElementById('info-weight-uas').innerText = weights.uas;
      document.getElementById('info-weight-kehadiran').innerText = weights.kehadiran;
    }

    function handleWeightUpdate() {
      weights.harian = parseInt(document.getElementById('weight-harian').value) || 0;
      weights.uts = parseInt(document.getElementById('weight-uts').value) || 0;
      weights.uas = parseInt(document.getElementById('weight-uas').value) || 0;
      weights.kehadiran = parseInt(document.getElementById('weight-kehadiran').value) || 0;

      if (activeScheme === 'scheme1') weights.uts = 0;

      const sum = weights.harian + weights.uts + weights.uas + weights.kehadiran;
      const badge = document.getElementById('weight-sum-badge');
      const warningBanner = document.getElementById('weight-warning-banner');

      badge.innerText = `Total: ${sum}%`;

      if (sum === 100) {
        badge.className = "px-2.5 py-1 rounded-lg text-xs font-bold bg-indigo-50 text-indigo-700 border border-indigo-100";
        warningBanner.classList.add('hidden');
      } else {
        badge.className = "px-2.5 py-1 rounded-lg text-xs font-bold bg-rose-50 text-rose-700 border border-rose-100";
        warningBanner.classList.remove('hidden');
      }

      updateWeightTexts(); renderApp();
    }

    // --- STREAMING_CHUNK:Render Tabel dan Rekap Data... ---
    function renderApp() {
      const tbody = document.getElementById('students-table-body');
      tbody.innerHTML = '';

      document.getElementById('header-kehadiran-col').innerText = attendanceMode === 'meetings' ? `Absen (H)` : `Absen (%)`;

      if (students.length === 0) {
        document.getElementById('empty-state').classList.remove('hidden');
        document.getElementById('empty-state').classList.add('flex');
      } else {
        document.getElementById('empty-state').classList.add('hidden');
        document.getElementById('empty-state').classList.remove('flex');

        students.forEach((student, idx) => {
          const finalVal = calculateSingleGradeValue(student);
          const gradeInfo = getGradeLetterInfo(finalVal);
          
          const inputClass = "w-full text-center bg-transparent hover:bg-slate-100 focus:bg-white focus:ring-2 focus:ring-indigo-400 focus:outline-none px-1.5 py-1.5 rounded-lg font-bold text-slate-700 transition-colors border border-transparent hover:border-slate-200";

          const utsCell = activeScheme === 'scheme2' ? `
            <td class="px-2 py-3 text-center">
              <input type="number" min="0" max="100" value="${student.uts}" onchange="handleInlineUpdate('${student.id}', 'uts', this.value)" class="${inputClass} text-indigo-700" />
            </td>` : '';

          const tr = document.createElement('tr');
          tr.className = "hover:bg-slate-50/50 transition-colors group";
          tr.innerHTML = `
            <td class="px-5 py-3 text-center font-bold text-slate-400">${idx + 1}</td>
            <td class="px-4 py-3">
              <input type="text" value="${student.name}" onchange="handleInlineUpdate('${student.id}', 'name', this.value)" class="w-full bg-transparent font-bold text-slate-800 hover:bg-slate-100 focus:bg-white focus:ring-2 focus:ring-indigo-400 focus:outline-none px-2 py-1.5 rounded-lg transition-colors border border-transparent hover:border-slate-200" />
            </td>
            <td class="px-2 py-3 text-center">
              <input type="number" min="0" max="100" value="${student.harian}" onchange="handleInlineUpdate('${student.id}', 'harian', this.value)" class="${inputClass}" />
            </td>
            ${utsCell}
            <td class="px-2 py-3 text-center">
              <input type="number" min="0" max="100" value="${student.uas}" onchange="handleInlineUpdate('${student.id}', 'uas', this.value)" class="${inputClass}" />
            </td>
            <td class="px-2 py-3 text-center relative">
              <input type="number" min="0" max="${attendanceMode === 'meetings' ? totalMeetings : 100}" value="${student.kehadiran}" onchange="handleInlineUpdate('${student.id}', 'kehadiran', this.value)" class="${inputClass}" />
              ${attendanceMode === 'meetings' ? `<span class="absolute -bottom-1 left-1/2 -translate-x-1/2 text-[9px] text-slate-400 font-bold opacity-0 group-hover:opacity-100 transition-opacity">${getKehadiranScore(student.kehadiran)}%</span>` : ''}
            </td>
            <td class="px-4 py-3 text-center bg-indigo-50/20">
              <span class="text-[15px] font-black text-indigo-900">${isWeightValid() ? finalVal : '-'}</span>
            </td>
            <td class="px-4 py-3 text-center">
              <span class="inline-flex px-3 py-1 rounded-full text-[11px] font-bold border ${gradeInfo.color}">${isWeightValid() ? gradeInfo.letter : '-'}</span>
            </td>
            <td class="px-4 py-3 text-right no-print">
              <button onclick="triggerConfirmDialog('Hapus data santri ${student.name}?', () => handleDeleteStudent('${student.id}', '${student.name}'))" class="p-2 text-rose-400 hover:text-rose-600 hover:bg-rose-50 rounded-xl transition-all" title="Hapus">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" /></svg>
              </button>
            </td>
          `;
          tbody.appendChild(tr);
        });
      }
      updateStatistics();
    }

    function updateStatistics() {
      const total = students.length;
      let sum = 0, highest = 0;
      if (isWeightValid() && total > 0) {
        students.forEach(st => {
          const score = calculateSingleGradeValue(st);
          sum += score;
          if (score > highest) highest = score;
        });
      }
      document.getElementById('stat-average').innerText = (isWeightValid() && total > 0) ? (sum / total).toFixed(1) : "0.0";
      document.getElementById('stat-highest').innerText = highest.toFixed(1);
      document.getElementById('stat-total').innerText = total;
    }

    // --- STREAMING_CHUNK:Sistem CRUD dan Modals... ---
    function handleAddStudent(e) {
      e.preventDefault();
      const name = document.getElementById('student-name').value.trim();
      const harian = parseFloat(document.getElementById('grade-harian').value) || 0;
      const uts = parseFloat(document.getElementById('grade-uts').value) || 0;
      const uas = parseFloat(document.getElementById('grade-uas').value) || 0;
      const kehadiran = parseFloat(document.getElementById('grade-kehadiran').value) || 0;

      if (!name) return showToast("Nama tidak valid", "Gagal menambahkan karena nama kosong.", "error");
      if (attendanceMode === 'meetings' && kehadiran > totalMeetings) {
        return showToast("Batas Hadir", `Kehadiran melampaui max (${totalMeetings}).`, "error");
      }

      students.push({ id: String(Date.now()), name, harian, uts, uas, kehadiran });
      showToast("Berhasil", `Data ${name} ditambahkan.`);
      document.getElementById('add-student-form').reset();
      renderApp();
    }

    function handleInlineUpdate(id, field, value) {
      students = students.map(student => {
        if (student.id === id) {
          if (field === 'name') return { ...student, name: value.trim() };
          let numVal = parseFloat(value) || 0;
          if (field === 'kehadiran' && attendanceMode === 'meetings') numVal = Math.min(totalMeetings, numVal);
          return { ...student, [field]: numVal };
        }
        return student;
      });
      renderApp();
    }

    function handleDeleteStudent(id, name) {
      students = students.filter(student => student.id !== id);
      showToast("Dihapus", `Data ${name} dihapus.`);
      renderApp();
    }

    function clearAllData() {
      students = [];
      showToast("Dikosongkan", "Seluruh data dihapus permanen.");
      closeConfirmModal();
      renderApp();
    }

    // Modal & UI Utils
    function animateModalOpen(modalId, contentId) {
      const modal = document.getElementById(modalId);
      const content = document.getElementById(contentId);
      modal.classList.remove('hidden');
      setTimeout(() => {
        content.classList.remove('scale-95', 'opacity-0');
        content.classList.add('scale-100', 'opacity-100');
      }, 10);
    }

    function animateModalClose(modalId, contentId) {
      const modal = document.getElementById(modalId);
      const content = document.getElementById(contentId);
      content.classList.remove('scale-100', 'opacity-100');
      content.classList.add('scale-95', 'opacity-0');
      setTimeout(() => modal.classList.add('hidden'), 300);
    }

    function triggerConfirmDialog(text, callback) {
      document.getElementById('confirm-modal-text').innerText = text;
      animateModalOpen('confirm-modal', 'confirm-modal-content');
      activeConfirmCallback = callback;
      document.getElementById('btn-confirm-action').onclick = function() {
        if (activeConfirmCallback) activeConfirmCallback();
      };
    }
    function closeConfirmModal() { animateModalClose('confirm-modal', 'confirm-modal-content'); activeConfirmCallback = null; }

    function openBulkModal() {
      animateModalOpen('bulk-modal', 'bulk-modal-content');
      const helper = document.getElementById('bulk-format-helper');
      if (activeScheme === 'scheme2') helper.innerHTML = `Format: <strong>Nama - Harian - UTS - UAS - Absen</strong><br/>Contoh: Raihan - 85 - 80 - 90 - 20`;
      else helper.innerHTML = `Format: <strong>Nama - Harian - UAS - Absen</strong><br/>Contoh: Siti - 90 - 85 - 18`;
    }
    function closeBulkModal() { animateModalClose('bulk-modal', 'bulk-modal-content'); document.getElementById('bulk-input-text').value = ''; }

    function openExportModal() { animateModalOpen('export-modal', 'export-modal-content'); }
    function closeExportModal() { animateModalClose('export-modal', 'export-modal-content'); }

    function showToast(title, message, type = 'success') {
      const toast = document.getElementById('notification-toast');
      document.getElementById('notification-title').innerText = title;
      document.getElementById('notification-text').innerText = message;
      
      const iconContainer = document.getElementById('toast-icon-container');
      if (type === 'error') {
        toast.className = `fixed bottom-8 right-8 z-50 flex items-start space-x-3 px-5 py-4 rounded-2xl shadow-2xl bg-white border-l-4 border-l-rose-500 border-y border-r border-slate-100 transition-all duration-300 transform max-w-sm w-full`;
        iconContainer.innerHTML = `<div class="bg-rose-100 text-rose-600 rounded-full p-1"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg></div>`;
      } else {
        toast.className = `fixed bottom-8 right-8 z-50 flex items-start space-x-3 px-5 py-4 rounded-2xl shadow-2xl bg-white border-l-4 border-l-indigo-500 border-y border-r border-slate-100 transition-all duration-300 transform max-w-sm w-full`;
        iconContainer.innerHTML = `<div class="bg-indigo-100 text-indigo-600 rounded-full p-1"><svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/></svg></div>`;
      }
      
      toast.classList.remove('hidden', 'translate-y-10', 'opacity-0');
      
      setTimeout(() => {
        toast.classList.add('translate-y-10', 'opacity-0');
        setTimeout(() => toast.classList.add('hidden'), 300);
      }, 3500);
    }

    // --- STREAMING_CHUNK:Logika Ekspor / Impor Spesifik... ---
    function handleBulkTextParse() {
      const text = document.getElementById('bulk-input-text').value;
      if (!text.trim()) return showToast("Kosong", "Tidak ada teks yang dimasukkan.", "error");

      const lines = text.split('\n');
      const parsed = [];

      lines.forEach((line, idx) => {
        if (!line.trim()) return;
        const parts = line.split(/[-]/).map(p => p.trim());
        
        if (parts.length >= 4 && activeScheme === 'scheme1') {
          let kehadiran = parseFloat(parts[3]) || 0;
          if (attendanceMode === 'meetings') kehadiran = Math.min(totalMeetings, kehadiran); else kehadiran = Math.min(100, kehadiran);
          parsed.push({ id: String(Date.now() + idx), name: parts[0], harian: parseFloat(parts[1]) || 0, uts: 0, uas: parseFloat(parts[2]) || 0, kehadiran });
        } else if (parts.length >= 5 && activeScheme === 'scheme2') {
          let kehadiran = parseFloat(parts[4]) || 0;
          if (attendanceMode === 'meetings') kehadiran = Math.min(totalMeetings, kehadiran); else kehadiran = Math.min(100, kehadiran);
          parsed.push({ id: String(Date.now() + idx), name: parts[0], harian: parseFloat(parts[1]) || 0, uts: parseFloat(parts[2]) || 0, uas: parseFloat(parts[3]) || 0, kehadiran });
        }
      });

      if (parsed.length > 0) {
        students = [...students, ...parsed];
        showToast("Impor Berhasil", `${parsed.length} data ditambahkan.`);
        closeBulkModal(); renderApp();
      } else { showToast("Format Salah", "Format teks tidak sesuai skema.", "error"); }
    }

    function copyWhatsAppReport() {
      if (students.length === 0) return showToast("Kosong", "Tidak ada data.", "error");
      if (!isWeightValid()) return showToast("Gagal", "Bobot tidak valid.", "error");

      let report = `📋 *LAPORAN NILAI MDTA*\n========================\n`;
      students.forEach((st, idx) => {
        const final = calculateSingleGradeValue(st);
        const letter = getGradeLetterInfo(final).letter;
        let attText = attendanceMode === 'meetings' ? `${st.kehadiran}/${totalMeetings}` : `${st.kehadiran}%`;
        report += `${idx+1}. *${st.name}* | NA: *${final}* (${letter})\n`;
      });

      const temp = document.createElement('textarea'); temp.value = report; document.body.appendChild(temp); temp.select(); document.execCommand('copy'); document.body.removeChild(temp);
      closeExportModal(); showToast("Disalin!", "Siap ditempel di WhatsApp.");
    }

    function downloadCSV() {
      if (students.length === 0) return showToast("Kosong", "Tidak ada data.", "error");
      let csv = "data:text/csv;charset=utf-8,";
      csv += activeScheme === 'scheme2' ? "No,Nama,Harian,UTS,UAS,Absen,Akhir,Predikat\n" : "No,Nama,Harian,UAS,Absen,Akhir,Predikat\n";

      students.forEach((st, idx) => {
        const final = isWeightValid() ? calculateSingleGradeValue(st) : "Invalid";
        const grade = isWeightValid() ? getGradeLetterInfo(final).letter : "-";
        const row = activeScheme === 'scheme2' ? [idx+1, `"${st.name}"`, st.harian, st.uts, st.uas, st.kehadiran, final, grade] : [idx+1, `"${st.name}"`, st.harian, st.uas, st.kehadiran, final, grade];
        csv += row.join(",") + "\n";
      });

      const link = document.createElement("a"); link.setAttribute("href", encodeURI(csv)); link.setAttribute("download", "Laporan_Nilai.csv"); document.body.appendChild(link); link.click(); document.body.removeChild(link);
      closeExportModal(); showToast("Diunduh", "File CSV berhasil disimpan.");
    }

    function executePrint() { closeExportModal(); setTimeout(() => window.print(), 300); }
  </script>
</body>
</html>
