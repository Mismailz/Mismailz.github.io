<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="google" content="notranslate">
    <title>مصحف التفسير والتلاوة الإلكتروني</title>
    <link rel="preconnect" href="https://googleapis.com">
    <link rel="preconnect" href="https://gstatic.com" crossorigin>
    <link href="https://googleapis.com/css2?family=Amiri:ital@0;1&family=Cairo:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0f766e;
            --primary-light: #14b8a6;
            --accent: #b45309;
            --accent-bg: #fffbeb;
            --bg: #f8fafc;
            --card: #ffffff;
            --text: #1e293b;
        }
        * {
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
        }
        body {
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            padding: 0;
            padding-bottom: 120px;
        }
        header {
            background: linear-gradient(135deg, var(--primary), #115e59);
            color: white;
            text-align: center;
            padding: 30px 15px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
        }
        header h1 {
            margin: 0;
            font-size: 24px;
            font-weight: 700;
        }
        header p {
            margin: 8px 0 0 0;
            font-size: 13px;
            opacity: 0.9;
        }
        .container {
            max-width: 800px;
            margin: 25px auto;
            padding: 0 15px;
        }
        .selector-box {
            background: var(--card);
            padding: 15px;
            border-radius: 12px;
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05);
            margin-bottom: 25px;
            display: flex;
            flex-direction: column;
            gap: 10px;
            border: 1px solid #e2e8f0;
        }
        label {
            font-weight: bold;
            color: var(--primary);
        }
        select {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: 2px solid #e2e8f0;
            font-size: 16px;
            background-color: #fff;
            cursor: pointer;
            outline: none;
            transition: 0.2s;
        }
        select:focus {
            border-color: var(--primary-light);
        }
        .loading {
            text-align: center;
            font-size: 18px;
            color: #64748b;
            padding: 40px;
            display: none;
        }
        .quran-content {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        .verse-card {
            background: var(--card);
            border: 1px solid #e2e8f0;
            border-radius: 14px;
            padding: 25px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.03);
            transition: 0.2s;
        }
        .verse-text {
            font-family: 'Amiri', serif;
            font-size: 28px;
            line-height: 2.2;
            text-align: center;
            color: #065f46;
            margin-bottom: 15px;
            direction: rtl;
        }
        .verse-num {
            display: inline-block;
            width: 30px;
            height: 30px;
            line-height: 30px;
            background: #e6f4ea;
            color: #065f46;
            border-radius: 50%;
            font-size: 14px;
            font-family: 'Cairo', sans-serif;
            margin-right: 8px;
            text-align: center;
        }
        .tafsir-box {
            background-color: var(--accent-bg);
            border-right: 4px solid var(--accent);
            padding: 15px;
            border-radius: 6px;
            margin-top: 15px;
        }
        .tafsir-title {
            font-weight: bold;
            color: var(--accent);
            font-size: 13px;
            margin-bottom: 5px;
        }
        .tafsir-text {
            font-size: 15px;
            line-height: 1.6;
            color: #475569;
        }
        .play-btn {
            background-color: var(--primary-light);
            color: white;
            border: none;
            padding: 10px 18px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
            margin-top: 15px;
            transition: 0.2s;
            width: 100%;
        }
        .play-btn:hover {
            background-color: var(--primary);
        }
        .fixed-player {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: white;
            box-shadow: 0 -5px 20px rgba(0,0,0,0.1);
            padding: 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            z-index: 1000;
            border-top: 1px solid #e2e8f0;
        }
        .track-info {
            font-size: 13px;
            font-weight: bold;
            color: var(--primary);
            text-align: center;
        }
        audio {
            width: 100%;
            max-width: 600px;
        }
    </style>
</head>
<body>
    <header>
        <h1>مصحف التفسير والتلاوة الإلكتروني</h1>
        <p>بصوت الشيخ الحصري (مرتل) مع التفسير الميسر للآيات</p>
    </header>
    <div class="container">
        <div class="selector-box">
            <label for="surah-select">اختر السورة الكريمة:</label>
            <select id="surah-select" onchange="fetchSurahData(this.value)">
                <option value="">-- جاري تحميل قائمة السور... --</option>
            </select>
        </div>
        <div class="loading" id="loading-text">جاري جلب الآيات والتفسير الآن...</div>
        <div class="quran-content" id="quran-container"></div>
    </div>
    <div class="fixed-player">
        <div class="track-info" id="current-track">اضغط على زر التشغيل تحت أي آية للاستماع</div>
        <audio id="audio-player" controls autoplay></audio>
    </div>
<script>
    const surahSelect = document.getElementById('surah-select');
    const quranContainer = document.getElementById('quran-container');
    const loadingText = document.getElementById('loading-text');
    const audioPlayer = document.getElementById('audio-player');
    const currentTrackText = document.getElementById('current-track');
    async function loadSurahList() {
        try {
            const res = await fetch('https://alquran.cloud');
            const data = await res.json();
            surahSelect.innerHTML = '';
            data.data.forEach(surah => {
                const option = document.createElement('option');
                option.value = surah.number;
                option.textContent = surah.number + '. سورة ' + surah.name;
                surahSelect.appendChild(option);
            });
            fetchSurahData(1);
        } catch (error) {
            surahSelect.innerHTML = '<option>فشل تحميل السور، يرجى تحديث الصفحة</option>';
        }
    }
    async function fetchSurahData(surahNumber) {
        if (!surahNumber) return;
        quranContainer.innerHTML = '';
        loadingText.style.display = 'block';
        try {
            const [resArabic, resTafsir, resAudio] = await Promise.all([
                fetch('https://alquran.cloud/' + surahNumber),
                fetch('https://alquran.cloud/' + surahNumber + '/ar.jalalayn'),
                fetch('https://alquran.cloud/' + surahNumber + '/ar.husary')
            ]);
            const dataArabic = await resArabic.json();
            const dataTafsir = await resTafsir.json();
            const dataAudio = await resAudio.json();
            loadingText.style.display = 'none';
            renderSurah(dataArabic.data, dataTafsir.data, dataAudio.data);
        } catch (error) {
            loadingText.style.display = 'none';
            quranContainer.innerHTML = '<p style="color:red; text-align:center;">حدث خطأ أثناء جلب البيانات، يرجى المحاولة لاحقاً.</p>';
        }
    }
    function renderSurah(arabicData, tafsirData, audioData) {
        const totalAyahs = arabicData.ayahs.length;
        const surahName = arabicData.name;
        for (let i = 0; i < totalAyahs; i++) {
            const ayahArabic = arabicData.ayahs[i];
            const ayahTafsir = tafsirData.ayahs[i];
            const ayahAudio = audioData.ayahs[i];
            const card = document.createElement('div');
            card.className = 'verse-card';
            card.innerHTML = '<div class="verse-text">' + ayahArabic.text + ' <span class="verse-num">' + ayahArabic.numberInSurah + '</span></div><div class="tafsir-box"><div class="tafsir-title">التفسير الميسر:</div><div class="tafsir-text">' + ayahTafsir.text + '</div></div><button class="play-btn" onclick="playTrack(\'' + ayahAudio.audio + '\', \'' + surahName + ' - آية ' + ayahArabic.numberInSurah + '\')">🔊 استماع لصوت الشيخ الحصري</button>';
            quranContainer.appendChild(card);
        }
    }
    function playTrack(audioUrl, trackName) {
        currentTrackText.textContent = "جاري تشغيل: " + trackName;
        audioPlayer.src = audioUrl;
        audioPlayer.play();
    }
    window.onload = loadSurahList;
</script>
</body>
</html>
