<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的國學筆記：五行與乾坤</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        .wuxing-card { transition: all 0.3s ease; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased pb-12">

    <header class="bg-gradient-to-r from-amber-700 to-amber-900 text-white shadow-md sticky top-0 z-50">
        <div class="max-w-4xl mx-auto px-4 py-4 flex justify-between items-center">
            <h1 class="text-xl font-bold tracking-wider">☯️ 國學自修室</h1>
            <nav class="space-x-4 text-sm font-medium">
                <a href="#wuxing" class="hover:text-amber-200 transition">五行奧秘</a>
                <a href="#tiangan-dizhi" class="hover:text-amber-200 transition">天干地支</a>
            </nav>
        </div>
    </header>

    <main class="max-w-4xl mx-auto px-4 mt-8 space-y-12">

        <section class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100 text-center">
            <h2 class="text-2xl font-bold text-amber-800 mb-2">一陰一陽之謂道</h2>
            <p class="text-slate-600 max-w-md mx-auto text-sm leading-relaxed">
                這是我的國學學習秘密基地。從最基礎的五行生克、天干地支開始，層層遞進，探索古人的智慧宇宙。
            </p>
        </section>

        <section id="wuxing" class="space-y-6">
            <div class="border-l-4 border-amber-700 pl-3">
                <h3 class="text-xl font-bold text-slate-950">🪵 🔥 ⏳ 🪙 💧 五行生克</h3>
                <p class="text-xs text-slate-500 mt-1">點擊下方按鈕觀看各行特質</p>
            </div>

            <div class="grid grid-cols-5 gap-2 md:gap-4">
                <button onclick="switchWuxing('mu')" class="py-3 rounded-xl font-bold text-center bg-green-100 text-green-800 hover:bg-green-200 transition shadow-sm cursor-pointer">木</button>
                <button onclick="switchWuxing('huo')" class="py-3 rounded-xl font-bold text-center bg-red-100 text-red-800 hover:bg-red-200 transition shadow-sm cursor-pointer">火</button>
                <button onclick="switchWuxing('tu')" class="py-3 rounded-xl font-bold text-center bg-amber-100 text-amber-800 hover:bg-amber-200 transition shadow-sm cursor-pointer">土</button>
                <button onclick="switchWuxing('jin')" class="py-3 rounded-xl font-bold text-center bg-gray-200 text-gray-800 hover:bg-gray-300 transition shadow-sm cursor-pointer">金</button>
                <button onclick="switchWuxing('shui')" class="py-3 rounded-xl font-bold text-center bg-blue-100 text-blue-800 hover:bg-blue-200 transition shadow-sm cursor-pointer">水</button>
            </div>

            <div id="wuxing-display" class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100 min-h-[200px] flex flex-col justify-between">
                <div>
                    <div id="wx-title" class="text-2xl font-bold mb-2 text-slate-800">請選擇一個五行元素</div>
                    <div id="wx-phrase" class="text-amber-700 font-medium italic mb-4 text-sm"></div>
                    <p id="wx-desc" class="text-slate-600 text-sm leading-relaxed">點擊上方按鈕，查看古人如何理解自然界的五種基本能量及其延伸含意。</p>
                </div>
                <div id="wx-relations" class="mt-6 pt-4 border-t border-slate-100 grid grid-cols-2 gap-4 text-xs text-slate-500 hidden">
                    <div>🔄 <span class="font-semibold text-slate-700">相生：</span><span id="wx-shang"></span></div>
                    <div>⚡ <span class="font-semibold text-slate-700">相克：</span><span id="wx-ke"></span></div>
                </div>
            </div>
        </section>

        <section id="tiangan-dizhi" class="space-y-6">
            <div class="border-l-4 border-amber-700 pl-3">
                <h3 class="text-xl font-bold text-slate-950">📅 天干地支組合</h3>
                <p class="text-xs text-slate-500 mt-1">天干為主幹，地支為枝葉，組合出六十甲子</p>
            </div>

            <div class="grid md:grid-cols-2 gap-6">
                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                    <h4 class="font-bold text-lg text-slate-900 mb-3 flex items-center gap-2">
                        <span class="px-2 py-0.5 bg-amber-100 text-amber-800 text-xs rounded">天之氣</span> 十天干
                    </h4>
                    <p class="text-xs text-slate-500 mb-4">代表天時、精神層面的影響。</p>
                    <div class="flex flex-wrap gap-2">
                        <span class="px-3 py-1.5 bg-green-50 text-green-700 rounded-lg text-sm font-medium border border-green-200">甲 (陽木)</span>
                        <span class="px-3 py-1.5 bg-green-50 text-green-700 rounded-lg text-sm font-medium border border-green-200">乙 (陰木)</span>
                        <span class="px-3 py-1.5 bg-red-50 text-red-700 rounded-lg text-sm font-medium border border-red-200">丙 (陽火)</span>
                        <span class="px-3 py-1.5 bg-red-50 text-red-700 rounded-lg text-sm font-medium border border-red-200">丁 (陰火)</span>
                        <span class="px-3 py-1.5 bg-amber-50 text-amber-700 rounded-lg text-sm font-medium border border-amber-200">戊 (陽土)</span>
                        <span class="px-3 py-1.5 bg-amber-50 text-amber-700 rounded-lg text-sm font-medium border border-amber-200">己 (陰土)</span>
                        <span class="px-3 py-1.5 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium border border-gray-200">庚 (陽金)</span>
                        <span class="px-3 py-1.5 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium border border-gray-200">辛 (陰金)</span>
                        <span class="px-3 py-1.5 bg-blue-50 text-blue-700 rounded-lg text-sm font-medium border border-blue-200">壬 (陽水)</span>
                        <span class="px-3 py-1.5 bg-blue-50 text-blue-700 rounded-lg text-sm font-medium border border-blue-200">癸 (陰水)</span>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-100">
                    <h4 class="font-bold text-lg text-slate-900 mb-3 flex items-center gap-2">
                        <span class="px-2 py-0.5 bg-stone-200 text-stone-800 text-xs rounded">地之質</span> 十二地支
                    </h4>
                    <p class="text-xs text-slate-500 mb-4">對應十二生肖、月份與一日的時辰。</p>
                    <div class="grid grid-cols-3 gap-2">
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">子 🐭</div>
                            <div class="text-[10px] text-stone-400">23-01點 / 水</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">丑 🐮</div>
                            <div class="text-[10px] text-stone-400">01-03點 / 土</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">寅 🐯</div>
                            <div class="text-[10px] text-stone-400">03-05點 / 木</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">卯 🐰</div>
                            <div class="text-[10px] text-stone-400">05-07點 / 木</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">辰 🐲</div>
                            <div class="text-[10px] text-stone-400">07-09點 / 土</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">巳 🐍</div>
                            <div class="text-[10px] text-stone-400">09-11點 / 火</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">午 🐴</div>
                            <div class="text-[10px] text-stone-400">11-13點 / 火</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">未 🐑</div>
                            <div class="text-[10px] text-stone-400">13-15點 / 土</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">申 🐵</div>
                            <div class="text-[10px] text-stone-400">15-17點 / 金</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">酉 🐔</div>
                            <div class="text-[10px] text-stone-400">17-19點 / 金</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">戌 🐶</div>
                            <div class="text-[10px] text-stone-400">19-21點 / 土</div>
                        </div>
                        <div class="p-2 bg-stone-50 rounded-lg border border-stone-100 text-center">
                            <div class="font-bold text-sm text-stone-700">亥 🐷</div>
                            <div class="text-[10px] text-stone-400">21-23點 / 水</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <script>
        const wuxingData = {
            mu: {
                title: "🪵 木 —— 東方青龍 · 春季",
                phrase: "「木曰曲直」：具有生長、條達、舒暢的特性。",
                desc: "代表生命力的萌芽與舒展。在人體對應「肝膽」，在情志代表「怒」。木能生火，但會克土。",
                shang: "木生火（木材燃燒產生火）",
                ke: "木克土（樹木扎根破土）"
            },
            huo: {
                title: "🔥 火 —— 南方朱雀 · 夏季",
                phrase: "「火曰炎上」：具有發熱、溫暖、向上的特性。",
                desc: "代表事物的鼎盛與光明。在人體對應「心小腸」，在情志代表「喜」。火能生土，但會克金。",
                shang: "火生土（物體燃燒後化為灰燼泥土）",
                ke: "火克金（烈火能熔化金屬）"
            },
            tu: {
                title: "⏳ 土 —— 中央黃龍 · 長夏",
                phrase: "「土爰稼穡」：具有承載、受納、育化萬物的特性。",
                desc: "是萬物的母親，具備包容與轉化的力量。在人體對應「脾胃」，在情志代表「思」。土能生金，但會克水。",
                shang: "土生金（金屬礦物從泥土中孕育而出）",
                ke: "土克水（兵來將擋，水來土掩）"
            },
            jin: {
                title: "🪙 金 —— 西方白虎 · 秋季",
                phrase: "「金曰從革」：具有肅殺、變革、收斂的特性。",
                desc: "代表果實的成熟與規律的建立（剪裁）。在人體對應「肺大腸」，在情志代表「悲」。金能生水，但會克木。",
                shang: "金生水（金屬遇冷凝結出水珠，或金屬熔化為水狀）",
                ke: "金克木（金屬斧頭能砍伐樹木）"
            },
            shui: {
                title: "💧 水 —— 北方玄武 · 冬季",
                phrase: "「水曰潤下」：具有滋潤、向下、閉藏的特性。",
                desc: "代表萬物的潛藏與智慧的源泉。在人體對應「腎膀胱」，在情志代表「恐」。水能生木，但會克火。",
                shang: "水生木（水能滋潤樹木生長）",
                ke: "水克火（水能滅火）"
            }
        };

        function switchWuxing(key) {
            const data = wuxingData[key];
            document.getElementById('wx-title').innerText = data.title;
            document.getElementById('wx-phrase').innerText = data.phrase;
            document.getElementById('wx-desc').innerText = data.desc;
            document.getElementById('wx-shang').innerText = data.shang;
            document.getElementById('wx-ke').innerText = data.ke;
            
            // 顯示生克關係區塊
            document.getElementById('wx-relations').classList.remove('hidden');
        }
    </script>
</body>
</html>
