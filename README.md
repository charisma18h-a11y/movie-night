
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ملتقى الأفلام - النادي الإعلامي | MTU</title>
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;800;900&family=Tajawal:wght@400;700;900&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-dark: #080203;
            --bg-deep-red: #1a0306;
            --bg-card: rgba(26, 6, 10, 0.85);
            --bg-card-hover: rgba(45, 10, 16, 0.95);
            
            --primary-red: #8b0000;
            --crimson-glow: #dc2626;
            --crimson-bright: #ef4444;
            --accent-gold: #fbbf24;
            --accent-gold-hover: #f59e0b;
            
            --text-main: #ffffff;
            --text-muted: #d1d5db;
            --text-dim: #9ca3af;
            
            --border-red: rgba(220, 38, 38, 0.35);
            --border-gold: rgba(251, 191, 36, 0.4);
            
            --shadow-glow: 0 0 25px rgba(220, 38, 38, 0.3);
            --gold-glow: 0 0 20px rgba(251, 191, 36, 0.25);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', 'Tajawal', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-dark);
            background-image: 
                radial-gradient(circle at 50% 10%, rgba(139, 0, 0, 0.45) 0%, rgba(8, 2, 3, 0.98) 75%),
                radial-gradient(circle at 10% 50%, rgba(180, 20, 30, 0.2) 0%, transparent 60%),
                radial-gradient(circle at 90% 80%, rgba(120, 10, 20, 0.2) 0%, transparent 60%);
            background-attachment: fixed;
            color: var(--text-main);
            line-height: 1.8;
            padding-bottom: 60px;
            overflow-x: hidden;
            position: relative;
        }

        /* Vertical Side Film Strips */
        .film-strip-side {
            position: fixed;
            top: 0;
            bottom: 0;
            width: 32px;
            background-color: #000000;
            border-left: 2px solid #2a0000;
            border-right: 2px solid #2a0000;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            align-items: center;
            z-index: 5;
            opacity: 0.5;
            pointer-events: none;
        }

        .film-strip-left { left: 0; }
        .film-strip-right { right: 0; }

        .film-hole {
            width: 16px;
            height: 12px;
            background-color: var(--bg-dark);
            border-radius: 3px;
            border: 1px solid rgba(220, 38, 38, 0.3);
            margin: 6px 0;
            box-shadow: inset 0 0 4px #000;
        }

        /* Welcome Splash Modal Overlay */
        .intro-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(135deg, rgba(15, 2, 4, 0.98) 0%, rgba(5, 0, 1, 0.99) 100%);
            z-index: 9999;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
            transition: opacity 0.8s ease, visibility 0.8s ease;
        }

        .intro-overlay.hidden {
            opacity: 0;
            visibility: hidden;
            pointer-events: none;
        }

        .intro-card {
            background: linear-gradient(180deg, rgba(40, 5, 10, 0.9) 0%, rgba(15, 2, 4, 0.95) 100%);
            border: 2px solid var(--border-gold);
            border-radius: 24px;
            padding: 45px 35px;
            max-width: 650px;
            width: 100%;
            text-align: center;
            box-shadow: 0 0 50px rgba(220, 38, 38, 0.4), inset 0 0 20px rgba(251, 191, 36, 0.1);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(15px);
            animation: modalPop 0.8s ease-out;
        }

        @keyframes modalPop {
            0% { transform: scale(0.85); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        /* Top & Bottom Film Borders inside Card */
        .card-film-header {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 18px;
            background: #000;
            display: flex;
            justify-content: space-around;
            align-items: center;
            border-bottom: 1px solid var(--border-red);
        }

        .card-film-header .mini-hole {
            width: 10px;
            height: 8px;
            background: var(--bg-dark);
            border-radius: 2px;
        }

        /* Logo Component */
        .logo-container {
            display: inline-flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            margin-top: 15px;
            margin-bottom: 15px;
            position: relative;
        }

        .mtu-badge {
            width: 110px;
            height: 110px;
            background: linear-gradient(135deg, #2b060a 0%, #0d0103 100%);
            border: 2px solid var(--accent-gold);
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            box-shadow: var(--gold-glow), var(--shadow-glow);
            position: relative;
            transition: transform 0.4s ease;
        }

        .mtu-badge:hover {
            transform: scale(1.06);
        }

        .mtu-badge .logo-text {
            font-size: 2.2rem;
            font-weight: 900;
            letter-spacing: 2px;
            background: linear-gradient(135deg, #fff 20%, var(--accent-gold) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1;
        }

        .mtu-badge .logo-subtext {
            font-size: 0.65rem;
            color: var(--accent-gold);
            letter-spacing: 3px;
            font-weight: 700;
            margin-top: 2px;
        }

        .mtu-badge-ring {
            position: absolute;
            width: 124px;
            height: 124px;
            border: 1px dashed rgba(251, 191, 36, 0.5);
            border-radius: 50%;
            animation: spinRing 20s linear infinite;
        }

        @keyframes spinRing {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .club-tag {
            color: var(--accent-gold);
            font-size: 1.15rem;
            font-weight: 800;
            letter-spacing: 1px;
            margin-top: 6px;
            display: inline-block;
            background: rgba(251, 191, 36, 0.12);
            padding: 4px 18px;
            border-radius: 20px;
            border: 1px solid var(--border-gold);
        }

        .intro-title {
            font-size: 2.8rem;
            font-weight: 900;
            color: #ffffff;
            margin: 15px 0 10px;
            text-shadow: 0 0 20px rgba(220, 38, 38, 0.8);
        }

        .intro-welcome-msg {
            color: var(--text-muted);
            font-size: 1.08rem;
            line-height: 1.8;
            margin-bottom: 28px;
        }

        /* Enter Button CTA */
        .btn-enter {
            background: linear-gradient(135deg, var(--accent-gold) 0%, #d97706 100%);
            color: #0d0103;
            font-size: 1.25rem;
            font-weight: 800;
            padding: 14px 42px;
            border: none;
            border-radius: 40px;
            cursor: pointer;
            box-shadow: 0 0 25px rgba(251, 191, 36, 0.4), 0 5px 15px rgba(0,0,0,0.5);
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 12px;
        }

        .btn-enter:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 0 35px rgba(251, 191, 36, 0.7), 0 8px 20px rgba(0,0,0,0.6);
            background: linear-gradient(135deg, #fef08a 0%, var(--accent-gold) 100%);
        }

        /* Ambient Top Glow Line */
        .ambient-light {
            position: fixed;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            max-width: 1200px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--crimson-glow), var(--accent-gold), var(--crimson-glow), transparent);
            box-shadow: 0 0 15px var(--crimson-glow);
            z-index: 100;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 24px;
            position: relative;
            z-index: 2;
        }

        /* Header Section */
        header {
            text-align: center;
            padding: 45px 20px 30px;
            position: relative;
        }

        .header-title-badge {
            background: rgba(139, 0, 0, 0.35);
            color: var(--accent-gold);
            padding: 8px 22px;
            border-radius: 30px;
            font-size: 0.95rem;
            font-weight: 700;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 18px;
            border: 1px solid var(--border-gold);
            backdrop-filter: blur(8px);
        }

        h1.main-title {
            font-size: 3rem;
            font-weight: 900;
            margin-bottom: 8px;
            color: #ffffff;
            text-shadow: 0 0 20px rgba(220, 38, 38, 0.7);
        }

        p.subtitle {
            color: var(--text-muted);
            font-size: 1.15rem;
            max-width: 650px;
            margin: 0 auto;
        }

        /* Cards & Film Strip Effect Sections */
        section {
            margin-bottom: 50px;
        }

        .section-title {
            font-size: 1.75rem;
            font-weight: 800;
            margin-bottom: 22px;
            display: flex;
            align-items: center;
            gap: 12px;
            color: #ffffff;
            position: relative;
            padding-right: 18px;
        }

        .section-title::before {
            content: '';
            position: absolute;
            right: 0;
            top: 15%;
            height: 70%;
            width: 5px;
            background: linear-gradient(180deg, var(--accent-gold), var(--crimson-glow));
            border-radius: 4px;
            box-shadow: 0 0 10px var(--crimson-glow);
        }

        .section-title i {
            color: var(--accent-gold);
        }

        .card {
            background: var(--bg-card);
            border: 1px solid var(--border-red);
            border-radius: 16px;
            padding: 26px;
            margin-bottom: 20px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(12px);
            transition: all 0.35s ease;
            position: relative;
        }

        .card:hover {
            background: var(--bg-card-hover);
            border-color: rgba(220, 38, 38, 0.6);
            transform: translateY(-4px);
            box-shadow: var(--shadow-glow);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 22px;
        }

        /* Workshop Cards */
        .workshop-card {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .card-top {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 15px;
        }

        .role-badge {
            background: rgba(220, 38, 38, 0.25);
            color: #fca5a5;
            padding: 4px 12px;
            border-radius: 8px;
            font-size: 0.85rem;
            font-weight: 700;
            border: 1px solid rgba(220, 38, 38, 0.4);
        }

        .workshop-icon {
            width: 42px;
            height: 42px;
            background: rgba(251, 191, 36, 0.12);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-gold);
            font-size: 1.2rem;
            border: 1px solid var(--border-gold);
        }

        .workshop-card h3 {
            color: #ffffff;
            margin-bottom: 10px;
            font-size: 1.25rem;
        }

        .workshop-card p {
            color: var(--text-muted);
            font-size: 0.96rem;
        }

        /* Agenda Timeline */
        .timeline {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .timeline-item {
            display: flex;
            align-items: flex-start;
            gap: 18px;
            background: var(--bg-card);
            padding: 18px 22px;
            border-radius: 14px;
            border: 1px solid var(--border-red);
            border-right: 4px solid var(--accent-gold);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .timeline-item:hover {
            transform: translateX(-5px);
            background: var(--bg-card-hover);
            box-shadow: 0 5px 20px rgba(0,0,0,0.6);
        }

        .time-badge {
            background: linear-gradient(135deg, var(--accent-gold) 0%, var(--accent-gold-hover) 100%);
            color: #1a0306;
            font-weight: 800;
            padding: 5px 14px;
            border-radius: 8px;
            font-size: 0.88rem;
            white-space: nowrap;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        /* Requirements List */
        ul.needs-list {
            list-style: none;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 16px;
        }

        ul.needs-list li {
            position: relative;
            padding: 16px 44px 16px 18px;
            background: rgba(30, 6, 12, 0.6);
            border: 1px solid var(--border-red);
            border-radius: 12px;
            color: var(--text-main);
            font-size: 1rem;
            display: flex;
            align-items: center;
        }

        ul.needs-list li i.check-icon {
            position: absolute;
            right: 16px;
            color: var(--accent-gold);
            font-size: 1.1rem;
        }

        /* Footer */
        footer {
            text-align: center;
            color: var(--text-dim);
            font-size: 0.95rem;
            padding-top: 35px;
            border-top: 1px solid var(--border-red);
            margin-top: 50px;
        }

        footer .credits {
            color: #ffffff;
            font-weight: 700;
        }

        @media (max-width: 768px) {
            .film-strip-side { display: none; }
            h1.main-title { font-size: 2.2rem; }
            .intro-title { font-size: 2.1rem; }
            .intro-card { padding: 30px 20px; }
            .timeline-item { flex-direction: column; gap: 10px; }
        }
    </style>
</head>
<body>

    <!-- Film Strips (Side Borders) -->
    <div class="film-strip-side film-strip-left">
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
    </div>
    <div class="film-strip-side film-strip-right">
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
        <div class="film-hole"></div><div class="film-hole"></div><div class="film-hole"></div>
    </div>

    <!-- 1. Intro Screen / Splash Modal Overlay -->
    <div class="intro-overlay" id="introOverlay">
        <div class="intro-card">
            <!-- Film perforation header inside card -->
            <div class="card-film-header">
                <div class="mini-hole"></div><div class="mini-hole"></div>
                <div class="mini-hole"></div><div class="mini-hole"></div>
                <div class="mini-hole"></div><div class="mini-hole"></div>
            </div>

            <!-- MTU Logo Badge -->
            <div class="logo-container">
                <div class="mtu-badge-ring"></div>
                <div class="mtu-badge">
                    <span class="logo-text">MTU</span>
                    <span class="logo-subtext">MEDIA</span>
                </div>
            </div>

            <div>
                <span class="club-tag"><i class="fa-solid fa-photo-film"></i> النادي الإعلامي</span>
            </div>

            <h2 class="intro-title">ملتقى الأفلام</h2>

            <p class="intro-welcome-msg">
            
            </p>

            <button class="btn-enter" onclick="enterSite()">
                <span>دخول الملتقى</span>
                <i class="fa-solid fa-clapperboard"></i>
            </button>
        </div>
    </div>

    <!-- Ambient Top Glow Line -->
    <div class="ambient-light"></div>

    <!-- Main Site Content -->
    <header>
        <!-- Top MTU Header Logo -->
        <div class="logo-container">
            <div class="mtu-badge-ring"></div>
            <div class="mtu-badge">
                <span class="logo-text">MTU</span>
                <span class="logo-subtext">MEDIA</span>
            </div>
            <span class="club-tag" style="margin-top: 10px;"><i class="fa-solid fa-photo-film"></i> النادي الإعلامي</span>
        </div>

        <br>

        <div class="header-title-badge">
            <i class="fa-solid fa-film"></i>
            <span>مقترح مشروع التقديم والخطابة</span>
        </div>

        <h1 class="main-title">ملتقى الأفلام</h1>
        <p class="subtitle">رؤية متكاملة لدمج الفن البصري بالمهارات الخطابية والإعلامية لطلاب الجامعة</p>
    </header>

    <div class="container">

        <!-- فكرة المشروع -->
        <section>
            <h2 class="section-title">
                <i class="fa-solid fa-lightbulb"></i>
                فكرة الملتقى والهدف
            </h2>
            <div class="card">
                <p style="font-size: 1.1rem; color: #e2e8f0; line-height: 1.9;">
                    ملتقى سينمائي وثقافي تنظيمي يُقام على مستوى الجامعة برعاية النادي الإعلامي. يهدف الملتقى إلى نقل التجربة الإعلامية من النظرية إلى التطبيق، عبر تقديم ورش عمل تفاعلية يقودها مسارات النادي (الإنتاج، التصوير، التسويق)، يتبعها عرض فيلم قصير هادف، وختام حواري تديره كوادر مسار التقديم والخطابة.
                </p>
            </div>
        </section>

        <!-- ورش العمل والمساهمين -->
        <section>
            <h2 class="section-title">
                <i class="fa-solid fa-masks-theater"></i>
                ورش العمل والمشاركون (حسب المسارات)
            </h2>
            <div class="grid">
                
                <div class="card workshop-card">
                    <div class="card-top">
                        <span class="role-badge">مسار التقديم والخطابة</span>
                        <div class="workshop-icon"><i class="fa-solid fa-microphone-lines"></i></div>
                    </div>
                    <h3>إدارة الحوار والربط</h3>
                    <p>الافتتاحية والترحيب، تقديم المتحدثين، وإدارة الجلسة الحوارية والنقدية مع الحضور بعد العرض.</p>
                </div>

                <div class="card workshop-card">
                    <div class="card-top">
                        <span class="role-badge">مسار الإنتاج</span>
                        <div class="workshop-icon"><i class="fa-solid fa-scroll"></i></div>
                    </div>
                    <h3>من الفكرة إلى السيناريو</h3>
                    <p>شرح كيفية التخطيط للفيلم القصير، إدارة فريق العمل، وتحويل الفكرة إلى سيناريو جاهز للتنفيذ.</p>
                </div>

                <div class="card workshop-card">
                    <div class="card-top">
                        <span class="role-badge">مسار التصوير والإضاءة</span>
                        <div class="workshop-icon"><i class="fa-solid fa-video"></i></div>
                    </div>
                    <h3>قراءة الكادر واللغة البصرية</h3>
                    <p>تطبيق عملي حقيقي على المسرح لشرح اختيار زوايا الكاميرا وتأثير الإضاءة في إيصال المشاعر.</p>
                </div>

                <div class="card workshop-card">
                    <div class="card-top">
                        <span class="role-badge">مسار التسويق والإعلام</span>
                        <div class="workshop-icon"><i class="fa-solid fa-bullhorn"></i></div>
                    </div>
                    <h3>صناعة الهوية وجذب الجمهور</h3>
                    <p>عرض استراتيجية تسويق الفيلم، تصميم الإعلانات التشويقية، وكتابة المحتوى الترويجي.</p>
                </div>

            </div>
        </section>

        <!-- أجندة الفعالية -->
        <section>
            <h2 class="section-title">
                <i class="fa-solid fa-clock"></i>
                التسلسل الزمني للفعالية (الأجندة)
            </h2>
            <div class="timeline">
                
                <div class="timeline-item">
                    <div class="time-badge"><i class="fa-regular fa-clock"></i> 10 دقائق</div>
                    <div><strong>الافتتاح والترحيب:</strong> مقدمة حماسية عن أهمية الإعلام والسينما يلقيها مسار التقديم.</div>
                </div>

                <div class="timeline-item">
                    <div class="time-badge"><i class="fa-regular fa-clock"></i> 30 دقيقة</div>
                    <div><strong>الورش التفاعلية:</strong> فقرات سريعة لكل مسار لشرح محاور العمل قبل المشاهدة.</div>
                </div>

                <div class="timeline-item">
                    <div class="time-badge"><i class="fa-regular fa-clock"></i> 20 دقيقة</div>
                    <div><strong>العرض الرئيسي:</strong> عرض الفيلم القصير المختار على الشاشة الكبرى.</div>
                </div>

                <div class="timeline-item">
                    <div class="time-badge"><i class="fa-regular fa-clock"></i> 15 دقيقة</div>
                    <div><strong>الجلسة الحوارية والختام:</strong> فتح باب النقاش مع الطلاب والضيوف وختام الفعالية.</div>
                </div>

            </div>
        </section>

        <!-- متطلبات الجامعة -->
        <section>
            <h2 class="section-title">
                <i class="fa-solid fa-list-check"></i>
                احتياجاتنا من الجامعة
            </h2>
            <div class="card">
                <ul class="needs-list">
                    <li><i class="fa-solid fa-circle-check check-icon"></i> حجز مسرح الجامعة الرئيسي أو قاعة مؤتمرات مجهزة.</li>
                    <li><i class="fa-solid fa-circle-check check-icon"></i> توفير شاشة عرض (Data Show) بنظام صوتي عالي الجودة.</li>
                    <li><i class="fa-solid fa-circle-check check-icon"></i> إضاءة مسرحية متناسقة للورش التطبيقية.</li>
                    <li><i class="fa-solid fa-circle-check check-icon"></i>    اركان جاهزة للورش .</li>
                    <li><i class="fa-solid fa-circle-check check-icon"></i> الموافقة على نشر البوستر الرسمي وتوجيه الدعوة لطلاب الجامعة عبر قنوات التواصل.</li>
                </ul>
            </div>
        </section>

        <!-- Footer -->
        <footer>
            <p>إعداد وتنسيق: <span class="credits">خالد الهلال</span> - النادي الإعلامي © 2026</p>
        </footer>

    </div>

    <script>
        function enterSite() {
            const overlay = document.getElementById('introOverlay');
            overlay.classList.add('hidden');
            // Smooth scroll to header
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }
    </script>
</body>
</html>
