<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ملتقى سينما الجامعة - النادي الإعلامي</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --accent: #f59e0b;
            --accent-hover: #d97706;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --border: #334155;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.8;
            padding-bottom: 60px;
        }

        header {
            background: linear-gradient(135deg, #1e1b4b, #0f172a);
            text-align: center;
            padding: 60px 20px;
            border-bottom: 2px solid var(--accent);
        }

        .badge {
            background-color: rgba(245, 158, 11, 0.15);
            color: var(--accent);
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 700;
            display: inline-block;
            margin-bottom: 15px;
            border: 1px solid var(--accent);
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 900;
            margin-bottom: 10px;
            color: #ffffff;
        }

        p.subtitle {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .container {
            max-width: 1000px;
            margin: 40px auto;
            padding: 0 20px;
        }

        section {
            margin-bottom: 50px;
        }

        .section-title {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--accent);
            border-right: 4px solid var(--accent);
            padding-right: 12px;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 24px;
            margin-bottom: 20px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.3);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .workshop-card h3 {
            color: var(--text-main);
            margin-bottom: 8px;
            font-size: 1.2rem;
        }

        .workshop-card .role {
            color: var(--accent);
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .timeline {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .timeline-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
            background: var(--card-bg);
            padding: 15px 20px;
            border-radius: 8px;
            border-right: 3px solid var(--accent);
        }

        .time {
            background: var(--accent);
            color: #000;
            font-weight: 700;
            padding: 2px 10px;
            border-radius: 6px;
            font-size: 0.85rem;
            white-space: nowrap;
        }

        ul.needs-list {
            list-style: none;
        }

        ul.needs-list li {
            position: relative;
            padding-right: 25px;
            margin-bottom: 12px;
            color: var(--text-main);
        }

        ul.needs-list li::before {
            content: "✓";
            position: absolute;
            right: 0;
            color: var(--accent);
            font-weight: bold;
        }

        footer {
            text-align: center;
            color: var(--text-muted);
            font-size: 0.9rem;
            padding-top: 30px;
            border-top: 1px solid var(--border);
        }
    </style>
</head>
<body>

    <header>
        <span class="badge">مقترح مشروع التقديم والخطابة - النادي الإعلامي</span>
        <h1>ملتقى سينما الجامعة</h1>
        <p class="subtitle">رؤية متكاملة لدمج الفن Bصري بالمهارات الخطابية والإعلامية لطلاب الجامعة</p>
    </header>

    <div class="container">

        <!-- فكرة المشروع -->
        <section>
            <h2 class="section-title">فكرة الملتقى والهدف</h2>
            <div class="card">
                <p>ملتقى سينمائي وثقافي تنظيمي يُقام على مستوى الجامعة برعاية النادي الإعلامي. يهدف الملتقى إلى نقل التجربة الإعلامية من النظرية إلى التطبيق، عبر تقديم ورش عمل تفاعلية يقودها مسارات النادي (الإنتاج، التصوير، التسويق)، يتبعها عرض فيلم قصير هادف، وختام حواري تديره كوادر مسار التقديم والخطابة.</p>
            </div>
        </section>

        <!-- ورش العمل والمساهمين -->
        <section>
            <h2 class="section-title">ورش العمل والمشاركين (حسب المسارات)</h2>
            <div class="grid">
                
                <div class="card workshop-card">
                    <span class="role">مسار التقديم والخطابة</span>
                    <h3>إدارة الحوار والربط</h3>
                    <p>الافتتاحية والترحيب، تقديم المتحدثين، وإدارة الجلسة الحوارية والنقدية مع الحضور بعد العرض.</p>
                </div>

                <div class="card workshop-card">
                    <span class="role">مسار الإنتاج</span>
                    <h3>من الفكرة إلى السيناريو</h3>
                    <p>شرح كيفية التخطيط للفيلم القصير، إدارة فريق العمل، وتحويل الفكرة إلى سيناريو جاهز للتنفيذ.</p>
                </div>

                <div class="card workshop-card">
                    <span class="role">مسار التصوير والإضاءة</span>
                    <h3>قراءة الكادر واللغة البصرية</h3>
                    <p>تطبيق عملي حقيقي على المسرح لشرح اختيار زوايا الكاميرا وتأثير الإضاءة في إيصال المشاعر.</p>
                </div>

                <div class="card workshop-card">
                    <span class="role">مسار التسويق والإعلام</span>
                    <h3>صناعة الهوية وجذب الجمهور</h3>
                    <p>عرض استراتيجية تسويق الفيلم، تصميم الإعلانات التشويقية، وكتابة المحتوى الترويجي.</p>
                </div>

            </div>
        </section>

        <!-- أجندة الفعالية -->
        <section>
            <h2 class="section-title">التسلسل الزمني للفعالية (الأجندة)</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <span class="time">10 دقائق</span>
                    <div><strong>الافتتاح والترحيب:</strong> مقدمة حماسية عن أهمية الإعلام والسينما يلقيها مسار التقديم.</div>
                </div>
                <div class="timeline-item">
                    <span class="time">30 دقيقة</span>
                    <div><strong>الورش التفاعلية:</strong> فقرات سريعة لكل مسار لشرح محاور العمل قبل المشاهدة.</div>
                </div>
                <div class="timeline-item">
                    <span class="time">20 دقيقة</span>
                    <div><strong>العرض الرئيسي:</strong> عرض الفيلم القصير المختار على الشاشة الكبرى.</div>
                </div>
                <div class="timeline-item">
                    <span class="time">15 دقيقة</span>
                    <div><strong>الجلسة الحوارية والختام:</strong> فتح باب النقاش مع الطلاب والضيوف وختام الفعالية.</div>
                </div>
            </div>
        </section>

        <!-- متطلبات الجامعة -->
        <section>
            <h2 class="section-title">احتياجاتنا من الجامعة</h2>
            <div class="card">
                <ul class="needs-list">
                    <li>حجز مسرح الجامعة الرئيسي أو قاعة مؤتمرات مجهزة.</li>
                    <li>توفير شاشة عرض (Data Show) بنظام صوتي عالي الجودة.</li>
                    <li>إضاءة مسرحية متناسقة للورش التطبيقية.</li>
                    <li>الموافقة على نشر البوستر الرسمي وتوجيه الدعوة لطلاب الجامعة عبر قنوات التواصل.</li>
                </ul>
            </div>
        </section>

        <footer>
            إعداد وتنسيق: خالد الهلال - النادي الإعلامي © 2026
        </footer>

    </div>

</body>
</html>
