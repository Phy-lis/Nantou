<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meowdia Marketing｜喵媒體行銷</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* 自訂樣式 - 使用新色盤 */
        /* 色盤: #bbe1c3, #a7cdbd, #869d7a, #91785d, #8b5d33 */
        html {
             scroll-behavior: smooth;
        }
        body {
            margin: 0; padding: 0; overflow-x: hidden;
            font-family: 'Noto Serif TC', serif; background-color: #fdfdfd;
            padding-top: 64px; /* 為固定導覽列預留空間 */
        }

        /* 固定導覽列 */
        nav {
            position: fixed; top: 0; left: 0; width: 100%; height: 64px;
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(8px);
            z-index: 50; /* 確保導覽列在最上層 */
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
            display: flex; align-items: center; justify-content: space-between;
            padding: 0 2rem;
        }
        /* 更新：讓 Logo 可點擊 */
        nav .logo a {
            font-weight: 700; font-size: 1.25rem; color: #869d7a;
            text-decoration: none; /* 移除連結底線 */
        }
        nav .nav-links a {
            margin-left: 1.5rem; text-decoration: none; color: #4a5568;
            transition: color 0.3s ease; font-size: 0.95rem;
        }
        nav .nav-links a:hover { color: #869d7a; }

        /* 主要內容區域 */
        main { display: block; }

        /* Hero Section */
        .hero-section {
            background-image: url('https://ai.google.dev/static/site-assets/images/marketing/gemini-api/google-io-2024/image_ea3a16.jpg');
            background-size: cover; background-position: center; background-repeat: no-repeat;
            padding: 6rem 2rem; text-align: center;
            position: relative; color: #ffffff;
        }
        .hero-section::before {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background-color: rgba(0, 0, 0, 0.35); z-index: 1;
        }
        .hero-section h1, .hero-section p, .hero-section .cta-button {
             position: relative; z-index: 2;
        }
        .hero-section h1 {
            font-size: 3.2rem; font-weight: 700; margin-bottom: 1.5rem;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.6);
        }
        .hero-section p {
            font-size: 1.2rem; color: rgba(255, 255, 255, 0.9); max-width: 650px;
            margin: 0 auto 3rem auto; text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        }
        .cta-button {
            background-color: #8b5d33; color: white; padding: 0.8rem 1.8rem; border-radius: 0.375rem;
            text-decoration: none; font-size: 1rem; font-weight: 600;
            transition: background-color 0.3s ease, transform 0.2s ease;
            display: inline-block; box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .cta-button:hover { background-color: #7a5129; transform: translateY(-2px); }

        /* 其他區塊通用樣式 */
        .content-section {
            padding: 4.5rem 2rem; max-width: 1200px; margin: 0 auto;
        }
        .section-title {
            font-size: 2.2rem; font-weight: 700; color: #869d7a;
            text-align: center; margin-bottom: 3.5rem;
        }

        /* 服務亮點區塊 */
        .services-highlight {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
        }
        .service-highlight-item {
            background-color: white; padding: 2.5rem; border-radius: 0.5rem;
            text-align: center; box-shadow: 0 4px 10px rgba(0,0,0,0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid #eee;
        }
        .service-highlight-item:hover {
            transform: translateY(-6px); box-shadow: 0 12px 20px rgba(0,0,0,0.08);
        }
        .service-highlight-item svg {
             width: 50px; height: 50px; margin: 0 auto 1.5rem auto; color: #869d7a;
        }
        .service-highlight-item h3 {
            font-size: 1.3rem; font-weight: 600; color: #333; margin-bottom: 0.75rem;
        }
        .service-highlight-item p {
            font-size: 0.95rem; color: #666; margin-bottom: 1.5rem;
        }
        .service-highlight-item a {
             color: #869d7a; text-decoration: none; font-weight: 600;
        }
         .service-highlight-item a:hover {
             color: #6c8161; text-decoration: underline;
        }

        /* 客戶展示區塊 */
        .clients-section { background-color: #f0f5f1; }
        .client-logo-container-home {
            display: flex; flex-wrap: wrap; gap: 2.5rem;
            justify-content: center; align-items: center;
        }
        .client-logo-home {
            height: 50px; filter: grayscale(80%); opacity: 0.8;
            transition: filter 0.3s ease, opacity 0.3s ease;
        }
        .client-logo-home:hover { filter: grayscale(0%); opacity: 1; }
        .more-clients-link {
             display: block; text-align: center; margin-top: 2.5rem;
             color: #869d7a; text-decoration: none; font-weight: 600;
        }
        .more-clients-link:hover { color: #6c8161; text-decoration: underline; }

        /* 頁尾 */
        footer.main-footer {
            background-color: #869d7a; color: #f0f5f1;
            padding: 3rem 2rem; text-align: center;
        }
        footer.main-footer p { font-size: 0.9rem; color: #dde5db; }


        /* --- 子頁面樣式 --- */
        .page-section {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: rgba(253, 253, 253, 0.98); backdrop-filter: blur(5px);
            /* 更新：降低 z-index 使其在導覽列下方 */
            z-index: 40;
            overflow-y: auto; padding: 3rem 2rem; color: #333;
            /* 更新：確保 padding-top 足夠 (考慮到 nav 高度 64px) */
            padding-top: calc(64px + 2rem); /* 導覽列高度 + 額外間距 */
        }
        .page-title {
            font-size: 2.5rem; font-weight: 700; color: #4a5568; text-align: center;
            margin-bottom: 3rem;
            border-bottom: 2px solid #cbd5e0; padding-bottom: 1rem;
        }
        .page-content {
            max-width: 1000px; margin: 0 auto; line-height: 1.8;
        }
        /* 移除 .back-button 樣式 */
        /* .back-button { ... } */

        .page-footer {
             margin-top: 4rem; padding-top: 1.5rem; text-align: center;
             font-size: 0.875rem; color: #718096; border-top: 1px solid #e2e8f0;
        }
        .message-box { /* 保持不變 */ }

        /* 服務項目頁面 */
        .service-item {
            background-color: white; padding: 2rem; border-radius: 0.5rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05); border: 1px solid #eee;
            display: flex; align-items: flex-start; gap: 1.5rem;
        }
        .service-item svg {
            width: 40px; height: 40px; color: #869d7a; flex-shrink: 0; margin-top: 0.25rem;
        }
        .service-item h2 {
            color: #869d7a; margin-bottom: 0.5rem; font-size: 1.3rem;
        }
        .service-item p { color: #555; line-height: 1.7; }

        /* 客戶案例頁面 */
        .case-study-item {
            background-color: white; border-radius: 0.5rem; box-shadow: 0 4px 10px rgba(0,0,0,0.05);
            border: 1px solid #eee; overflow: hidden; display: flex; flex-direction: column;
        }
        .case-study-item img { width: 100%; height: 200px; object-fit: cover; }
        .case-study-content { padding: 1.5rem; }
        .case-study-item h2 { color: #869d7a; margin-bottom: 0.5rem; font-size: 1.3rem; }
        .case-study-item .client-name { font-size: 0.9rem; color: #777; margin-bottom: 1rem; display: block; }
        .case-study-item p { color: #555; margin-bottom: 1rem; line-height: 1.7; }
        .case-study-item a { color: #869d7a; text-decoration: none; font-weight: 600; display: inline-block; margin-top: auto; }
        .case-study-item a:hover { color: #6c8161; text-decoration: underline; }

        /* 最新消息頁面 */
        .news-item {
            background-color: white; padding: 2rem; border-radius: 0.5rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05); border: 1px solid #eee; margin-bottom: 2rem;
        }
        .news-item h2 { color: #869d7a; margin-bottom: 0.5rem; font-size: 1.4rem; }
        .news-item .news-date { font-size: 0.9rem; color: #777; margin-bottom: 1rem; display: block; }
        .news-item p { color: #555; margin-bottom: 1rem; line-height: 1.7; }
        .news-item a.read-more-link { color: #869d7a; text-decoration: none; font-weight: 600; display: inline-block; margin-top: 0.5rem; }
        .news-item a.read-more-link:hover { color: #6c8161; text-decoration: underline; }
        .news-detail {
            margin-top: 1.5rem; padding-top: 1.5rem; border-top: 1px dashed #d1d5db;
            background-color: #f9fafb; padding: 1.5rem; border-radius: 0.375rem;
        }
        .news-detail p, .news-detail ul { color: #4b5563; }
        .news-detail a.inline-link { color: #869d7a; }
        .news-detail a.inline-link:hover { color: #6c8161; }

        /* 子頁面網格佈局 */
        .page-grid { display: grid; grid-template-columns: 1fr; gap: 2rem; }
        @media (min-width: 768px) {
            .page-grid-cols-2 { grid-template-columns: repeat(2, 1fr); gap: 2.5rem; }
        }

        /* 子頁面的客戶 Logo 容器 (保持不變) */
        .client-logo-container { display: flex; flex-wrap: wrap; gap: 2rem; justify-content: center; align-items: center; margin-top: 2rem; }
        .client-logo { height: 60px; filter: grayscale(100%); opacity: 0.7; transition: filter 0.3s ease, opacity 0.3s ease; }
        .client-logo:hover { filter: grayscale(0%); opacity: 1; }
        /* 聯絡表單 (保持不變) */
        .contact-form label { display: block; margin-bottom: 0.5rem; font-weight: 600; color: #4a5568; }
        .contact-form input, .contact-form textarea { width: 100%; padding: 0.75rem; border: 1px solid #cbd5e0; border-radius: 0.375rem; margin-bottom: 1rem; font-family: inherit; }
        .contact-form button { background-color: #8b5d33; }
        .contact-form button:hover { background-color: #7a5129; }

    </style>
</head>
<body>

    <nav>
        <div class="logo">
            <a href="#" onclick="navigateTo('main-content')">Meowdia Marketing</a>
        </div>
        <div class="nav-links">
            <a href="#services" onclick="navigateTo('services-page')">服務項目</a>
            <a href="#clients" onclick="navigateTo('clients-page')">合作客戶</a>
            <a href="#case-studies" onclick="navigateTo('case-studies-page')">客戶案例</a>
            <a href="#about-us" onclick="navigateTo('about-us-page')">關於我們</a>
            <a href="#news" onclick="navigateTo('news-page')">最新消息</a>
            <a href="#contact" onclick="navigateTo('contact-page')">立即諮詢</a>
        </div>
    </nav>

    <main id="main-content">
        <section class="hero-section">
            <h1>放大您的社群影響力</h1>
            <p>Meowdia Marketing 專注於為品牌打造有溫度、高互動的社群連結，讓您的故事被更多人看見。</p>
            <a href="#" class="cta-button" onclick="navigateTo('contact-page')">立即開始諮詢</a>
        </section>
        <section class="content-section">
            <h2 class="section-title">核心服務</h2>
            <div class="services-highlight">
                <div class="service-highlight-item">
                     <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M16.862 4.487l1.687-1.688a1.875 1.875 0 112.652 2.652L10.582 16.07a4.5 4.5 0 01-1.897 1.13L6 18l.8-2.685a4.5 4.5 0 011.13-1.897l8.932-8.931zm0 0L19.5 7.125M18 14v4.75A2.25 2.25 0 0115.75 21H5.25A2.25 2.25 0 013 18.75V8.25A2.25 2.25 0 015.25 6H10" /></svg>
                    <h3>社群代管與內容</h3>
                    <p>建立品牌形象，製作吸睛內容，提升粉絲互動。</p>
                    <a href="#" onclick="navigateTo('services-page')">了解更多 &rarr;</a>
                </div>
                <div class="service-highlight-item">
                     <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M10.5 6a7.5 7.5 0 107.5 7.5h-7.5V6z" /><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 10.5H21A7.5 7.5 0 0013.5 3v7.5z" /></svg>
                    <h3>廣告投放優化</h3>
                    <p>精準觸及目標受眾，最大化廣告效益與轉換率。</p>
                    <a href="#" onclick="navigateTo('services-page')">了解更多 &rarr;</a>
                </div>
                <div class="service-highlight-item">
                     <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M18 18.72a9.094 9.094 0 003.741-.479 3 3 0 00-4.682-2.72m.94 3.198l.001.031c0 .225-.012.447-.037.666A11.944 11.944 0 0112 21c-2.17 0-4.207-.576-5.963-1.584A6.062 6.062 0 016 18.719m12 0a5.971 5.971 0 00-.941-3.197m0 0A5.995 5.995 0 0012 12.75a5.995 5.995 0 00-5.058 2.772m0 0a3 3 0 00-4.681 2.72 8.986 8.986 0 003.74.477m.94-3.197a5.971 5.971 0 00.94 3.197M15 6.75a3 3 0 11-6 0 3 3 0 016 0zm6 3a2.25 2.25 0 11-4.5 0 2.25 2.25 0 014.5 0zM12 12.75a2.25 2.25 0 110-4.5 2.25 2.25 0 010 4.5z" /></svg>
                    <h3>KOL 影響力行銷</h3>
                    <p>媒合最適網紅，擴大品牌聲量與市場觸及。</p>
                    <a href="#" onclick="navigateTo('services-page')">了解更多 &rarr;</a>
                </div>
            </div>
        </section>
        <section class="content-section clients-section">
            <h2 class="section-title">他們都選擇 Meowdia</h2>
            <div class="client-logo-container-home">
                <img src="https://placehold.co/120x50/ffffff/a0aec0?text=客戶A" alt="客戶 Logo A" class="client-logo-home">
                <img src="https://placehold.co/120x50/ffffff/a0aec0?text=客戶B" alt="客戶 Logo B" class="client-logo-home">
                <img src="https://placehold.co/120x50/ffffff/a0aec0?text=客戶C" alt="客戶 Logo C" class="client-logo-home">
                <img src="https://placehold.co/120x50/ffffff/a0aec0?text=客戶D" alt="客戶 Logo D" class="client-logo-home">
                <img src="https://placehold.co/120x50/ffffff/a0aec0?text=客戶E" alt="客戶 Logo E" class="client-logo-home">
            </div>
             <a href="#" class="more-clients-link" onclick="navigateTo('clients-page')">查看更多合作夥伴 &rarr;</a>
        </section>
        <footer class="main-footer">
            <p>© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</p>
        </footer>
    </main>

    <div id="services-page" class="page-section">
        <h1 class="page-title">我們的服務</h1>
        <div class="page-content">
            <p class="text-center text-gray-600 mb-12">我們提供全方位的社群行銷解決方案，助您達成品牌目標。</p>
            <div class="page-grid page-grid-cols-2"> <div class="service-item">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M16.862 4.487l1.687-1.688a1.875 1.875 0 112.652 2.652L10.582 16.07a4.5 4.5 0 01-1.897 1.13L6 18l.8-2.685a4.5 4.5 0 011.13-1.897l8.932-8.931zm0 0L19.5 7.125M18 14v4.75A2.25 2.25 0 0115.75 21H5.25A2.25 2.25 0 013 18.75V8.25A2.25 2.25 0 015.25 6H10" /></svg>
                    <div>
                        <h2 class="text-xl font-semibold">社群帳號代管</h2>
                        <p>全方位管理您的 Facebook、Instagram、LINE OA 等社群平台，建立品牌形象，提升粉絲互動，維持品牌聲量。</p>
                    </div>
                </div>
                <div class="service-item">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M10.5 6a7.5 7.5 0 107.5 7.5h-7.5V6z" /><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 10.5H21A7.5 7.5 0 0013.5 3v7.5z" /></svg>
                    <div>
                        <h2 class="text-xl font-semibold">廣告投放優化</h2>
                        <p>精準設定目標受眾，進行 A/B 測試，優化廣告預算分配，提升轉換率，達成行銷目標。</p>
                    </div>
                </div>
                <div class="service-item">
                     <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M12 18v-5.25m0 0a6.01 6.01 0 001.5-.189m-1.5.189a6.01 6.01 0 01-1.5-.189m3 .378a3 3 0 11-6 0 3 3 0 016 0zM12 12.75h.008v.008H12v-.008z" /><path stroke-linecap="round" stroke-linejoin="round" d="M7.5 6.75h.75v.75h-.75zM15 6.75h.75v.75h-.75z" /><path stroke-linecap="round" stroke-linejoin="round" d="M16.5 18.75h.75v.75h-.75zM9 18.75h.75v.75h-.75z" /><path stroke-linecap="round" stroke-linejoin="round" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
                    <div>
                        <h2 class="text-xl font-semibold">內容創意發想</h2>
                        <p>製作吸睛圖文、短影音、互動遊戲、活動企劃，打造高擴散力的病毒式內容，引爆社群討論。</p>
                    </div>
                </div>
                <div class="service-item">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M18 18.72a9.094 9.094 0 003.741-.479 3 3 0 00-4.682-2.72m.94 3.198l.001.031c0 .225-.012.447-.037.666A11.944 11.944 0 0112 21c-2.17 0-4.207-.576-5.963-1.584A6.062 6.062 0 016 18.719m12 0a5.971 5.971 0 00-.941-3.197m0 0A5.995 5.995 0 0012 12.75a5.995 5.995 0 00-5.058 2.772m0 0a3 3 0 00-4.681 2.72 8.986 8.986 0 003.74.477m.94-3.197a5.971 5.971 0 00.94 3.197M15 6.75a3 3 0 11-6 0 3 3 0 016 0zm6 3a2.25 2.25 0 11-4.5 0 2.25 2.25 0 014.5 0zM12 12.75a2.25 2.25 0 110-4.5 2.25 2.25 0 010 4.5z" /></svg>
                    <div>
                        <h2 class="text-xl font-semibold">KOL/網紅媒合</h2>
                        <p>根據品牌調性與行銷目標，篩選並媒合最適合的意見領袖，策劃合作內容，擴大品牌影響力。</p>
                    </div>
                </div>
            </div>
        </div>
        <footer class="page-footer">© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</footer>
    </div>

    <div id="clients-page" class="page-section">
         <h1 class="page-title">合作客戶</h1>
         <div class="page-content">
             <p class="text-center mb-8">我們很榮幸能與眾多優秀品牌合作，共同成長。</p>
             <div class="client-logo-container">
                 <img src="https://placehold.co/150x60/e2e8f0/a0aec0?text=客戶Logo+A" alt="客戶 Logo A" class="client-logo">
                 <img src="https://placehold.co/150x60/e2e8f0/a0aec0?text=客戶Logo+B" alt="客戶 Logo B" class="client-logo">
                 <img src="https://placehold.co/150x60/e2e8f0/a0aec0?text=客戶Logo+C" alt="客戶 Logo C" class="client-logo">
                 <img src="https://placehold.co/150x60/e2e8f0/a0aec0?text=客戶Logo+D" alt="客戶 Logo D" class="client-logo">
                 <img src="https://placehold.co/150x60/e2e8f0/a0aec0?text=客戶Logo+E" alt="客戶 Logo E" class="client-logo">
                 <img src="https://placehold.co/150x60/e2e8f0/a0aec0?text=客戶Logo+F" alt="客戶 Logo F" class="client-logo">
             </div>
         </div>
         <footer class="page-footer">© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</footer>
    </div>

    <div id="case-studies-page" class="page-section">
         <h1 class="page-title">客戶案例</h1>
         <div class="page-content">
             <p class="text-center text-gray-600 mb-12">探索我們如何透過創意策略，為客戶帶來實質成效。</p>
             <div class="page-grid page-grid-cols-2"> <div class="case-study-item">
                     <img src="https://placehold.co/600x338/a7cdbd/ffffff?text=案例研究+A+(600x338)" alt="案例研究 A 圖片">
                     <div class="case-study-content">
                         <h2 class="text-xl font-semibold">時尚品牌 A - IG 粉絲增長 200%</h2>
                         <span class="client-name">客戶：時尚品牌 A</span>
                         <p>透過內容優化與互動活動企劃，三個月內 Instagram 粉絲數顯著提升，互動率增加 50%。</p>
                         <a href="#" class="mt-2 inline-block">閱讀完整案例 (暫無)</a>
                     </div>
                 </div>
                 <div class="case-study-item">
                     <img src="https://placehold.co/600x338/bbe1c3/ffffff?text=案例研究+B+(600x338)" alt="案例研究 B 圖片">
                     <div class="case-study-content">
                         <h2 class="text-xl font-semibold">餐飲品牌 B - FB 廣告轉換提升 30%</h2>
                         <span class="client-name">客戶：餐飲品牌 B</span>
                         <p>精準鎖定潛在客戶，優化廣告素材與文案，成功提升線上訂單轉換率，降低每次轉換成本。</p>
                         <a href="#" class="mt-2 inline-block">閱讀完整案例 (暫無)</a>
                     </div>
                 </div>
                 <div class="case-study-item">
                     <img src="https://placehold.co/600x338/f0f5f1/444444?text=案例研究+C+(600x338)" alt="案例研究 C 圖片">
                     <div class="case-study-content">
                         <h2 class="text-xl font-semibold">生活用品 C - 新品上市成功曝光</h2>
                         <span class="client-name">客戶：生活用品 C</span>
                         <p>結合網紅開箱與社群抽獎活動，新品上市首月即達成預期銷售目標，創造高討論度。</p>
                         <a href="#" class="mt-2 inline-block">閱讀完整案例 (暫無)</a>
                     </div>
                 </div>
                 </div>
         </div>
         <footer class="page-footer">© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</footer>
    </div>

    <div id="about-us-page" class="page-section">
         <h1 class="page-title">關於 Meowdia</h1>
         <div class="page-content">
             <h2 class="text-2xl font-semibold mb-4 text-gray-700">我們的理念</h2><p class="mb-6">在 Meowdia Marketing，我們相信社群的力量。我們不只做行銷，更致力於為品牌與受眾建立真實、有意義的連結。如同貓咪般靈活、敏銳、充滿好奇心，我們為客戶挖掘社群中的無限可能。</p>
             <h2 class="text-2xl font-semibold mb-4 text-gray-700">我們的團隊</h2><p class="mb-6">（此處可放置團隊介紹文字或照片區塊）</p><p>我們是一群熱愛社群、充滿創意的行銷專家，擁有豐富的產業經驗與對市場趨勢的敏銳洞察力。我們樂於接受挑戰，為客戶量身打造最有效的社群行銷策略。</p>
             <h2 class="text-2xl font-semibold mb-4 text-gray-700">公司里程碑</h2><p>（此處可放置公司發展歷程或重要記事）</p>
         </div>
         <footer class="page-footer">© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</footer>
    </div>

    <div id="contact-page" class="page-section">
         <h1 class="page-title">立即諮詢</h1>
         <div class="page-content grid grid-cols-1 md:grid-cols-2 gap-8">
             <div><h2 class="text-2xl font-semibold mb-4 text-gray-700">與我們聯繫</h2><p class="mb-4">對我們的服務感興趣嗎？或是有任何行銷上的疑問？<br>歡迎透過以下方式與我們聯繫，或填寫右側表單，我們會盡快回覆您！</p><p class="mb-2"><strong>Email:</strong> contact@meowdia.tw (範例)</p><p class="mb-2"><strong>電話:</strong> (02) 1234-5678 (範例)</p><p class="mb-2"><strong>地址:</strong> 123 喵喵大道, 貓奴區, 數位市 (範例)</p><p class="mb-2"><strong>服務時間:</strong> 週一至週五 09:00 - 18:00</p></div>
             <form class="contact-form"><h2 class="text-2xl font-semibold mb-4 text-gray-700">諮詢表單</h2><div><label for="name">姓名</label><input type="text" id="name" name="name" required></div><div><label for="email">電子郵件</label><input type="email" id="email" name="email" required></div><div><label for="phone">聯絡電話 (選填)</label><input type="tel" id="phone" name="phone"></div><div><label for="message">您的訊息</label><textarea id="message" name="message" rows="5" required></textarea></div><button type="submit">送出表單</button></form>
         </div>
         <footer class="page-footer">© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</footer>
    </div>

    <div id="news-page" class="page-section">
         <h1 class="page-title">最新消息</h1>
         <div class="page-content">
             <div class="news-item">
                 <h2 class="text-xl font-semibold">Meowdia 榮獲 2025 年度最佳社群行銷創意獎</h2>
                 <span class="news-date">發布日期：2025 年 4 月 10 日</span>
                 <p>感謝客戶與評審的肯定！Meowdia 將持續帶來更多創新、有效的社群行銷方案。</p>
                 <div id="news-detail-1" class="news-detail"><p>我們非常榮幸地宣布，Meowdia Marketing 在競爭激烈的評選中脫穎而出，榮獲由《數位時代》雜誌主辦的「2025 年度最佳社群行銷創意獎」。此次獲獎是對我們團隊創意、策略執行力以及客戶合作成果的高度肯定。</p><p class="mt-2">評審團特別讚揚了我們為客戶「時尚品牌 A」所執行的 Instagram 整合行銷活動，該活動不僅成功提升品牌知名度，更有效帶動了粉絲互動與實際銷售轉換。我們將秉持初衷，繼續為客戶提供最前瞻、最有效的社群解決方案。</p></div>
                 <a href="#" class="read-more-link mt-2 inline-block" data-target="news-detail-1">閱讀更多</a>
             </div>
             <div class="news-item">
                 <h2 class="text-xl font-semibold">【產業洞察】短影音趨勢分析與品牌應用策略</h2>
                 <span class="news-date">發布日期：2025 年 3 月 28 日</span>
                 <p>掌握 Reels、Shorts、TikTok 的最新玩法，讓您的品牌在短影音浪潮中脫穎而出。</p>
                 <div id="news-detail-2" class="news-detail"><p>短影音已成為社群平台的主流內容形式。本篇文章將深入分析 Instagram Reels、YouTube Shorts 及 TikTok 的最新演算法特性、熱門內容風格與使用者偏好，並提供品牌主實際可行的應用策略，包含：</p><ul class="list-disc list-inside ml-4 mt-2"><li>如何製作高互動率的原生短影音內容</li><li>如何運用熱門音效與挑戰賽增加曝光</li><li>短影音廣告投放的最佳實踐</li><li>結合網紅行銷放大短影音效益</li></ul><p class="mt-2">立即閱讀，掌握短影音行銷的致勝關鍵！</p></div>
                 <a href="#" class="read-more-link mt-2 inline-block" data-target="news-detail-2">閱讀更多</a>
             </div>
             <div class="news-item">
                 <h2 class="text-xl font-semibold">Meowdia 擴大徵才！尋找熱愛社群的你</h2>
                 <span class="news-date">發布日期：2025 年 3 月 15 日</span>
                 <p>我們正在尋找社群經理、廣告投手、內容企劃等夥伴，歡迎加入 Meowdia 大家庭！</p>
                 <div id="news-detail-3" class="news-detail"><p>隨著業務的快速發展，Meowdia Marketing 正積極擴大我們的專業團隊！我們正在尋找對社群充滿熱情、勇於創新、樂於學習的優秀人才。</p><p class="mt-2">目前開放職缺包含：</p><ul class="list-disc list-inside ml-4 mt-2"><li>資深社群經理 (Senior Social Media Manager)</li><li>數位廣告優化師 (Digital Advertising Specialist)</li><li>社群內容企劃 (Social Media Content Creator)</li><li>客戶關係經理 (Account Manager)</li></ul><p class="mt-2">如果您符合條件並渴望在充滿活力的環境中成長，請將您的履歷寄至 <a href="mailto:hr@meowdia.tw" class="inline-link">hr@meowdia.tw</a> (範例)。</p></div>
                 <a href="#" class="read-more-link mt-2 inline-block" data-target="news-detail-3">閱讀更多</a>
             </div>
         </div>
         <footer class="page-footer">© 2025 Meowdia Marketing｜喵媒體行銷股份有限公司. All rights reserved.</footer>
    </div>

    <div id="messageBox" class="message-box"></div>

    <script>
        // JavaScript 保持不變
        const pageSections = document.querySelectorAll('.page-section');
        const mainContent = document.getElementById('main-content');

        function navigateTo(pageId) {
            event.preventDefault();
            pageSections.forEach(section => { section.style.display = 'none'; });
            if(mainContent) { mainContent.style.display = 'none'; }
            if (pageId === 'main-content' || pageId === null) {
                 if(mainContent) { mainContent.style.display = 'block'; }
                 window.scrollTo(0, 0);
            } else {
                const targetPage = document.getElementById(pageId);
                if (targetPage) {
                    targetPage.style.display = 'block';
                    // 將頁面滾動到頂部 (考慮到固定導覽列)
                    // window.scrollTo(0, 0); // 直接滾動到頂部可能會被 navbar 遮住
                    targetPage.scrollTop = 0; // 滾動子頁面自身內容到頂部
                } else {
                    console.error("找不到頁面:", pageId);
                     if(mainContent) { mainContent.style.display = 'block'; }
                }
            }
            console.log(`Navigating to: ${pageId}`);
        }

        function showMessage(text) {
            const messageBox = document.getElementById('messageBox');
            messageBox.textContent = text; messageBox.style.display = 'block';
            setTimeout(() => { messageBox.style.display = 'none'; }, 2000);
        }

        window.addEventListener('load', () => {
            console.log('頁面已載入');
            pageSections.forEach(section => { section.style.display = 'none'; });
             if(mainContent) { mainContent.style.display = 'block'; }
        });

        const contactForm = document.querySelector('.contact-form');
        if (contactForm) {
            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                showMessage('感謝您的諮詢，我們會盡快與您聯繫！');
                contactForm.reset();
            });
        }

        const readMoreLinks = document.querySelectorAll('.read-more-link');
        readMoreLinks.forEach(link => {
            link.addEventListener('click', function(event) {
                event.preventDefault();
                const targetId = this.getAttribute('data-target');
                const targetDetail = document.getElementById(targetId);
                if (targetDetail) {
                    const isHidden = targetDetail.style.display === 'none' || targetDetail.style.display === '';
                    targetDetail.style.display = isHidden ? 'block' : 'none';
                    this.textContent = isHidden ? '收起內容' : '閱讀更多';
                } else { console.error('找不到目標詳細內容區塊:', targetId); }
            });
        });
    </script>

</body>
</html>
