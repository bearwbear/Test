<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>亥亥的自學日記</title>
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
                <button onclick="selectWuxing('mu')" class="py-4 rounded-xl font-bold text-lg text-center bg-emerald-50 text-emerald-950 border border-emerald-2
