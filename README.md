<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FitWellness Pro - تطبيق الصحة والرياضة الشامل</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        * { font-family: 'Tajawal', sans-serif; }
        .bg-relax { background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%); }
        .glass-card { background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(10px); border: 1px solid rgba(255, 255, 255, 0.1); }
        .tab-btn.active { background-color: #14b8a6; color: white; }
    </style>
</head>
<body class="bg-relax text-slate-100 min-h-screen flex flex-col justify-between">

    <!-- Top Header -->
    <header class="p-4 border-b border-slate-700 flex justify-between items-center glass-card sticky top-0 z-50">
        <div class="flex items-center gap-2">
            <i class="fa-solid fa-heart-pulse text-teal-400 text-2xl"></i>
            <h1 class="font-bold text-xl text-teal-300" id="app-title">FitWellness Pro</h1>
        </div>
        <!-- Language Selector -->
        <select id="langSelect" onchange="changeLanguage(this.value)" class="bg-slate-800 text-teal-300 text-sm border border-teal-500/30 rounded-lg px-2 py-1 outline-none">
            <option value="ar">العربية 🇩🇿</option>
            <option value="en">English 🇺🇸</option>
            <option value="fr">Français 🇫🇷</option>
            <option value="ru">Русский 🇷🇺</option>
        </select>
    </header>

    <!-- Top Ad Banner Placeholder -->
    <div class="container mx-auto px-4 my-3">
        <div class="bg-slate-800/60 border border-teal-500/20 rounded-lg p-2 text-center text-xs text-slate-400">
            <i class="fa-solid fa-rectangle-ad mr-1"></i> <span id="ad-top-text">مساحة إعلانية (Google AdSense)</span>
        </div>
    </div>

    <!-- Main Content Container -->
    <main class="container mx-auto px-4 py-2 flex-grow">
        
        <!-- Navigation Tabs -->
        <div class="flex overflow-x-auto gap-2 mb-6 pb-2 no-scrollbar text-sm font-medium">
            <button onclick="switchTab('exercises')" id="tab-exercises" class="tab-btn active px-4 py-2 rounded-xl border border-teal-500/30 flex items-center gap-2 whitespace-nowrap transition-all">
                <i class="fa-solid fa-dumbbell"></i> <span data-key="nav_exercises">التمارين</span>
            </button>
            <button onclick="switchTab('diseases')" id="tab-diseases" class="tab-btn px-4 py-2 rounded-xl border border-teal-500/30 flex items-center gap-2 whitespace-nowrap transition-all">
                <i class="fa-solid fa-stethoscope"></i> <span data-key="nav_diseases">دليل الأمراض</span>
            </button>
            <button onclick="switchTab('nutrition')" id="tab-nutrition" class="tab-btn px-4 py-2 rounded-xl border border-teal-500/30 flex items-center gap-2 whitespace-nowrap transition-all">
                <i class="fa-solid fa-apple-whole"></i> <span data-key="nav_nutrition">التغذية</span>
            </button>
            <button onclick="switchTab('timers')" id="tab-timers" class="tab-btn px-4 py-2 rounded-xl border border-teal-500/30 flex items-center gap-2 whitespace-nowrap transition-all">
                <i class="fa-solid fa-stopwatch"></i> <span data-key="nav_timers">المشي والراحة</span>
            </button>
        </div>

        <!-- Section 1: Exercises -->
        <section id="sec-exercises" class="space-y-4">
            <h2 class="text-lg font-bold text-teal-300 flex items-center gap-2">
                <i class="fa-solid fa-house"></i> <span data-key="ex_title">تمارين منزلية بدون معدات</span>
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div class="glass-card p-4 rounded-2xl border-l-4 border-l-teal-400">
                    <h3 class="font-bold text-teal-200" data-key="ex_pushups_title">تمرين الضغط (Push-ups)</h3>
                    <p class="text-sm text-slate-300 mt-1" data-key="ex_pushups_desc">يقوي عضلات الصدر والكتفين والترايسبس. 3 مجموعات × 12 تكرار.</p>
                </div>
                <div class="glass-card p-4 rounded-2xl border-l-4 border-l-teal-400">
                    <h3 class="font-bold text-teal-200" data-key="ex_squats_title">تمرين السكوات (Squats)</h3>
                    <p class="text-sm text-slate-300 mt-1" data-key="ex_squats_desc">لتقوية عضلات الفخذين والأرداف. 3 مجموعات × 15 تكرار.</p>
                </div>
                <div class="glass-card p-4 rounded-2xl border-l-4 border-l-teal-400">
                    <h3 class="font-bold text-teal-200" data-key="ex_plank_title">تمرين الثبات (Plank)</h3>
                    <p class="text-sm text-slate-300 mt-1" data-key="ex_plank_desc">لتقوية عضلات البطن والجذع. الثبات لمدة 45 ثانية × 3 مرات.</p>
                </div>
            </div>
        </section>

        <!-- Section 2: Medical & Diseases Guide -->
        <section id="sec-diseases" class="space-y-4 hidden">
            <h2 class="text-lg font-bold text-teal-300 flex items-center gap-2">
                <i class="fa-solid fa-book-medical"></i> <span data-key="dis_title">دليل الأعراض والأمراض الشائعة</span>
            </h2>
            <div class="glass-card p-3 rounded-xl flex items-center gap-2">
                <i class="fa-solid fa-magnifying-glass text-teal-400"></i>
                <input type="text" id="diseaseSearch" onkeyup="filterDiseases()" placeholder="ابحث عن مرض أو عرض..." class="bg-transparent w-full outline-none text-sm text-slate-100">
            </div>
            <div id="diseasesList" class="space-y-3">
                <div class="glass-card p-4 rounded-2xl border-r-4 border-r-amber-400 disease-item">
                    <h3 class="font-bold text-amber-300" data-key="dis_flu_title">الإنفلونزا الموسمية</h3>
                    <p class="text-sm text-slate-300 mt-1"><b>الأعراض:</b> ارتفاع الحرارة، السعال، إرهاق عام، ألم العضلات.</p>
                    <p class="text-xs text-teal-300 mt-2"><b>الراحة والتعافي:</b> شرب السوائل الدافئة والراحة التامة.</p>
                </div>
                <div class="glass-card p-4 rounded-2xl border-r-4 border-r-amber-400 disease-item">
                    <h3 class="font-bold text-amber-300" data-key="dis_dehyd_title">الجفاف وإجهاد التمرين</h3>
                    <p class="text-sm text-slate-300 mt-1"><b>الأعراض:</b> الصداع، جفاف الفم، التقلصات العضلية، الدوار.</p>
                    <p class="text-xs text-teal-300 mt-2"><b>الراحة والتعافي:</b> شرب الماء مع المعادن وتعويض الأملاح فوراً.</p>
                </div>
            </div>
        </section>

        <!-- Section 3: Nutrition -->
        <section id="sec-nutrition" class="space-y-4 hidden">
            <h2 class="text-lg font-bold text-teal-300 flex items-center gap-2">
                <i class="fa-solid fa-utensils"></i> <span data-key="nut_title">نصائح التغذية الأسبوعية</span>
            </h2>
            <div class="glass-card p-4 rounded-2xl space-y-3">
                <div class="flex items-start gap-3">
                    <i class="fa-solid fa-check-circle text-emerald-400 text-lg mt-1"></i>
                    <div>
                        <h4 class="font-bold text-slate-200" data-key="nut_tip1_title">البروتين لبناء العضلات</h4>
                        <p class="text-sm text-slate-300" data-key="nut_tip1_desc">تناول البيض، الدجاج، أو الأسماك بعد التمرين بـ 30 دقيقة لإعادة بناء العضلات.</p>
                    </div>
                </div>
                <hr class="border-slate-700">
                <div class="flex items-start gap-3">
                    <i class="fa-solid fa-check-circle text-emerald-400 text-lg mt-1"></i>
                    <div>
                        <h4 class="font-bold text-slate-200" data-key="nut_tip2_title">شرب الماء المنتظم</h4>
                        <p class="text-sm text-slate-300" data-key="nut_tip2_desc">اشرب على الأقل 2.5 إلى 3 لترات ماء يومياً لتعزيز الأيض والنشاط البدني.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Section 4: Timers & Rest -->
        <section id="sec-timers" class="space-y-4 hidden">
            <h2 class="text-lg font-bold text-teal-300 flex items-center gap-2">
                <i class="fa-solid fa-clock"></i> <span data-key="timer_title">منظم وقت المشي والاسترخاء</span>
            </h2>
            <div class="glass-card p-6 rounded-2xl text-center space-y-4">
                <div class="text-4xl font-bold font-mono text-teal-300" id="timerDisplay">20:00</div>
                <p class="text-sm text-slate-400" id="timerModeText">وقت المشي السريع</p>
                <div class="flex justify-center gap-3">
                    <button onclick="startTimer()" class="bg-teal-500 hover:bg-teal-600 px-6 py-2 rounded-xl font-bold transition-all"><i class="fa-solid fa-play"></i> ابدأ</button>
                    <button onclick="pauseTimer()" class="bg-slate-700 hover:bg-slate-600 px-6 py-2 rounded-xl font-bold transition-all"><i class="fa-solid fa-pause"></i> إيقاف</button>
                    <button onclick="resetTimer()" class="bg-rose-500/30 hover:bg-rose-500/50 text-rose-200 px-4 py-2 rounded-xl transition-all"><i class="fa-solid fa-rotate-left"></i></button>
                </div>
            </div>
        </section>

    </main>

    <!-- Bottom Ad Banner Placeholder -->
    <div class="container mx-auto px-4 my-2">
        <div class="bg-slate-800/60 border border-teal-500/20 rounded-lg p-2 text-center text-xs text-slate-400">
            <i class="fa-solid fa-rectangle-ad mr-1"></i> <span id="ad-bottom-text">مساحة إعلانية سفلية (Google AdSense)<...
