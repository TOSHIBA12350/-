<!DOCTYPE html>
<html lang="ar">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="محرك البحث استجلاء: محرك بحث متقدم يوفر البحث عن الإنترنت مع دعم البحث الصوتي.">
    <meta name="author" content="محرك البحث استجلاء">
    <meta name="robots" content="index, follow">
    <meta property="og:title" content="محرك البحث استجلاء">
    <meta property="og:description" content="محرك البحث استجلاء - البحث في الإنترنت بسهولة مع دعم الترجمة الصوتية.">
    <meta property="og:image" content="https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Google_Chromium_logo.svg/1200px-Google_Chromium_logo.svg.png">
    <meta property="og:url" content="http://www.yoursite.com">
    
    <title>محرك البحث استجلاء</title>
    <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/thumb/3/37/Google_Chromium_logo.svg/1200px-Google_Chromium_logo.svg.png" type="image/x-icon">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #121212, #000, #2575fc); /* تدرج بين الأسود والأزرق */
            background-size: 400% 400%;
            animation: backgroundAnimation 15s ease infinite; 
            color: #e0e0e0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            text-align: center;
            margin: 0;
        }

        @keyframes backgroundAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        h1 {
            font-size: 3rem;
            color: #fff;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeIn 1.5s ease-out forwards;
        }

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

        .search-container {
            width: 100%;
            max-width: 600px;
            background-color: rgba(0, 0, 0, 0.8);
            border-radius: 50px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            margin-bottom: 30px;
            transition: transform 0.3s ease;
        }

        .search-container:hover {
            transform: scale(1.05);
        }

        .search-container input {
            width: 80%;
            height: 45px;
            border: none;
            outline: none;
            padding: 0 15px;
            border-radius: 50px;
            font-size: 18px;
            background-color: #333; /* الخلفية الداكنة */
            color: #fff; /* النص باللون الأبيض */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .search-container input:focus {
            border: 2px solid #2575fc; /* اللون الأزرق عند التركيز */
            box-shadow: 0 0 8px rgba(37, 117, 252, 0.6);
        }

        .search-container button {
            width: 60px;
            height: 45px;
            border: none;
            background-color: #2575fc; /* اللون الأزرق */
            color: white;
            border-radius: 50px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s, transform 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .search-container button:hover {
            background-color: #6a11cb;
            transform: scale(1.1);
        }

        .search-container #voice-search {
            animation: voiceButtonAnimation 2s infinite;
        }

        @keyframes voiceButtonAnimation {
            0% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0); }
        }

        .footer-buttons {
            margin-top: 20px;
            display: flex;
            justify-content: center;
        }

        .footer-buttons button {
            background-color: #333; /* اللون الأسود */
            color: #fff; /* النص الأبيض */
            border: 1px solid #dcdcdc;
            border-radius: 30px;
            padding: 10px 20px;
            margin: 0 10px;
            cursor: pointer;
            font-size: 14px;
            transition: background-color 0.3s, transform 0.3s;
        }

        .footer-buttons button:hover {
            background-color: #2575fc;
            transform: scale(1.05);
        }

        .links {
            margin-top: 20px;
            font-size: 16px;
        }

        .links a {
            color: #fff;
            text-decoration: none;
            margin: 0 10px;
        }

        .links a:hover {
            color: #2575fc; /* اللون الأزرق عند التمرير */
        }
    </style>
</head>

<body>

    <h1>محرك البحث استجلاء</h1>
    <div class="search-container">
        <input type="text" id="search-query" placeholder="ابحث في الإنترنت..." />
        <button id="search-btn" onclick="search()">بحث</button>
        <button id="voice-search" onclick="startVoiceSearch()">🎤</button>
    </div>

    <div class="footer-buttons">
        <button onclick="changeLanguage('ar')">العربية</button>
        <button onclick="changeLanguage('en')">English</button>
    </div>

    <div class="links">
        <a href="https://www.google.com" target="_blank">Google</a>
        <a href="https://www.youtube.com" target="_blank">YouTube</a>
    </div>

    <script>
        // البحث في محرك البحث الافتراضي في المتصفح (هنا افترضنا Google)
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
                document.getElementById("search-btn").textContent = "بحث"; // تغيير نص الزر
            } else {
                document.documentElement.setAttribute("lang", "en");
                document.querySelector("h1").textContent = "Ijlaa Search";
                document.querySelector("input").setAttribute("placeholder", "Search the internet...");
                document.getElementById("search-btn").textContent = "Search"; // تغيير نص الزر
            }
        }

        // تعريف SpeechRecognition
        var recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();

        recognition.onresult = function(event) {
            const voiceQuery = event.results[0][0].transcript;
            document.getElementById("search-query").value = voiceQuery;
            search();
        }

        recognition.onerror = function(event) {
            alert("حدث خطأ أثناء محاولة التعرف على الصوت: " + event.error);
        }

        // البدء في البحث الصوتي
        function startVoiceSearch() {
            recognition.start();
        }

        recognition.lang = 'ar-SA';
    </script>
</body>

</html>
