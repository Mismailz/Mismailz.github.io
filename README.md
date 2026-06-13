<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>حصن المسلم الإلكتروني - Mismailz</title>
    <!-- استدعاء الخطوط -->
    <link rel="preconnect" href="https://googleapis.com">
    <link rel="preconnect" href="https://gstatic.com" crossorigin>
    <link href="https://googleapis.com/css2?family=Amiri&family=Cairo:wght@400;700&display=swap" rel="stylesheet">
    <!-- ربط ملف التنسيق الخارجي -->
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>حصن المسلم الإلكتروني الذكي 📿</h1>
        <h2>جميع الأذكار والأدعية اليومية مع العداد الصوتي والتفاعلي الذكي</h2>
        
        <div class="nav-links">
            <a href="index.html">📖 العودة للمصحف الشريف</a>
            <a href="hesn.html" class="active-link">📿 حصن المسلم</a>
        </div>

        <div class="instruction-note">
            💡 <strong>إرشادات الاستخدام:</strong><br>
            • اختر تصنيف الأذكار الذي تريده من القائمة المنسدلة بالأسفل.<br>
            • اضغط على زر <strong>🔊 استمع للذكر</strong> لنطق الذكر كاملاً عبر المحرك الصوتي لجهازك.<br>
            • اضغط على زر <strong>التكرار</strong> لحساب مرات القراءة حتى يكتمل العدد المطلوب.
        </div>

        <select id="categorySelect" onchange="loadCategory(this.value)">
            <option value="">اختر باباً من أبواب الأذكار...</option>
        </select>

        <div id="azkarContainer"></div>

        <footer>جميع الحقوق محفوظة للموقع - تم التطوير لصالح حساب Mismailz</footer>
    </div>

    <!-- ربط ملف البرمجة الخارجي -->
    <script src="script.js"></script>
</body>
</html>
body { 
    font-family: 'Amiri', serif; 
    background-color: #f4f1ea; 
    color: #2b2b2b; 
    margin: 0; 
    padding: 20px; 
    display: flex; 
    flex-direction: column; 
    align-items: center; 
}
.container { 
    max-width: 850px; 
    width: 100%; 
    background: #ffffff; 
    padding: 35px; 
    border-radius: 16px; 
    box-shadow: 0 10px 30px rgba(0,0,0,0.05); 
    border: 1px solid #dfd8ca; 
    box-sizing: border-box; 
}
h1 { 
    font-family: 'Cairo', sans-serif; 
    color: #1e3f20; 
    text-align: center; 
    margin-bottom: 5px; 
    font-size: 26px; 
}
h2 { 
    font-family: 'Cairo', sans-serif; 
    color: #5c6b5e; 
    text-align: center; 
    margin-top: 0; 
    margin-bottom: 30px; 
    font-size: 16px; 
    font-weight: 400; 
}
.nav-links { 
    display: flex; 
    justify-content: center; 
    gap: 15px; 
    margin-bottom: 25px; 
    font-family: 'Cairo', sans-serif; 
}
.nav-links a { 
    color: #1e3f20; 
    text-decoration: none; 
    font-weight: bold; 
    padding: 8px 16px; 
    border: 1px solid #1e3f20; 
    border-radius: 8px; 
    transition: all 0.3s; 
}
.nav-links a:hover { 
    background-color: #1e3f20; 
    color: white; 
}
.nav-links .active-link {
    background-color: #1e3f20; 
    color: white;
}
.instruction-note { 
    background-color: #eef7f4; 
    border-right: 5px solid #1e3f20; 
    padding: 12px; 
    border-radius: 6px; 
    font-family: 'Cairo', sans-serif; 
    font-size: 14px; 
    color: #1e3f20; 
    margin-bottom: 20px; 
    line-height: 1.6; 
}
select { 
    width: 100%; 
    padding: 14px; 
    font-family: 'Cairo', sans-serif; 
    font-size: 16px; 
    border-radius: 10px; 
    border: 2px solid #dfd8ca; 
    margin-bottom: 25px; 
    background-color: #faf9f6; 
    color: #1e3f20; 
    cursor: pointer; 
    outline: none; 
}
select:focus { 
    border-color: #1e3f20; 
    box-shadow: 0 0 5px rgba(30, 63, 32, 0.1); 
}
.zkr-card { 
    background: #faf9f6; 
    border: 1px solid #dfd8ca; 
    border-radius: 12px; 
    padding: 25px; 
    margin-bottom: 20px; 
    box-shadow: 0 4px 10px rgba(0,0,0,0.02); 
    transition: all 0.3s; 
    position: relative; 
}
.zkr-text { 
    font-size: 24px; 
    line-height: 2.1; 
    text-align: justify; 
    margin-bottom: 15px; 
    color: #1e3f20; 
}
.zkr-control { 
    display: flex; 
    justify-content: space-between; 
    align-items: center; 
    font-family: 'Cairo', sans-serif; 
    border-top: 1px dashed #dfd8ca; 
    padding-top: 15px; 
    margin-top: 15px; 
    flex-wrap: wrap; 
    gap: 10px; 
}
.zkr-note { 
    font-size: 14px; 
    color: #666; 
    max-width: 60%; 
}
.counter-btn { 
    background-color: #1e3f20; 
    color: white; 
    border: none; 
    padding: 10px 20px; 
    border-radius: 8px; 
    font-size: 16px; 
    font-weight: bold; 
    cursor: pointer; 
    transition: background-color 0.2s; 
    display: flex; 
    align-items: center; 
    gap: 10px; 
}
.counter-btn:disabled { 
    background-color: #b3c2b5; 
    color: #666; 
    cursor: not-allowed; 
}
.audio-btn { 
    background-color: #dfd8ca; 
    color: #1e3f20; 
    border: none; 
    padding: 10px 15px; 
    border-radius: 8px; 
    font-size: 14px; 
    font-weight: bold; 
    cursor: pointer; 
    transition: all 0.2s; 
}
.audio-btn:hover { 
    background-color: #1e3f20; 
    color: white; 
}
.flex-buttons { 
    display: flex; 
    align-items: center; 
    gap: 10px; 
}
footer { 
    text-align: center; 
    margin-top: 40px; 
    font-family: 'Cairo', sans-serif; 
    font-size: 14px; 
    color: #777; 
    border-top: 1px solid #dfd8ca; 
    padding-top: 15px; 
}
// قاعدة بيانات الأذكار
const azkarData = {
    "أذكار الصباح": [
        { "zkr": "أَصْبَحْنَا وَأَصْبَحَ الْمُلْكُ لِلَّهِ، وَالْحَمْدُ لِلَّهِ، لَا إِلَهَ إِلَّا اللهُ وَحْدَهُ لَا شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.", "count": 1, "description": "رواه مسلم" },
        { "zkr": "اللّهُ لاَ إِلَـهَ إِلاَّ هُوَ الْحَيُّ الْقَيُّومُ لاَ تَأْخُذُهُ سِنَةٌ وَلاَ نَوْمٌ لَّهُ مَا فِي السَّمَاوَاتِ وَمَا فِي الأَرْضِ مَن ذَا الَّذِي يَشْفَعُ عِنْدَهُ إِلاَّ بِإِذْنِهِ يَعْلَمُ مَا بَيْنَ أَيْدِيهِمْ وَمَا خَلْفَهُمْ وَلاَ يُحِيطُونَ بِشَيْءٍ مِّنْ عِلْمِهِ إِلاَّ بِمَا شَاء وَسِعَ كُرْسِيُّهُ السَّمَاوَاتِ وَالأَرْضَ وَلاَ يَؤُودُهُ حِفْظُهُمَا وَهُوَ الْعَلِيُّ الْعَظِيمُ.", "count": 1, "description": "آية الكرسي - من قالها حين يصبح أجير من الجن حتى يمسي" },
        { "zkr": "قُلْ هُوَ اللَّهُ أَحَدٌ، قُلْ أَعُوذُ بِرَبِّ الْفَلَقِ، قُلْ أَعُوذُ بِرَبِّ النَّاسِ", "count": 3, "description": "تكفيه من كل شيء" },
        { "zkr": "بِسْمِ اللَّهِ الَّذِي لَا يَضُرُّ مَعَ اسْمِهِ شَيْءٌ فِي الْأَرْضِ وَلَا فِي السَّمَاءِ وَهُوَ السَّمِيعُ الْعَلِيمُ.", "count": 3, "description": "لم يضره شيء في ذلك اليوم" },
        { "zkr": "سُبْحَانَ اللهِ وَبِحَمْدِهِ.", "count": 100, "description": "حُطّت خطاياه وإن كانت مثل زبد البحر" }
    ],
    "أذكار المساء": [
        { "zkr": "أَمْسَيْنَا وَأَمْسَى الْمُلْكُ لِلَّهِ، وَالْحَمْدُ لِلَّهِ، لَا إِلَهَ إِلَّا اللهُ وَحْدَهُ لَا شَرِيكَ لَهُ، لَهُ الْمُلْكُ وَلَهُ الْحَمْدُ وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ.", "count": 1, "description": "رواه مسلم" },
        { "zkr": "بِسْمِ اللَّهِ الَّذِي لَا يَضُرُّ مَعَ اسْمِهِ شَيْءٌ فِي الْأَرْضِ وَلَا فِي السَّمَاءِ وَهُوَ السَّمِيعُ الْعَلِيمُ.", "count": 3, "description": "لم تضره فجأة بلاء" },
        { "zkr": "أَعُوذُ بِكَلِمَاتِ اللهِ التَّامَّاتِ مِنْ شَرِّ مَا خَلَقَ.", "count": 3, "description": "لم تضره لدغة عقرب في تلك الليلة" }
    ],
    "أذكار النوم": [
        { "zkr": "بِاسْمِكَ رَبِّي وَضَعْتُ جَنْبِي، وَبِكَ أَرْفَعُهُ، فَإِنْ أَمْسَكْتَ نَفْسِي فَارْحَمْهَا، وَإِنْ أَرْسَلْتَهَا فَاحْفَظْهَا بِمَا تَحْفَظُ بِهِ عِبَادَكَ الصَّالِحِينَ.", "count": 1, "description": "رواه البخاري ومسلم" },
        { "zkr": "اللَّهُمَّ بِاسْمِكَ أَمُوتُ وَأَحْيَا.", "count": 1, "description": "رواه البخاري" }
    ]
};

// تهيئة ملء القائمة المنسدلة عند فتح الصفحة
function init() {
    const select = document.getElementById('categorySelect');
    const categories = Object.keys(azkarData);
    
    categories.forEach(category => {
        let option = document.createElement('option');
        option.value = category; 
        option.textContent = category;
        select.appendChild(option);
    });
}

// عرض الأذكار بناءً على الخيار المحدد
function loadCategory(categoryName) {
    const container = document.getElementById('azkarContainer');
    container.innerHTML = "";
    if (!categoryName || !azkarData[categoryName]) return;

    const items = azkarData[categoryName];
    items.forEach((item, index) => {
        const card = document.createElement('div'); card.className = 'zkr-card';
        const textDiv = document.createElement('div'); textDiv.className = 'zkr-text';
        textDiv.textContent = item.zkr; card.appendChild(textDiv);

        const controlDiv = document.createElement('div'); controlDiv.className = 'zkr-control';
        const noteDiv = document.createElement('div'); noteDiv.className = 'zkr-note';
        noteDiv.textContent = item.description || "حصن المسلم"; controlDiv.appendChild(noteDiv);

        const flexButtons = document.createElement('div'); flexButtons.className = 'flex-buttons';
        const audioBtn = document.createElement('button'); audioBtn.className = 'audio-btn';
        audioBtn.innerHTML = "🔊 استمع للذكر"; audioBtn.onclick = () => speakZkr(item.zkr);
        flexButtons.appendChild(audioBtn);

        const countRequired = parseInt(item.count) || 1; let currentCount = 0;
        const counterBtn = document.createElement('button'); counterBtn.className = 'counter-btn';
        counterBtn.innerHTML = `التكرار: ${currentCount} / ${countRequired}`;
        
        counterBtn.onclick = () => {
            currentCount++;
            if (currentCount <= countRequired) {
                counterBtn.innerHTML = `التكرار: ${currentCount} / ${countRequired}`;
                if (navigator.vibrate) navigator.vibrate(50);
                if (currentCount === countRequired) {
                    counterBtn.disabled = true; counterBtn.innerHTML = "✓ تم الانتهاء";
                    counterBtn.style.backgroundColor = "#2c5234"; card.style.opacity = "0.6";
                }
            }
        };
        flexButtons.appendChild(counterBtn); controlDiv.appendChild(flexButtons);
        card.appendChild(controlDiv); container.appendChild(card);
    });
}

// تشغيل ميزة النطق الصوتي للذكر
function speakZkr(text) {
    if ('speechSynthesis' in window) {
        window.speechSynthesis.cancel();
        const cleanText = text.replace(/[()]/g, "").trim();
        const utterance = new SpeechSynthesisUtterance(cleanText);
        utterance.lang = 'ar-SA'; utterance.rate = 0.88;
        window.speechSynthesis.speak(utterance);
    } else {
        alert("خاصية النطق الصوتي غير مدعومة في متصفحك الحالي.");
    }
}

// تفعيل السكريبت عند تحميل كامل عناصر الـ DOM
document.addEventListener("DOMContentLoaded", init);
