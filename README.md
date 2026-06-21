<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>亥亥的國學自修室</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@500;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Noto Serif TC', serif; }
        .hand-slot { transition: all 0.2s; }
        .hand-slot:hover { transform: scale(1.05); background-color: #fef3c7; }
    </style>
</head>
<body class="bg-stone-100 text-stone-800 antialiased pb-16">

    <header class="bg-gradient-to-r from-amber-900 to-stone-900 text-amber-100 shadow-md sticky top-0 z-50 border-b border-amber-700/30">
        <div class="max-w-5xl mx-auto px-4 py-4 flex justify-between items-center">
            <h1 class="text-xl font-bold tracking-widest flex items-center gap-2">☯️ 國學深修筆記</h1>
            <nav class="space-x-6 text-sm font-medium">
                <a href="#wuxing" class="hover:text-amber-400 transition">五行與運勢</a>
                <a href="#palm-chart" class="hover:text-amber-400 transition">地支掌訣</a>
                <a href="#tiangan" class="hover:text-amber-400 transition">天干地支</a>
            </nav>
        </div>
    </header>

    <main class="max-w-5xl mx-auto px-4 mt-8 space-y-12">

        <section class="bg-white p-8 rounded-2xl shadow-sm border border-stone-200/60 text-center relative overflow-hidden">
            <div class="absolute top-0 right-0 text-stone-100 text-9xl font-bold select-none translate-x-10 -translate-y-10">☯️</div>
            <h2 class="text-2xl font-bold text-amber-900 mb-3">天地氤氳，萬物化生</h2>
            <p class="text-stone-600 max-w-2xl mx-auto text-base leading-relaxed">
                 五行並非孤立的物質，而是宇宙間五種能量的流動與平衡。
                「生」為滋養發育，「剋」為制約規律。知五行、明運勢、調心性，方能順應天道。
            </p>
        </section>

        <section id="wuxing" class="space-y-6">
            <div class="border-l-4 border-amber-800 pl-3">
                <h3 class="text-2xl font-bold text-stone-900">🪵 🔥 ⏳ 🪙 💧 五行全息運勢</h3>
                <p class="text-sm text-stone-500 mt-1">點擊下方五行，解鎖命理運勢、人體中醫與心性調和</p>
            </div>

            <div class="grid grid-cols-5 gap-2 md:gap-4">
                <button onclick="selectWuxing('mu')" class="py-4 rounded-xl font-bold text-lg text-center bg-emerald-50 text-emerald-950 border border-emerald-200 hover:bg-emerald-100 transition shadow-sm cursor-pointer">木</button>
                <button onclick="selectWuxing('huo')" class="py-4 rounded-xl font-bold text-lg text-center bg-rose-50 text-rose-950 border border-rose-200 hover:bg-rose-100 transition shadow-sm cursor-pointer">火</button>
                <button onclick="selectWuxing('tu')" class="py-4 rounded-xl font-bold text-lg text-center bg-amber-50 text-amber-950 border border-amber-200 hover:bg-amber-100 transition shadow-sm cursor-pointer">土</button>
                <button onclick="selectWuxing('jin')" class="py-4 rounded-xl font-bold text-lg text-center bg-stone-200 text-stone-950 border border-stone-300 hover:bg-stone-300 transition shadow-sm cursor-pointer">金</button>
                <button onclick="selectWuxing('shui')" class="py-4 rounded-xl font-bold text-lg text-center bg-blue-50 text-blue-950 border border-blue-200 hover:bg-blue-100 transition shadow-sm cursor-pointer">水</button>
            </div>

            <div id="wuxing-card" class="bg-white p-8 rounded-2xl shadow-md border border-stone-200 min-h-[300px] transition-all duration-300">
                <div class="text-center py-12 text-stone-400" id="wuxing-placeholder">
                    <p class="text-lg">請點擊上方五行按鈕，開啟古人全息命理視野</p>
                </div>
                
                <div id="wuxing-content" class="hidden space-y-6">
                    <div class="flex flex-col md:flex-row md:items-center justify-between border-b border-stone-100 pb-4">
                        <div>
                            <h4 id="wx-name" class="text-3xl font-bold text-stone-900"></h4>
                            <p id="wx-nature" class="text-amber-800 font-medium mt-1"></p>
                        </div>
                        <div class="flex gap-4 mt-2 md:mt-0">
                            <span class="px-3 py-1 bg-stone-100 rounded-full text-sm" id="wx-season"></span>
                            <span class="px-3 py-1 bg-stone-100 rounded-full text-sm" id="wx-direction"></span>
                        </div>
                    </div>

                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="space-y-3">
                            <h5 class="font-bold text-amber-950 border-b pb-1">🔮 命理與人生運勢</h5>
                            <p id="wx-fortune" class="text-stone-600 text-sm leading-relaxed"></p>
                        </div>
                        <div class="space-y-3">
                            <h5 class="font-bold text-amber-950 border-b pb-1">🌿 中醫五臟與心性</h5>
                            <p id="wx-health" class="text-stone-600 text-sm leading-relaxed"></p>
                        </div>
                    </div>

                    <div class="bg-stone-50 p-4 rounded-xl grid grid-cols-2 gap-4 text-sm border border-stone-100">
                        <div>🔄 <span class="font-bold text-emerald-800">相生（滋養）：</span><span id="wx-birth" class="text-stone-600"></span></div>
                        <div>⚡ <span class="font-bold text-rose-800">相剋（制約）：</span><span id="wx-crush" class="text-stone-600"></span></div>
                    </div>
                </div>
            </div>
        </section>

        <section id="palm-chart" class="space-y-6">
            <div class="border-l-4 border-amber-800 pl-3">
                <h3 class="text-2xl font-bold text-stone-900">✋ 左手地支掌訣（掐指一算）</h3>
                <p class="text-sm text-stone-500 mt-1">古人將十二地支固定在左手關節上，順時針轉一圈即是宇宙循環</p>
            </div>

            <div class="grid md:grid-cols-12 gap-8 bg-white p-8 rounded-2xl shadow-sm border border-stone-200">
                <div class="md:col-span-5 flex flex-col items-center justify-center bg-stone-50 p-4 rounded-xl border border-stone-200/60">
                    <span class="text-xs text-stone-400 mb-4">模擬左手掌心朝己（點擊可查看說明）</span>
                    
                    <div class="grid grid-cols-4 gap-2 w-full max-w-[320px]">
                        <div onclick="showKey('巳')" class="hand-slot p-3 bg-rose-50 border border-rose-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-rose-700">巳 🐍</div><div class="text-[10px] text-stone-400">食指尖</div>
                        </div>
                        <div onclick="showKey('午')" class="hand-slot p-3 bg-rose-50 border border-rose-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-rose-700">午 🐴</div><div class="text-[10px] text-stone-400">中指尖</div>
                        </div>
                        <div onclick="showKey('未')" class="hand-slot p-3 bg-amber-50 border border-amber-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-amber-700">未 🐑</div><div class="text-[10px] text-stone-400">無名尖</div>
                        </div>
                        <div onclick="showKey('申')" class="hand-slot p-3 bg-stone-100 border border-stone-300 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-stone-700">申 🐵</div><div class="text-[10px] text-stone-400">小指尖</div>
                        </div>

                        <div onclick="showKey('辰')" class="hand-slot p-3 bg-amber-50 border border-amber-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-amber-700">辰 🐲</div><div class="text-[10px] text-stone-400">食指二</div>
                        </div>
                        <div class="p-3 bg-stone-200/30 rounded-lg text-center text-stone-400 text-xs flex items-center justify-center col-span-2 row-span-2 font-bold">
                            掌心<br>乾坤
                        </div>
                        <div onclick="showKey('酉')" class="hand-slot p-3 bg-stone-100 border border-stone-300 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-stone-700">酉 🐔</div><div class="text-[10px] text-stone-400">小指二</div>
                        </div>

                        <div onclick="showKey('寅')" class="hand-slot p-3 bg-emerald-50 border border-emerald-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-emerald-700">寅 🐯</div><div class="text-[10px] text-stone-400">食指三</div>
                        </div>
                        <div onclick="showKey('戌')" class="hand-slot p-3 bg-amber-50 border border-amber-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-amber-700">戌 🐶</div><div class="text-[10px] text-stone-400">小指三</div>
                        </div>

                        <div onclick="showKey('丑')" class="hand-slot p-3 bg-amber-50 border border-amber-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-amber-700">丑 🐮</div><div class="text-[10px] text-stone-400">食指根</div>
                        </div>
                        <div onclick="showKey('子')" class="hand-slot p-3 bg-blue-50 border border-blue-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-blue-700">子 🐭</div><div class="text-[10px] text-stone-400">中指根</div>
                        </div>
                        <div onclick="showKey('亥')" class="hand-slot p-3 bg-blue-50 border border-blue-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-blue-700">亥 🐷</div><div class="text-[10px] text-stone-400">無名根</div>
                        </div>
                        <div onclick="showKey('卯')" class="hand-slot p-3 bg-emerald-50 border border-emerald-200 rounded-lg text-center cursor-pointer">
                            <div class="font-bold text-emerald-700">卯 🐰</div><div class="text-[10px] text-stone-400">小指根</div>
                        </div>
                    </div>
                </div>

                <div class="md:col-span-7 space-y-4 flex flex-col justify-between">
                    <div class="bg-amber-50/60 p-5 rounded-xl border border-amber-200/50">
                        <h4 class="font-bold text-amber-900 mb-2 flex items-center gap-2">📜 地支記憶與生剋口訣</h4>
                        <ul class="space-y-2 text-sm text-stone-700 leading-relaxed">
                            <li>🎯 <strong>手排軌跡</strong>：從無名指根的「子」出發，沿著邊緣<strong>順時針</strong>繞一圈。</li>
                            <li>🤝 <strong>地支六合（橫向對稱）</strong>：掌圖左右相對即相合。
                                <br><span class="text-xs text-stone-500">子丑合土、寅亥合木、卯戌合火、辰酉合金、巳申合水、午未合土。</span>
                            </li>
                            <li>⚡ <strong>地支六衝（對角對線）</strong>：手掌上直線相對即相衝，代表變動不穩。
                                <br><span class="text-xs text-stone-500">子午相衝、丑未相衝、寅申相衝、卯酉相衝、辰戌相衝、巳亥相衝。</span>
                            </li>
                        </ul>
                    </div>

                    <div class="bg-stone-50 p-4 rounded-xl border border-stone-200 min-h-[90px]">
                        <div id="key-title" class="font-bold text-base text-stone-800">💡 點選左手關節位置</div>
                        <div id="key-desc" class="text-xs text-stone-500 mt-1">點擊左手掌圖中的地支，此處將顯示其時間、方位與五行含意。</div>
                    </div>
                </div>
            </div>
        </section>

        <section id="tiangan" class="space-y-6">
            <div class="border-l-4 border-amber-800 pl-3">
                <h3 class="text-2xl font-bold text-stone-900">📅 十天干意象</h3>
                <p class="text-sm text-stone-500 mt-1">天干主外、主精神。代表天時能量的展現。</p>
            </div>

            <div class="bg-white p-6 rounded-2xl shadow-sm border border-stone-200 grid md:grid-cols-5 gap-4">
                <div class="p-4 bg-emerald-50/40 rounded-xl border border-emerald-100">
                    <span class="text-xs font-bold text-emerald-800 block mb-2">🪵 東方木</span>
                    <div class="font-bold text-stone-800">甲木 <span class="text-xs text-stone-400">(陽大樹)</span></div>
                    <div class="font-bold text-stone-800 mt-1">乙木 <span class="text-xs text-stone-400">(陰花草)</span></div>
                </div>
                <div class="p-4 bg-rose-50/40 rounded-xl border border-rose-100">
                    <span class="text-xs font-bold text-rose-800 block mb-2">🔥 南方火</span>
                    <div class="font-bold text-stone-800">丙火 <span class="text-xs text-stone-400">(陽太陽)</span></div>
                    <div class="font-bold text-stone-800 mt-1">丁火 <span class="text-xs text-stone-400">(陰燈燭)</span></div>
                </div>
                <div class="p-4 bg-amber-50/40 rounded-xl border border-amber-100">
                    <span class="text-xs font-bold text-amber-800 block mb-2">⏳ 中央土</span>
                    <div class="font-bold text-stone-800">戊土 <span class="text-xs text-stone-400">(陽高山)</span></div>
                    <div class="font-bold text-stone-800 mt-1">己土 <span class="text-xs text-stone-400">(陰田園)</span></div>
                </div>
                <div class="p-4 bg-stone-100 rounded-xl border border-stone-200">
                    <span class="text-xs font-bold text-stone-600 block mb-2">🪙 西方金</span>
                    <div class="font-bold text-stone-800">庚金 <span class="text-xs text-stone-400">(陽刀劍)</span></div>
                    <div class="font-bold text-stone-800 mt-1">辛金 <span class="text-xs text-stone-400">(陰珠寶)</span></div>
                </div>
                <div class="p-4 bg-blue-50/40 rounded-xl border border-blue-100">
                    <span class="text-xs font-bold text-blue-800 block mb-2">💧 北方水</span>
                    <div class="font-bold text-stone-800">壬水 <span class="text-xs text-stone-400">(陽江河)</span></div>
                    <div class="font-bold text-stone-800 mt-1">癸水 <span class="text-xs text-stone-400">(陰雨露)</span></div>
                </div>
            </div>
        </section>

    </main>

    <script>
        // 五行詳盡資料（整合禪香不二深度解讀）
        const wuxingDatabase = {
            mu: {
                name: "🪵 木 —— 青龍之氣",
                nature: "「木曰曲直」：具有生長、條達、向上開拓的動力。",
                season: "🌸 春季 (正/二月)",
                direction: "🧭 東方",
                fortune: "在人生運勢中，木氣旺者仁慈、有惻隱之心，具備極強的創業與突破能力。但若木氣過旺，容易流於固執、剛愎自用；木氣衰弱則缺乏執行力、容易畏縮不前。運勢起伏如樹木遭遇四季風霜。",
                health: "對應人體【肝與膽】。主控筋骨與視力。情志上對應【怒】。長期壓力或暴怒容易導致肝氣鬱結。修行重在修「仁」，以寬容化解戾氣。",
                birth: "木生火 (燃木生火，傳遞光明)",
                crush: "木剋土 (樹根扎入土壤，破土而生)"
            },
            huo: {
                name: "🔥 火 —— 朱雀之光",
                nature: "「火曰炎上」：具有發熱、溫暖、散發、向上的特質。",
                season: "☀️ 夏季 (四/五月)",
                direction: "🧭 南方",
                fortune: "火主「禮」。火氣旺的人熱情豪爽、雄辯且有爆發力，人生運勢多在青年或中年期迎來高峰，絢麗奪目。然而火旺者缺乏耐心、性子急躁，易流於與人衝突；火衰則顯得冷淡、缺乏前進熱情。",
                health: "對應人體【心與小腸】。主控血液循環與神明。情志對應【喜】。過度激動（大喜）或焦慮易傷心神。修行重在修「禮」，以規律與內斂尋求心境平靜。",
                birth: "火生土 (萬物焚毀化為灰燼，回歸大地)",
                crush: "火剋金 (烈火紅爐，能熔鍊金屬器皿)"
            },
            tu: {
                name: "⏳ 土 —— 勾陳黃龍",
                nature: "「土爰稼穡」：具有承載、受納、孕育萬物的厚德。",
                season: "🍂 長夏 / 四季交界月",
                direction: "🧭 中央",
                fortune: "土主「信」。土氣深厚者踏實、包容、誠實穩重，是極佳的守成者與管理者，財運往往細水長流。但土過旺者容易流於死板、不願變革且過度保守；土衰者則缺乏原則、難以獲得他人信任。",
                health: "對應人體【脾與胃】。主控消化系統與肌肉力量。情志對應【思】。過度憂慮（思慮傷脾）會導致食慾不振與消化不良。修行重在修「信」，保持內心坦蕩與寬容。",
                birth: "土生金 (泥土深處孕育出璀璨礦石金屬)",
                crush: "土剋水 (兵來將擋，水來土掩，築堤防洪)"
            },
            jin: {
                name: "🪙 金 —— 白虎之變",
                nature: "「金曰從革」：具有肅殺、變革、收斂、裁切的決斷力。",
                season: "🍁 秋季 (七/八月)",
                direction: "🧭 西方",
                fortune: "金主「義」。金氣旺者黑白分明、具決斷力、仗義疏財，適合從事管理、法規或開拓型行業。但金過旺容易流於冷酷無情、好勇鬥狠；金衰則意志不堅、容易在關鍵時刻猶豫妥協。",
                health: "對應人體【肺與大腸】。主控呼吸、皮膚與免疫力。情志對應【悲】。過度悲傷易使肺氣受損。修行重在修「義」，在原則中保留一份慈悲與彈性。",
                birth: "金生水 (金屬遇冷凝結成水露，或熔化為水流)",
                crush: "金剋木 (鋼刀斧頭能修剪、砍伐草木)"
            },
            shui: {
                name: "💧 水 —— 玄武之智",
                nature: "「水曰潤下」：具有滋潤、向下、閉藏、智慧的特質。",
                season: "❄️ 冬季 (十/十一月)",
                direction: "🧭 北方",
                fortune: "水主「智」。水氣旺的人聰明絕頂、擅長謀略、適應力如水般能隨方就圓，人生多有奇謀與巧遇。然而水過旺容易流於漂泊不定、心機深沉、缺乏定性；水衰則思維僵化、缺乏遠見與變通智慧。",
                health: "對應人體【腎與膀胱】。主控骨骼、髓與先天精氣。情志對應【恐】。長期處於驚恐狀態極易傷腎氣。修行重在修「智」，讓心如止水，洞察萬物。",
                birth: "水生木 (雨露溪水滋潤樹木，生命得以繁衍)",
                crush: "水剋火 (清冷之水能澆滅炙熱烈火)"
            }
        };

        function selectWuxing(key) {
            document.getElementById('wuxing-placeholder').classList.add('hidden');
            const content = document.getElementById('wuxing-content');
            content.classList.remove('hidden');

            const data = wuxingDatabase[key];
            document.getElementById('wx-name').innerText = data.name;
            document.getElementById('wx-nature').innerText = data.nature;
            document.getElementById('wx-season').innerText = data.season;
            document.getElementById('wx-direction').innerText = data.direction;
            document.getElementById('wx-fortune').innerText = data.fortune;
            document.getElementById('wx-health').innerText = data.health;
            document.getElementById('wx-birth').innerText = data.birth;
            document.getElementById('wx-crush').innerText = data.crush;
        }

        // 地支手掌細節資料
        const palmDatabase = {
            '子': { title: "子時 (23:00 - 01:00) / 屬水 🐭", desc: "【無名指根】一天的開始，陰極生陽之時。對應正冬十一月。主冰冷、潛藏、智慧源頭。" },
            '丑': { title: "丑時 (01:00 - 03:00) / 屬土 🐮", desc: "【食指根部】黎明前的黑暗，四庫土之一。對應十二月。代表沉穩、勞碌、孕育生機。" },
            '寅': { title: "寅時 (03:00 - 05:00) / 屬木 🐯", desc: "【食指第三關節】三陽開泰，新生命破土而出。對應正月（春季開始）。主開拓、膽識。" },
            '辰': { title: "辰時 (07:00 - 09:00) / 屬土 🐲", desc: "【食指第二關節】群龍行雨，草木繁茂。四庫土之一。對應三月。主變幻莫測、包容力。" },
            '巳': { title: "巳時 (09:00 - 11:00) / 屬火 🐍", desc: "【食指尖端】陽氣鼎盛，臨近中午。對應四月。主熱情、思路敏捷、變化快。" },
            '午': { title: "午時 (11:00 - 13:00) / 屬火 🐴", desc: "【中指尖端】日正當中，陽極生陰。對應五月。主光明正大、奔放、禮節。" },
            '未': { title: "未時 (13:00 - 15:00) / 屬土 🐑", desc: "【無名指尖端】烈日西斜，萬物成熟。四庫土之一。對應六月。主溫和、含蓄、藝術天賦。" },
            '申': { title: "申時 (15:00 - 17:00) / 屬金 🐵", desc: "【小指尖端】夕陽金輝，秋氣漸濃。對應七月。主機智、靈活、帶有肅殺決斷力。" },
            '酉': { title: "酉時 (17:00 - 19:00) / 屬金 🐔", desc: "【小指第二關節】日落西山，成果收割。對應八月。主追求完美、講義氣、精準。" },
            '戌': { title: "戌時 (19:00 - 21:00) / 屬土 🐶", desc: "【小指第三關節】華燈初上，萬物棲息。四庫土之一。對應九月。主忠誠、防衛心強、責任感。" },
            '亥': { title: "亥時 (21:00 - 23:00) / 屬水 🐷", desc: "【小指根部】夜深人靜，天地歸於沉寂。對應十月。主溫柔、包容、內向、潛力巨大。" },
            '卯': { title: "卯時 (05:00 - 07:00) / 屬木 🐰", desc: "【中指根部上方/此處排列於右下】旭日東升，朝氣蓬勃。對應二月。主溫和、人緣好、直覺敏銳。" }
        };

        function showKey(key) {
            const data = palmDatabase[key];
            if (data) {
                document.getElementById('key-title').innerHTML = `📍 ${data.title}`;
                document.getElementById('key-desc').innerHTML = data.desc;
            }
        }
    </script>
</body>
</html>
