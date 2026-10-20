```html

<!DOCTYPE html>  <html lang="vi">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">  
    <title>Chúc Mừng Ngày 20/10 - Siêu Rực Rỡ & Lung Linh 💖</title>  
    <!-- Tailwind CSS CDN -->  
    <script src="https://cdn.tailwindcss.com"></script>  
    <!-- FontAwesome icons -->  
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">  
    <!-- Google Fonts -->  
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Nunito:wght@400;700;800;900&family=Pacifico&family=Quicksand:wght@600;700&display=swap" rel="stylesheet">  
    <!-- Canvas Confetti JS -->  
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>  
    <!-- Vanilla Tilt JS cho hiệu ứng nghiêng 3D -->  
    <script src="https://cdnjs.cloudflare.com/ajax/libs/vanilla-tilt/1.8.1/vanilla-tilt.min.js"></script>  <style>  
    * {  
        box-sizing: border-box;  
        user-select: none;  
        -webkit-tap-highlight-color: transparent;  
    }  

    body {  
        font-family: 'Quicksand', 'Nunito', sans-serif;  
        background: #0B0813; /* Bầu trời đêm sâu thẳm */  
        min-height: 100vh;  
        overflow-x: hidden;  
        position: relative;  
        color: #fff;  
    }  

    .font-cursive { font-family: 'Dancing Script', cursive; }  
    .font-pacifico { font-family: 'Pacifico', cursive; }  

    /* Canvas Nền Pháo Hoa & Cánh Hoa Rơi & Con Trỏ Chuột */  
    #bgCanvas, #fgCanvas {  
        position: fixed;  
        top: 0;  
        left: 0;  
        width: 100%;  
        height: 100%;  
        pointer-events: none;  
    }  
    #bgCanvas { z-index: 1; }  
    #fgCanvas { z-index: 30; }  

    /* Bầu trời đêm sao nhấp nháy */  
    .stars-bg {  
        position: fixed;  
        top: 0;  
        left: 0;  
        width: 100%;  
        height: 100%;  
        background: radial-gradient(ellipse at bottom, #1B142A 0%, #090A0F 100%);  
        z-index: 0;  
    }  

    /* Glassmorphism Card Đỉnh Cao */  
    .glass-card-ultra {  
        background: rgba(255, 255, 255, 0.08);  
        backdrop-filter: blur(20px);  
        -webkit-backdrop-filter: blur(20px);  
        border: 2px solid rgba(255, 182, 218, 0.4);  
        box-shadow: 0 0 50px rgba(236, 72, 153, 0.35),  
                    0 0 100px rgba(168, 85, 247, 0.2),  
                    inset 0 0 20px rgba(255, 255, 255, 0.2);  
        border-radius: 32px;  
    }  

    /* Viền Phát Sáng Neon Bảy Màu */  
    @keyframes rainbowGlow {  
        0% { border-color: rgba(244, 114, 182, 0.8); box-shadow: 0 0 30px rgba(244, 114, 182, 0.6); }  
        33% { border-color: rgba(192, 132, 252, 0.8); box-shadow: 0 0 35px rgba(192, 132, 252, 0.7); }  
        66% { border-color: rgba(251, 191, 36, 0.8); box-shadow: 0 0 35px rgba(251, 191, 36, 0.6); }  
        100% { border-color: rgba(244, 114, 182, 0.8); box-shadow: 0 0 30px rgba(244, 114, 182, 0.6); }  
    }  

    .neon-border {  
        animation: rainbowGlow 4s infinite ease-in-out;  
    }  

    /* Chữ Phát Sáng Neon */  
    .neon-text-pink {  
        text-shadow: 0 0 10px rgba(244, 114, 182, 0.8),  
                     0 0 20px rgba(244, 114, 182, 0.6),  
                     0 0 30px rgba(236, 72, 153, 0.4);  
    }  

    .neon-text-gold {  
        text-shadow: 0 0 10px rgba(253, 224, 71, 0.8),  
                     0 0 20px rgba(234, 179, 8, 0.6);  
    }  

    /* Floating Animation */  
    @keyframes bounceSlow {  
        0%, 100% { transform: translateY(0px) rotate(0deg); }  
        50% { transform: translateY(-15px) rotate(4deg); }  
    }  
    @keyframes floatRotate {  
        0%, 100% { transform: translateY(0px) rotate(-3deg) scale(1); }  
        50% { transform: translateY(-20px) rotate(5deg) scale(1.05); }  
    }  
    .float-anim { animation: bounceSlow 3.5s infinite ease-in-out; }  
    .float-anim-2 { animation: floatRotate 4.2s infinite ease-in-out; }  

    /* Hộp quà xuất hiện bất ngờ */  
    #giftModal {  
        transition: all 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);  
    }
  #giftModal.opened {  
        opacity: 0;  
        pointer-events: none;  
        transform: scale(1.5);  
    }  

    /* Hộp quà nhún nhảy */  
    @keyframes giftPulse {  
        0%, 100% { transform: scale(1) rotate(0deg); }  
        25% { transform: scale(1.08) rotate(-4deg); }  
        75% { transform: scale(1.08) rotate(4deg); }  
    }  
    .gift-box-anim {  
        animation: giftPulse 1.5s infinite ease-in-out;  
    }  

    /* Tùy chỉnh Typing Cursor */  
    .typing-cursor::after {  
        content: '|';  
        animation: blink 0.7s infinite;  
    }  
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }  

    /* CD Disc Rotation */  
  @keyframes spinDisc {  
        0% { transform: rotate(0deg); }  
        100% { transform: rotate(360deg); }  
    }  
    .spinning-cd {  
        animation: spinDisc 6s linear infinite;  
    }  
    .paused-cd {  
        animation-play-state: paused;  
    }  

    /* Shiny Button Effect */  
    .btn-shiny {  
        position: relative;  
        overflow: hidden;  
    }  
    .btn-shiny::after {  
        content: '';  
        position: absolute;  
        top: -50%;  
        left: -50%;  
        width: 200%;  
        height: 200%;  
        background: linear-gradient(60deg, transparent, rgba(255,255,255,0.4), transparent);  
        transform: rotate(30deg);  
        transition: 0.8s;  
    }  
    .btn-shiny:hover::after {  
        left: 100%;  
    }  
</style>

</head>  
<body class="flex flex-col items-center justify-center min-h-screen p-3 sm:p-6 select-none relative overflow-x-hidden">  <!-- Bầu trời đêm sao -->  
<div class="stars-bg"></div>  

<!-- Canvas đằng sau: Pháo hoa + Mưa cánh hoa & lá -->  
<canvas id="bgCanvas"></canvas>  
  
<!-- Canvas đằng trước: Vệt sáng con trỏ chuột -->  
<canvas id="fgCanvas"></canvas>  

<!-- Nút điều khiển nhạc & pháo hoa khẩn cấp góc phải -->  
<div class="fixed top-4 right-4 z-50 flex items-center gap-3">  
    <!-- CD Player Widget -->  
    <div id="musicToggle" class="cursor-pointer bg-white/10 backdrop-blur-md hover:bg-white/20 p-2 rounded-full border border-pink-400/40 shadow-2xl flex items-center gap-2 transition-all group">  
        <div id="cdDisc" class="w-10 h-10 rounded-full bg-gradient-to-tr from-pink-500 via-purple-600 to-yellow-400 flex items-center justify-center shadow-md spinning-cd paused-cd">  
            <div class="w-3 h-3 bg-black rounded-full border border-white"></div>  
        </div>  
        <div class="hidden sm:block pr-2 text-xs font-bold text-pink-200">  
            <span id="musicStatus">Nhạc: Tắt</span>  
        </div>  
    </div>  

    <button id="fireworksBtn" class="btn-shiny bg-gradient-to-r from-pink-500 via-purple-500 to-amber-400 hover:scale-105 active:scale-95 text-white px-4 py-2.5 rounded-full shadow-lg border border-pink-300/50 flex items-center gap-2 font-bold text-xs sm:text-sm">  
        <i class="fas fa-fireworks text-yellow-300 text-lg"></i>  
        <span class="hidden sm:inline">Pháo Hoa Trời</span>  
    </button>  
</div>  

<!-- ==================== MÀN HÌNH MỞ HỘP QUÀ BẤT NGỜ ==================== -->  
<div id="giftModal" class="fixed inset-0 z-50 flex flex-col items-center justify-center p-4 bg-black/80 backdrop-blur-xl">  
    <div class="text-center max-w-md mx-auto">  
        <div class="inline-block relative mb-6 cursor-pointer group" onclick="openGift()">  
            <div class="text-8xl sm:text-9xl gift-box-anim transition-transform filter drop-shadow-[0_0_35px_rgba(244,114,182,0.8)]">  
                🎁  
            </div>  
            <div class="absolute -top-3 -right-3 bg-yellow-400 text-purple-950 font-black text-xs px-3 py-1 rounded-full shadow-lg uppercase tracking-wider animate-bounce">  
                Chạm Để Mở!  
            </div>  
        </div>  
        <h2 class="text-2xl sm:text-4xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-pink-300 via-purple-300 to-yellow-200 font-pacifico mb-3">  
            Bạn Có 1 Món Quà Đặc Biệt!  
        </h2>  
        <p class="text-pink-200/90 text-sm sm:text-base font-semibold mb-8">  
            Nhấn vào Hộp Quà lấp lánh để khám phá bí mật chúc mừng ngày 20/10 🎉  
        </p>  
        <button onclick="openGift()" class="btn-shiny bg-gradient-to-r from-pink-500 to-purple-600 hover:from-pink-600 hover:to-purple-700 text-white font-extrabold px-8 py-4 rounded-full text-lg shadow-[0_0_30px_rgba(236,72,153,0.6)] transform hover:scale-105 transition-all">  
            ✨ MỞ QUÀ NGAY ✨  
        </button>  
    </div>  
</div>  

<!-- ==================== CONTAINER CHÍNH THIỆP 3D ==================== -->  
<main id="mainContent" class="relative z-10 w-full max-w-2xl my-auto opacity-0 transform scale-90 transition-all duration-1000">  
      
    <!-- Chibi Sticker Trái (Ayato Genshin Cute Style) -->  
    <div class="absolute -top-12 -left-6 sm:-left-12 z-20 w-28 sm:w-36 float-anim pointer-events-none filter drop-shadow-[0_10px_15px_rgba(0,0,0,0.5)]">  
        <svg viewBox="0 0 200 200" class="w-full h-full">  
            <circle cx="100" cy="100" r="75" fill="#C7D2FE" opacity="0.3"/>  
            <!-- Hair & Head -->  
            <path d="M50 100 C50 40, 150 40, 150 100 C150 120, 140 150, 100 150 C60 150, 50 120, 50 100 Z" fill="#818CF8"/>  
            <circle cx="100" cy="105" r="45" fill="#FEF3C7"/>  
            <!-- Bangs -->  
            <path d="M60 80 Q100 110 140 80 Q120 60 100 60 Q80 60 60 80 Z" fill="#6366F1"/>  
            <!-- Eyes -->  
            <ellipse cx="82" cy="102" rx="7" ry="10" fill="#1E1B4B"/>  
            <ellipse cx="118" cy="102" rx="7" ry="10" fill="#1E1B4B"/>  
            <circle cx="80" cy="99" r="3" fill="#FFF"/>  
            <circle cx="116" cy="99" r="3" fill="#FFF"/>  
            <!-- Blush -->  
            <ellipse cx="73" cy="112" rx="6" ry="3" fill="#F472B6" opacity="0.7"/>  
            <ellipse cx="127" cy="112" rx="6" ry="3" fill="#F472B6" opacity="0.7"/>  
            <!-- Smile -->  
            <path d="M93 115 Q100 122 107 115" stroke="#4338CA" stroke-width="3" fill="none" stroke-linecap="round"/>  
            <!-- Flower bouquet -->  
            <path d="M85 140 L115 140 L100 175 Z" fill="#93C5FD"/>  
            <circle cx="92" cy="138" r="10" fill="#F472B6"/>  
            <circle cx="108" cy="138" r="10" fill="#C084FC"/>  
            <circle cx="100" cy="130" r="11" fill="#FDE047"/>  
        </svg>  
    </div>  

    <!-- Chibi Sticker Phải (Hu Tao / Anime Chibi) -->  
    <div class="absolute -bottom-8 -right-4 sm:-right-10 z-20 w-24 sm:w-32 float-anim-2 pointer-events-none filter drop-shadow-[0_10px_15px_rgba(0,0,0,0.5)]">  
        <div class="bg-white/10 backdrop-blur-md p-3 rounded-3xl border border-pink-300/40 shadow-2xl text-center transform rotate-6">  
            <span class="text-5xl sm:text-6xl block">👻</span>  
            <span class="text-[10px] font-black text-pink-300 tracking-wider uppercase block mt-1">Super Cute</span>  
        </div>  
    </div>  

    <!-- Khung Thiệp 3D Tilt Glassmorphism Ultra -->  
    <div id="tiltCard" class="glass-card-ultra neon-border p-6 sm:p-10 text-center relative overflow-hidden" data-tilt data-tilt-max="7" data-tilt-speed="400" data-tilt-glare data-tilt-max-glare="0.2">  
          
        <!-- Hoa trang trí 4 góc -->  
        <div class="absolute top-2 left-2 text-pink-300/30 text-5xl pointer-events-none animate-spin" style="animation-duration: 20s;">🌸</div>  
        <div class="absolute bottom-2 right-2 text-purple-300/30 text-5xl pointer-events-none animate-spin" style="animation-duration: 25s;">🌺</div>  

        <!-- Header Badge -->  
        <div class="mb-4">  
            <span class="bg-gradient-to-r from-pink-500/30 via-purple-500/30 to-pink-500/30 text-pink-200 border border-pink-400/50 text-xs sm:text-sm font-black px-5 py-2 rounded-full uppercase tracking-widest inline-block shadow-[0_0_15px_rgba(236,72,153,0.3)]">  
                ✨ 20 / 10 / 2026 ✨  
            </span>  
        </div>  

        <!-- Tiêu đề lớn phát sáng -->  
        <h1 class="text-3xl sm:text-5xl font-black text-transparent bg-clip-text bg-gradient-to-r from-pink-300 via-rose-200 to-yellow-200 font-pacifico leading-relaxed neon-text-pink mb-4">  
            Hôm nay là ngày 20/10  
        </h1>  

        <!-- Khung Lời Chúc Gõ Chữ / Glowing Text -->  
        <div class="space-y-4 text-pink-100 text-sm sm:text-lg font-bold leading-relaxed my-6 text-left sm:text-center bg-black/30 backdrop-blur-md p-5 sm:p-7 rounded-2xl border border-pink-500/30 shadow-inner">  
                      <div class="space-y-4 text-pink-100 text-sm sm:text-lg font-bold leading-relaxed my-6 text-left sm:text-center bg-black/30 backdrop-blur-md p-5 sm:p-7 rounded-2xl border border-pink-500/30 shadow-inner">  
              
            <p class="transition-all hover:text-yellow-200">  
                Chúc tất cả bạn một ngày lễ trọn vẹn, đầy ý nghĩa với những kỷ niệm đẹp nhất.   
                <span class="inline-block animate-bounce text-pink-400">💖</span>  
            </p>  

            <p class="transition-all hover:text-yellow-200">  
                Chúc bạn luôn vui vẻ, gặp nhiều may mắn, chúc bạn mỗi ngày đều cười tươi.   
                <span class="inline-block hover:rotate-180 transition-transform duration-500 text-yellow-300">🎁</span>  
            </p>  

            <p class="transition-all hover:text-yellow-200">  
                Chúc bạn ngày càng xinh đẹp, giỏi giang, chúc bạn cuộc sống đong đầy bao nhiêu hạnh phúc đều là của bạn   
                <span class="inline-block animate-pulse text-rose-400">💕</span>  
            </p>  

            <p class="transition-all hover:t<!-- Dòng nhắn nhủ hài hước từ ảnh -->  
        <div class="mt-4 bg-gradient-to-r from-pink-500/20 via-purple-500/20 to-pink-500/20 p-4 sm:p-5 rounded-2xl border border-pink-400/40 backdrop-blur-sm">  
            <p class="font-extrabold text-yellow-200 text-sm sm:text-base leading-relaxed italic">  
                "Tôi xin ko tặng hoa vì ko thể tặng hoa cho 1 bông hoa, bn thích gì gửi tui, tui gửi link cho chứ tôi ko mua 🤣🤣"  
            </p>  
        </div>  

        <!-- Nút tương tác siêu vui -->  
        <div class="mt-8 flex flex-wrap justify-center gap-3 sm:gap-4">  
            <button onclick="triggerMegaFireworks()" class="btn-shiny bg-gradient-to-r from-pink-500 via-rose-500 to-purple-600 hover:scale-105 active:scale-95 text-white font-extrabold px-6 py-3.5 rounded-full shadow-[0_0_20px_rgba(244,114,182,0.6)] text-xs sm:text-sm flex items-center gap-2">  
                <i class="fas fa-heart text-rose-300"></i>  
                <span>Thả Tim Ngợp Trời</span>  
            </button>  

            <button onclick="openGiftLinkModal()" class="btn-shiny bg-gradient-to-r from-amber-400 via-orange-500 to-pink-500 hover:scale-105 active:scale-95 text-slate-950 font-black px-6 py-3.5 rounded-full shadow-[0_0_20px_rgba(251,191,36,0.6)] text-xs sm:text-sm flex items-center gap-2">  
                <i class="fas fa-link text-slate-950"></i>  
                <span>Gửi Link Món Quà Bạn Thích 🎁</span>  
            </button>  
        </div>  

    </div>  

    <p class="text-center text-xs text-pink-300/70 mt-6 font-bold tracking-wide">  
        💖 Chúc Các Bạn Nữ Luôn Rạng Rỡ & Hạnh Phúc! 💖  
    </p>  
</main>  

<!-- ==================== POPUP GỬI LINK QUÀ HÀI HƯỚC ==================== -->  
<div id="giftLinkModal" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 bg-black/80 backdrop-blur-md">  
    <div class="glass-card-ultra neon-border p-6 sm:p-8 max-w-md w-full text-center relative transform transition-all scale-95 opacity-0" id="giftLinkModalCard">  
        <button onclick="closeGiftLinkModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white text-xl">  
            <i class="fas fa-times"></i>  
        </button>  
        <div class="text-5xl mb-3">🛍️</div>  
        <h3 class="text-2xl font-black text-yellow-300 mb-2 font-pacifico">Gửi Link Món Quà Bạn Thích</h3>  
        <p class="text-xs sm:text-sm text-pink-200/90 mb-4 font-semibold">  
            Dán link Shopee, Lazada, Tiki hoặc món quà ước nguyện vào đây nè! (Gửi xong tui xem... chứ tui hông mua đâu 🤪)  
        </p>  
          
        <div class="space-y-3 mb-5">  
            <input type="text" id="giftUrlInput" placeholder="https://shopee.vn/mon-qua-xinh-dep..." class="w-full bg-black/50 border border-pink-400/50 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-yellow-400 transition-colors placeholder-gray-500">  
            <textarea id="giftNoteInput" placeholder="Lời nhắn kèm theo (VD: Mua nhanh nha bạn tui ơi)..." rows="2" class="w-full bg-black/50 border border-pink-400/50 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-yellow-400 transition-colors placeholder-gray-500 resize-none"></textarea>  
        </div>  

        <button onclick="submitGiftLink()" class="btn-shiny w-full bg-gradient-to-r from-pink-500 to-purple-600 hover:from-pink-600 hover:to-purple-700 text-white font-black py-3 rounded-xl shadow-lg text-sm uppercase tracking-wider">  
            🚀 GỬI LINK NGAY & LUÔN  
        </button>  
    </div>  
</div>  

<!-- Audio Nhạc Nền Cute Chill -->  
<audio id="bgMusic" loop preload="auto">  
    <source src="https://assets.mixkit.co/music/preview/mixkit-beautiful-dream-493.mp3" type="audio/mpeg">  
</audio>  

<!-- ==================== JAVASCRIPT XỬ LÝ
LÝ SIÊU HIỆU ỨNG ==================== -->  
<script>  
    /* 1. KHỞI TẠO CANVAS BACKGROUND & FOREGROUND */  
    const bgCanvas = document.getElementById('bgCanvas');  
    const bgCtx = bgCanvas.getContext('2d');  
    const fgCanvas = document.getElementById('fgCanvas');  
    const fgCtx = fgCanvas.getContext('2');
    let width = bgCanvas.width = fgCanvas.width = window.innerWidth;
        let height = bgCanvas.height = fgCanvas.height = window.innerHeight;

        window.addEventListener('resize', () => {
            width = bgCanvas.width = fgCanvas.width = window.innerWidth;
            height = bgCanvas.height = fgCanvas.height = window.innerHeight;
        });

        /* 2. HIỆU ỨNG CÁNH HOA & TRÁI TIM RƠI TRÊN CANVAS NỀN */
        const petals = [];
        const petalColors = ['#F472B6', '#EC4899', '#F43F5E', '#C084FC', '#FDE047', '#38BDF8'];
        const petalSymbols = ['🌸', '🌺', '✨', '💖', '💐', '🌹'];

        class Petal {
            constructor() {
                this.reset();
            }
            reset() {
                this.x = Math.random() * width;
                this.y = -20 - Math.random() * 100;
                this.size = Math.random() * 14 + 10;
                this.speedY = Math.random() * 1.5 + 0.8;
                this.speedX = Math.random() * 1 - 0.5;
                this.symbol = petalSymbols[Math.floor(Math.random() * petalSymbols.length)];
                this.opacity = Math.random() * 0.7 + 0.3;
                this.rotation = Math.random() * 360;
                this.rotSpeed = (Math.random() - 0.5) * 2;
            }
            update() {
                this.y += this.speedY;
                this.x += Math.sin(this.y * 0.01) + this.speedX;
                this.rotation += this.rotSpeed;
                if (this.y > height + 30) {
                    this.reset();
                }
            }
            draw() {
                bgCtx.save();
                bgCtx.translate(this.x, this.y);
                bgCtx.rotate((this.rotation * Math.PI) / 180);
                bgCtx.globalAlpha = this.opacity;
                bgCtx.font = `${this.size}px sans-serif`;
                bgCtx.textAlign = 'center';
                bgCtx.textBaseline = 'middle';
                bgCtx.fillText(this.symbol, 0, 0);
                bgCtx.restore();
            }
        }

        for (let i = 0; i < 35; i++) {
            petals.push(new Petal());
        }

        /* 3. PHÁO HOA TỰ ĐỘNG VÀ BẮN KHỦNG */
        const fireworks = [];
this.distanceTraveled = 0;
                this.angle = Math.atan2(targetY - startY, targetX - startX);
                this.speed = 8;
                this.friction = 0.99;
                this.hue = Math.floor(Math.random() * 360);
            }
            update(index) {
                const vx = Math.cos(this.angle) * this.speed;
                const vy = Math.sin(this.angle) * this.speed;
(this.distanceTraveled < 10 || this.y <= this.targetY) {
                    createParticles(this.targetX, this.targetY, this.hue);
                    fireworks.splice(index, 1);
                } else {
                    this.x += vx;
                    this.y += vy;
                }
            }
            draw() {
                bgCtx.beginPath();
                bgCtx.arc(this.x, this.y, 3, 0, Math.PI * 2);
                bgCtx.fillStyle = `hsl(${this.hue}, 100%, 60%)`;
                bgCtx.fill();
            }
        }

        class Particle {
            constructor(x, y, hue) {
                this.x = x;
                this.y = y;
                this.hue = hue;
                this.angle = Math.random() * Math.PI * 2;
                this.speed = Math.random() * 6 + 1;
                this.friction = 0.95;
                this.gravity = 0.15;
                this.alpha = 1;
                this.decay = Math.random() * 0.02 + 0.015;
            }
            update(index) {
                this.speed *= this.friction;
                this.x += Math.cos(this.angle) * this.speed;
                this.y += Math.sin(this.angle) * this.speed + this.gravity;
                this.alpha -= this.decay;
                if (this.alpha <= 0) {
                    particles.splice(index, 1);
                }
            }
            draw() {
                bgCtx.save();
                bgCtx.globalAlpha = this.alpha;
                bgCtx.beginPath();
                bgCtx.arc(this.x, this.y, 2.5, 0, Math.PI * 2);
                bgCtx.fillStyle = `hsl(${this.hue}, 100%, 65%)`;
                bgCtx.shadowBlur = 10;
                bgCtx.shadowColor = `hsl(${this.hue}, 100%, 50%)`;
                bgCtx.fill();
                bgCtx.restore();
            }
        }

        function createParticles(x, y, hue) {
            const count = 40;
            for (let i = 0; i < count; i++) {
                particles.push(new Particle(x, y, hue));
            }
        }

        function launchRandomFirework() {
            const startX = width / 2 + (Math.random() - 0.5) * (width * 0.6);
            const startY = height;
            const targetX = Math.random() * width;
            const targetY = Math.random() * (height * 0.5);
            fireworks.push(new Firework(startX, startY, targetX, targetY));
        }
 /* 4. VỆT SÁNG TRÁI TIM THEO CON TRỎ CHUỘT / TOUCH */
        const cursorTrails = [];
        function addCursorTrail(x, y) {
            cursorTrails.push({
                x: x,
                y: y,
                size: Math.random() * 12 + 8,
                alpha: 1,
                color: `hsl(${Math.random() * 60 + 320}, 100%, 70%)`
            });
        }

        window.addEventListener('mousemove', (e) => addCursorTrail(e.clientX, e.clientY));
        window.addEventListener('touchmove', (e) => {
            if (e.touches.length > 0) {
                addCursorTrail(e.touches[0].clientX, e.touches[0].clientY);
            }
        });

        /* 5. LOOP ANIMATION CHÍNH */
        function animate() {
            bgCtx.clearRect(0, 0, width, height);

            // Cập nhật Cánh hoa
            petals.forEach(petal => {
                petal.update();
                petal.draw();
            });

            // Cập nhật Pháo hoa
            fireworks.forEach((fw, i) => {
                fw.update(i);
                fw.draw();
            });

            particles.forEach((p, i) => {
                p.update(i);
                p.draw();
            });

            // Bắn pháo ngẫu nhiên nhẹ nhàng
            if (Math.random() < 0.03) {
                launchRandomFirework();
            }

        const particles = [];

        class Firework {
            constructor(startX, startY, targetX, targetY) {
                this.x = startX;
                this.y = startY;
                this.targetX = targetX;
                this.targetY = targetY;
                this.distanceToTarget = Math.hypot(targetX - startX, targetY - startY);
    // Cập nhật Con trỏ chuột trên fgCanvas
            fgCtx.clearRect(0, 0, width, height);
            cursorTrails.forEach((ct, i) => {
                ct.alpha -= 0.03;
                ct.size *= 0.96;
                if (ct.alpha <= 0) {
                    cursorTrails.splice(i, 1);
                } else {
                    fgCtx.save();
                    fgCtx.globalAlpha = ct.alpha;
                    fgCtx.font = `${ct.size}px sans-serif`;
                    fgCtx.fillStyle = ct.color;
                    fgCtx.fillText('💖', ct.x, ct.y);
                    fgCtx.restore();
                }
            });

            requestAnimationFrame(animate);
        }

        /* 6. LOGIC MỞ HỘP QUÀ & PHÁT NHẠC */
        let isMusicPlaying = false;
        const bgMusic = document.getElementById('bgMusic');
        const cdDisc = document.getElementById('cdDisc');
        const musicStatus = document.getElementById('musicStatus');

        function toggleMusic() {
            if (isMusicPlaying) {
                bgMusic.pause();
                cdDisc.classList.add('paused-cd');
                musicStatus.innerText = 'Nhạc: Tắt';
                isMusicPlaying = false;
            } else {
bgMusic.play().then(() => {
                    cdDisc.classList.remove('paused-cd');
                    musicStatus.innerText = 'Nhạc: Bật 🎵';
                    isMusicPlaying = true;
                }).catch(() => {
                    showToast("Vui lòng chạm tương tác để bật nhạc nha! ✨");
                });
            }
        }

        function openGift() {
            const giftModal = document.getElementById('giftModal');
            const mainContent = document.getElementById('mainContent');

            giftModal.classList.add('opened');

            // Bật nhạc tự động
            if (!isMusicPlaying) {
                toggleMusic();
            }

            // Nổ confetti rực rỡ
            confetti({
                particleCount: 120,
                spread: 100,
                origin: { y: 0.6 }
            });

            // Mega fireworks
setTimeout(triggerMegaFireworks, 300);

            // Hiện thiệp chính
            setTimeout(() => {
                giftModal.style.display = 'none';
                mainContent.classList.remove('opacity-0', 'scale-90');
                mainContent.classList.add('opacity-100', 'scale-100');
            }, 600);
        }

        function triggerMegaFireworks() {
            confetti({
                particleCount: 80,
                angle: 60,
                spread: 70,
                origin: { x: 0 }
            });
            confetti({
                particleCount: 80,
                angle: 120,
                spread: 70,
                origin: { x: 1 }
            });

            for (let i = 0; i < 8; i++) {
                setTimeout(launchRandomFirework, i * 150);
            }
        }

        /* 7. POPUP GỬI LINK QUÀ HÀI HƯỚC */
        function openGiftLinkModal() {
            const modal = document.getElementById('giftLinkModal');
            const card = document.getElementById('giftLinkModalCard');
            modal.classList.remove('hidden');
            setTimeout(() => {
                card.classList.remove('scale-95', 'opacity-0');
                card.classList.add('scale-100', 'opacity-100');
            }, 10);
        }

        function closeGiftLinkModal() {
            const modal = document.getElementById('giftLinkModal');
            const card = document.getElementById('giftLinkModalCard');
            card.classList.remove('scale-100', 'opacity-100');
            card.classList.add('scale-95', 'opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 200);
        }

        function submitGiftLink() {
            const giftUrl = document.getElementById('giftUrlInput').value.trim();
            if (!giftUrl) {
                showToast("Nhập bừa cái link gì đó đi bạn tui ơi 🤪!");
                return;
            }

            closeGiftLinkModal();
            triggerMegaFireworks();

            setTimeout(() => {
                showToast("Cảm ơn bạn đã gửi link! Tui đã nhận và... cất vào góc tủ chứ không mua đâu 🤪🤣");
                document.getElementById('giftUrlInput').value = '';
                document.getElementById('giftNoteInput').value = '';
            }, 300);
        }

        /* 8. CUSTOM TOAST NOTIFICATION */
        function showToast(msg) {
            const toast = document.getElementById('toast');
            const toastMessage = document.getElementById('toastMessage');
            toastMessage.innerText = msg;
/ Khởi tạo VanillaTilt cho Card Thiệp
            if (typeof VanillaTilt !== 'undefined') {
                VanillaTilt.init(document.querySelectorAll("#tiltCard"), {
                    max: 8,
                    speed: 400,
                    glare: true,
                    "max-glare": 0.2,
                });
            }
        };
    </script>
</body>
</html>
```                
    
            toast.classList.remove('hidden');
            setTimeout(() => {
                toast.classList.add('hidden');
            }, 4000);
        }

        /* 9. KHỞI CHẠY LHI NỀN LOAD XONG */
        window.onload = function() {
            
