# Sturdy-wadsle
```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bespoke Nail Studio & Admin System</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Hind+Siliguri:wght@300;400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        nude: {
                            50: '#FAF7F5',
                            100: '#F5EFEB',
                            200: '#EADCD3',
                            300: '#DEC5B5',
                            400: '#CEAA95',
                            500: '#BC8E75',
                            600: '#A47058',
                        },
                        rose: {
                            gold: '#B38B6D',
                            accent: '#E8C5B8',
                            soft: '#FFF5F2'
                        },
                        studio: {
                            dark: '#2A2421',
                            charcoal: '#3D3531',
                            muted: '#7A6E67'
                        }
                    },
                    fontFamily: {
                        serif: ['"Cormorant Garamond"', 'serif'],
                        sans: ['"Plus Jakarta Sans"', '"Hind Siliguri"', 'sans-serif'],
                        bangla: ['"Hind Siliguri"', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        .glass-card {
            background: rgba(255, 255, 255, 0.82);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(222, 197, 181, 0.35);
        }
        .text-gold-gradient {
            background: linear-gradient(135deg, #A47058 0%, #D4AF37 50%, #BC8E75 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .btn-rose-gold {
            background: linear-gradient(135deg, #C59B80 0%, #A47058 100%);
            transition: all 0.3s ease;
        }
        .btn-rose-gold:hover {
            background: linear-gradient(135deg, #B3896E 0%, #8E5D46 100%);
            box-shadow: 0 10px 20px -5px rgba(164, 112, 88, 0.4);
        }
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #FAF7F5;
        }
        ::-webkit-scrollbar-thumb {
            background: #CEAA95;
            border-radius: 4px;
        }
    </style>
</head>
<body class="bg-nude-50 text-studio-dark font-sans antialiased selection:bg-rose-accent selection:text-studio-dark">

    <!-- Top Admin Bar for Studio Owner -->
    <div class="bg-studio-dark text-nude-200 text-xs py-2 px-4 flex items-center justify-between border-b border-white/10 sticky top-0 z-50">
        <div class="flex items-center gap-3">
            <span class="bg-rose-accent/20 text-rose-accent font-semibold px-2 py-0.5 rounded text-[10px] uppercase tracking-wider">Owner Portal</span>
            <span class="hidden sm:inline text-nude-300">Customize prices in BDT (৳), shapes, services & studio info live.</span>
        </div>
        <div class="flex items-center gap-2">
            <button onclick="toggleNumeralFormat()" class="bg-white/10 hover:bg-white/20 text-white px-2.5 py-1 rounded text-[11px] transition flex items-center gap-1">
                <i class="fa-solid fa-language"></i> <span id="numeral-btn-text">Bangla Numerals: ON</span>
            </button>
            <button onclick="openAdminModal()" class="bg-rose-gold text-white font-semibold px-3 py-1 rounded text-[11px] hover:opacity-90 transition flex items-center gap-1">
                <i class="fa-solid fa-sliders"></i> Edit Studio & Prices
            </button>
            <button onclick="openHostingGuideModal()" class="bg-emerald-700 hover:bg-emerald-800 text-white font-semibold px-3 py-1 rounded text-[11px] transition flex items-center gap-1">
                <i class="fa-solid fa-cloud-arrow-up"></i> How to Own Free
            </button>
        </div>
    </div>

    <!-- Navigation Header -->
    <header class="bg-white/80 backdrop-blur-md border-b border-nude-200 sticky top-[33px] z-40">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <a href="#" class="flex items-center gap-2 group">
                <span i
