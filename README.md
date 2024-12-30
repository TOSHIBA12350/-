<!DOCTYPE html>
<html lang="ar">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="محرك البحث استجلاء: محرك بحث متقدم يوفر البحث عن الإنترنت مع دعم البحث الصوتي والوضع المظلم.">
    <meta name="author" content="محرك البحث استجلاء">
    <meta name="robots" content="index, follow">
    <meta property="og:title" content="محرك البحث استجلاء">
    <meta property="og:description" content="محرك البحث استجلاء - البحث في الإنترنت بسهولة مع دعم الترجمة الصوتية والوضع المظلم.">
    <meta property="og:image" content="https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Google_Chromium_logo.svg/1200px-Google_Chromium_logo.svg.png">
    <meta property="og:url" content="http://www.yoursite.com">
    
    <title>محرك البحث استجلاء</title>
    <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Google_Chromium_logo.svg/1200px-Google_Chromium_logo.svg.png" type="image/x-icon">
    
    <!-- إضافة Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=UA-XXXXXXX-X"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'UA-XXXXXXX-X'); // استبدل مع ID الخاص بك
    </script>

    <style>
        /* إعدادات عامة */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            background-color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            text-align: center;
            margin: 0;
            transition: background-color 0.3s;
            background-size: cover;
            background-position: center;
            overflow: hidden;
        }

        h1 {
            font-size: 3rem;
            color: #0078d4;
            margin-bottom: 20px;
            opacity: 0;
            animation: fadeIn 1.5s ease-out forwards;
        }

        /* تأثير fadeIn عند تحميل الصفحة */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* تأثيرات الحقل وزر البحث */
        .search-container {
            width: 100%;
            max-width: 600px;
            background-color: #fff;
            border-radius: 24px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 15px;
            margin-bottom: 20px;
            transform: translateY(20px);
            animation: slideIn 1s ease-out forwards;
        }

        /* تأثير انزلاق الحقل */
        @keyframes slideIn {
            from {
                transform: translateY(20px);
                opacity: 0;
            }

            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .search-container input {
            width: 85%;
            height: 40px;
            border: none;
            outline: none;
            padding: 0 10px;
            border-radius: 30px;
            font-size: 16px;
            background-color: #f8f8f8;
            transition: all 0.3s ease;
        }

        .search-container input:focus {
            border: 2px solid #0078d4;
            box-shadow: 0 0 8px rgba(0, 120, 212, 0.5);
            transform: scale(1.05);
        }

        .search-container button {
            width: 50px;
            height: 40px;
            border: none;
            background-color: #f8f8f8;
            border-radius: 30px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s, transform 0.3s;
        }

        .search-container button:hover {
            background-color: #0078d4;
            color: #fff;
            transform: scale(1.1);
        }

        .search-container button#voice-search {
            background-color: #4c74af; /* اللون الأزرق للأيقونة الصوتية */
            color: white;
        }

        .search-container button#voice-search:hover {
            background-color: #45a049;
        }

        .footer-buttons {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            opacity: 0;
            animation: fadeIn 1.5s ease-out forwards 1s;
        }

        .footer-buttons button {
            background-color: #f8f8f8;
            border: 1px solid #dcdcdc;
            border-radius: 5px;
            padding: 8px 15px;
            margin: 0 10px;
            cursor: pointer;
            font-size: 14px;
            transition: background-color 0.3s, transform 0.3s;
        }

        .footer-buttons button:hover {
            background-color: #0078d4;
            color: #fff;
            transform: scale(1.05);
        }

        /* الوضع المظلم */
        .dark-mode {
            background-color: #121212;
            color: #e0e0e0;
        }

        .dark-mode .search-container {
            background-color: #333;
        }

        .dark-mode .search-container input {
            background-color: #555;
            color: #fff;
        }

        .dark-mode .search-container button {
            background-color: #333;
            color: #fff;
        }

        /* تأثيرات الأزرار */
        .animate-button {
            position: relative;
            animation: bounce 1s infinite;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-10px);
            }
        }
    </style>
</head>

<body>

    <h1>محرك البحث استجلاء</h1>
    <div class="search-container">
        <input type="text" id="search-query" placeholder="ابحث في الإنترنت..." />
        <button onclick="search()">بحث</button>
        <button id="voice-search" onclick="startVoiceSearch()" class="animate-button">🎤</button>
    </div>

    <div class="footer-buttons">
        <button onclick="changeLanguage('ar')">العربية</button>
        <button onclick="changeLanguage('en')">English</button>
        <button onclick="toggleDarkMode()">الوضع المظلم</button>
    </div>

    <script>
        // وظيفة البحث
        function search() {
            var query = document.getElementById("search-query").value;
            if (query) {
                window.location.href = "https://www.google.com/search?q=" + encodeURIComponent(query);
            } else {
                alert("يرجى إدخال مصطلح للبحث");
            }
        }

        // تغيير اللغة
        function changeLanguage(lang) {
            if (lang === 'ar') {
                document.documentElement.setAttribute("lang", "ar");
                document.querySelector("h1").textContent = "محرك البحث استجلاء";
                document.querySelector("input").setAttribute("placeholder", "ابحث في الإنترنت...");
                recognition.lang = 'ar-SA'; // ضبط اللغة العربية
            } else {
                document.documentElement.setAttribute("lang", "en");
                document.querySelector("h1").textContent = "Ijlaa Search";
                document.querySelector("input").setAttribute("placeholder", "Search the internet...");
                recognition.lang = 'en-US'; // ضبط اللغة الإنجليزية
            }
        }

        // تفعيل الوضع المظلم
        function toggleDarkMode() {
            document.body.classList.toggle("dark-mode");
        }

        // البحث الصوتي
        var recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();

        recognition.onresult = function(event) {
            const voiceQuery = event.results[0][0].transcript;
            document.getElementById("search-query").value = voiceQuery;
            search();
        }

        recognition.onerror = function(event) {
            alert("حدث خطأ أثناء محاولة التعرف على الصوت: " + event.error);
        }

        // بدء البحث الصوتي
        function startVoiceSearch() {
            recognition.start();
        }

        // إعداد اللغة الافتراضية عند تحميل الصفحة
        recognition.lang = 'ar-SA'; // الافتراضي: اللغة العربية
    </script>
</body>

</html>
