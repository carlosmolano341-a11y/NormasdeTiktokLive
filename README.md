<!DOCTYPE html>
<html lang="es" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TikTok LIVE Shield Pro | Auditoría Pre/Post LIVE & Defensa del Creador</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter & Plus Jakarta Sans -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Plus+Jakarta+Sans:wght@600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                    colors: {
                        ttDark: '#0b0c10',
                        ttCard: '#12151e',
                        ttBorder: '#1f2433',
                        ttCyan: '#00f2fe',
                        ttPink: '#fe0979',
                        ttRed: '#ff0050',
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #0b0c10;
            color: #f3f4f6;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }
        /* Efectos Neón estilo TikTok LIVE Studio */
        .tt-gradient-text {
            background: linear-gradient(90deg, #00f2fe 0%, #ffffff 50%, #ff0050 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .tt-btn-primary {
            background: linear-gradient(135deg, #ff0050 0%, #fe0979 100%);
            box-shadow: 0 0 20px rgba(255, 0, 80, 0.35);
            transition: all 0.2s ease;
        }
        .tt-btn-primary:hover {
            transform: translateY(-1px);
            box-shadow: 0 0 28px rgba(0, 242, 254, 0.5), 0 0 20px rgba(255, 0, 80, 0.5);
        }
        .tt-btn-cyan {
            background: linear-gradient(135deg, #00f2fe 0%, #0284c7 100%);
            color: #061018;
            box-shadow: 0 0 18px rgba(0, 242, 254, 0.3);
            transition: all 0.2s ease;
        }
        .tt-btn-cyan:hover {
            transform: translateY(-1px);
            box-shadow: 0 0 25px rgba(0, 242, 254, 0.55);
        }
        .tt-card {
            background: rgba(18, 21, 30, 0.92);
            border: 1px solid rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(12px);
        }
        .tt-card-cyan {
            background: linear-gradient(180deg, rgba(0, 242, 254, 0.07) 0%, rgba(18, 21, 30, 0.95) 100%);
            border: 1px solid rgba(0, 242, 254, 0.3);
        }
        .tt-card-pink {
            background: linear-gradient(180deg, rgba(255, 0, 80, 0.08) 0%, rgba(18, 21, 30, 0.95) 100%);
            border: 1px solid rgba(255, 0, 80, 0.35);
        }
        .tab-active {
            background: linear-gradient(135deg, rgba(0, 242, 254, 0.16) 0%, rgba(255, 0, 80, 0.16) 100%);
            border-color: #00f2fe !important;
            color: #ffffff !important;
            box-shadow: 0 0 16px rgba(0, 242, 254, 0.2);
        }
        /* Scrollbar personalizada */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0b0c10;
        }
        ::-webkit-scrollbar-thumb {
            background: #262c3d;
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00f2fe;
        }
        @keyframes pulseGlow {
            0%, 100% { box-shadow: 0 0 15px rgba(255, 0, 80, 0.35); }
            50% { box-shadow: 0 0 28px rgba(0, 242, 254, 0.55); }
        }
        .animate-glow {
            animation: pulseGlow 3s infinite;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col selection:bg-ttCyan selection:text-black">

    <!-- NOTIFICACIÓN TOAST FLOTANTE (SIN USAR ALERT) -->
    <div id="toastContainer" class="fixed bottom-5 right-5 z-50 flex flex-col gap-2 max-w-sm w-full pointer-events-none px-4 sm:px-0"></div>

    <!-- BANNER SUPERIOR DE PROTOCOLO OBLIGATORIO DE AGENCIA -->
    <div class="bg-gradient-to-r from-[#0e1726] via-[#1a0b1e] to-[#0e1726] border-b border-ttCyan/30 px-4 py-2.5 text-xs sm:text-sm">
        <div class="max-w-7xl mx-auto flex flex-wrap items-center justify-between gap-2">
            <div class="flex items-center gap-2.5">
                <span class="inline-flex items-center justify-center px-2 py-0.5 rounded-full text-[11px] font-extrabold bg-ttRed text-white uppercase tracking-wider animate-pulse">
                    <i class="fa-solid fa-shield-halved mr-1"></i> Regla de Oro
                </span>
                <p class="text-gray-200 font-medium">
                    <strong class="text-ttCyan">1° APELA siempre en la app.</strong> Si TikTok rechaza tu apelación pero estás <strong class="text-white underline decoration-ttPink">100% seguro de que fue injusto</strong>, pídenos ayuda para escalarlo con un <strong class="text-ttCyan">Manager Oficial de TikTok</strong>.
                </p>
            </div>
            <div class="flex flex-wrap items-center gap-2 ml-auto">
                <button onclick="openManagerModal()" class="px-3 py-1.5 rounded-lg bg-ttPink/20 hover:bg-ttPink/30 border border-ttPink/50 text-white font-semibold text-xs flex items-center gap-1.5 transition">
                    <i class="fa-solid fa-headset text-ttCyan"></i> Escalar a Manager TikTok
                </button>
            </div>
        </div>
    </div>

    <!-- ENCABEZado PRINCIPAL -->
    <header class="pt-6 pb-4 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto w-full">
        <div class="flex flex-col lg:flex-row lg:items-center lg:justify-between gap-4">
            <div class="flex items-start sm:items-center gap-4">
                <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-ttCyan via-black to-ttRed p-0.5 shrink-0 shadow-lg shadow-ttCyan/20">
                    <div class="w-full h-full bg-[#0b0c10] rounded-[14px] flex items-center justify-center">
                        <i class="fa-brands fa-tiktok text-2xl tt-gradient-text"></i>
                    </div>
                </div>
                <div>
                    <div class="flex flex-wrap items-center gap-2">
                        <span class="text-[11px] font-bold uppercase tracking-widest px-2.5 py-0.5 rounded-full bg-ttCyan/15 text-ttCyan border border-ttCyan/30">
                            Sistema Inteligente IA + Visión
                        </span>
                        <span class="text-[11px] font-bold uppercase tracking-widest px-2.5 py-0.5 rounded-full bg-emerald-500/15 text-emerald-400 border border-emerald-500/30">
                            Actualización Puntuación 100 Pts
                        </span>
                    </div>
                    <h1 class="text-2xl sm:text-3xl lg:text-4xl font-extrabold font-display tracking-tight mt-1">
                        Centro de Auditoría y Defensa <span class="tt-gradient-text">TikTok LIVE</span>
                    </h1>
                    <p class="text-gray-400 text-xs sm:text-sm mt-0.5">
                        Previene sanciones antes de transmitir, audita pantallazos en vivo, protege el <strong class="text-amber-400">20% de tus regalos</strong> y verifica quién tiene la razón: <strong class="text-white">¿Tú o TikTok?</strong>
                    </p>
                </div>
            </div>

            <!-- TARJETAS RÁPIDAS DE DIFERENCIACIÓN CRÍTICA -->
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5 lg:w-[440px] shrink-0">
                <div class="tt-card rounded-xl p-3 border-l-4 border-l-ttCyan">
                    <div class="flex items-center justify-between">
                        <span class="text-[11px] font-bold uppercase text-ttCyan">¿Dónde sale la infracción?</span>
                        <i class="fa-solid fa-mobile-screen-button text-ttCyan"></i>
                    </div>
                    <p class="text-xs text-gray-300 mt-1 leading-snug">
                        Una sanción real sale <strong class="text-white">A MITAD DE PANTALLA</strong> (pop-up), <strong class="text-rose-400">NUNCA en comentarios</strong> del chat.
                    </p>
                </div>
                <div class="tt-card rounded-xl p-3 border-l-4 border-l-amber-500">
                    <div class="flex items-center justify-between">
                        <span class="text-[11px] font-bold uppercase text-amber-400">Alerta 20% Regalos</span>
                        <i class="fa-solid fa-Gifts text-amber-400"></i>
                    </div>
                    <p class="text-xs text-gray-300 mt-1 leading-snug">
                        Diferencia <strong class="text-white">baja de visibilidad</strong> vs sanción dura (<strong class="text-amber-300">-20% diamantes</strong> o bloqueo 3-7 días).
                    </p>
                </div>
            </div>
        </div>

        <!-- NAVEGACIÓN DE MÓDULOS PRINCIPALES -->
        <nav class="mt-6 grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-2.5" aria-label="Módulos del Sistema">
            <button onclick="switchTab('prelive')" id="tab-prelive" class="tab-btn tab-active flex items-center gap-2.5 p-3 rounded-xl border border-white/10 bg-ttCard text-left transition hover:border-ttCyan/50">
                <div class="w-9 h-9 rounded-lg bg-ttCyan/15 text-ttCyan flex items-center justify-center shrink-0">
                    <i class="fa-solid fa-shield-cat text-base"></i>
                </div>
                <div class="overflow-hidden">
                    <div class="text-[10px] font-bold uppercase tracking-wider text-ttCyan">1. El Antes</div>
                    <div class="text-xs sm:text-sm font-bold text-white truncate">Auditoría Pre-LIVE</div>
                </div>
            </button>

            <button onclick="switchTab('postlive')" id="tab-postlive" class="tab-btn flex items-center gap-2.5 p-3 rounded-xl border border-white/10 bg-ttCard text-left transition hover:border-ttCyan/50 text-gray-300">
                <div class="w-9 h-9 rounded-lg bg-ttPink/15 text-ttPink flex items-center justify-center shrink-0">
                    <i class="fa-solid fa-scale-balanced text-base"></i>
                </div>
                <div class="overflow-hidden">
                    <div class="text-[10px] font-bold uppercase tracking-wider text-ttPink">2. El Después</div>
                    <div class="text-xs sm:text-sm font-bold text-white truncate">¿Tú o TikTok? (Juez)</div>
                </div>
            </button>

            <button onclick="switchTab('reputation')" id="tab-reputation" class="tab-btn flex items-center gap-2.5 p-3 rounded-xl border border-white/10 bg-ttCard text-left transition hover:border-ttCyan/50 text-gray-300">
                <div class="w-9 h-9 rounded-lg bg-emerald-500/15 text-emerald-400 flex items-center justify-center shrink-0">
                    <i class="fa-solid fa-gauge-high text-base"></i>
                </div>
                <div class="overflow-hidden">
                    <div class="text-[10px] font-bold uppercase tracking-wider text-emerald-400">3. Puntuación 100</div>
                    <div class="text-xs sm:text-sm font-bold text-white truncate">Reputación LIVE</div>
                </div>
            </button>

            <button onclick="switchTab('consultant')" id="tab-consultant" class="tab-btn flex items-center gap-2.5 p-3 rounded-xl border border-white/10 bg-ttCard text-left transition hover:border-ttCyan/50 text-gray-300">
                <div class="w-9 h-9 rounded-lg bg-amber-500/15 text-amber-400 flex items-center justify-center shrink-0">
                    <i class="fa-solid fa-robot text-base"></i>
                </div>
                <div class="overflow-hidden">
                    <div class="text-[10px] font-bold uppercase tracking-wider text-amber-400">4. Dudas 24/7</div>
                    <div class="text-xs sm:text-sm font-bold text-white truncate">Consultor & Diccionario</div>
                </div>
            </button>

            <button onclick="switchTab('guide')" id="tab-guide" class="tab-btn col-span-2 sm:col-span-1 flex items-center gap-2.5 p-3 rounded-xl border border-white/10 bg-ttCard text-left transition hover:border-ttCyan/50 text-gray-300">
                <div class="w-9 h-9 rounded-lg bg-purple-500/15 text-purple-400 flex items-center justify-center shrink-0">
                    <i class="fa-solid fa-book-open-reader text-base"></i>
                </div>
                <div class="overflow-hidden">
                    <div class="text-[10px] font-bold uppercase tracking-wider text-purple-400">5. Guía Visual</div>
                    <div class="text-xs sm:text-sm font-bold text-white truncate">Niveles y Reglas</div>
                </div>
            </button>
        </nav>
    </header>

    <!-- CONTENIDO PRINCIPAL -->
    <main class="flex-1 max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-4 space-y-8">

        <!-- ===================================================================== -->
        <!-- MÓDULO 1: AUDITORÍA PRE-LIVE ("EL ANTES" + ESCÁNER PANTALLA/VESTIMENTA) -->
        <!-- ===================================================================== -->
        <section id="section-prelive" class="tab-section space-y-6">
            <!-- Banner Explicativo del Módulo 1 -->
            <div class="tt-card-cyan rounded-2xl p-4 sm:p-5 flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                <div class="space-y-1">
                    <div class="inline-flex items-center gap-2 text-ttCyan font-bold text-xs uppercase tracking-wider">
                        <i class="fa-solid fa-bolt"></i> Prevención Total Antes de Transmitir
                    </div>
                    <h2 class="text-lg sm:text-xl font-bold text-white">
                        Escáner Pre-LIVE: Audita tu Dinámica, Retos PK, Palabras y Pantalla
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-300">
                        Describe lo que planeas hacer o <strong class="text-white">toma un pantallazo / sube una foto</strong> de tu escenario y vestimenta. El sistema detecta al instante si corres riesgo de que <strong class="text-amber-400">TikTok te quite el 20% de tus regalos</strong> o bloquee tu LIVE.
                    </p>
                </div>
                <div class="flex flex-wrap gap-2 shrink-0">
                    <span class="px-3 py-1.5 rounded-xl bg-black/50 border border-white/10 text-xs text-gray-300 flex items-center gap-1.5">
                        <i class="fa-solid fa-camera text-ttCyan"></i> Detecta Vestimenta y Objetos
                    </span>
                    <span class="px-3 py-1.5 rounded-xl bg-black/50 border border-white/10 text-xs text-gray-300 flex items-center gap-1.5">
                        <i class="fa-solid fa-percent text-amber-400"></i> Calcula Riesgo -20% Regalos
                    </span>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                <!-- Columna Izquierda: Entradas del Creador (7 cols) -->
                <div class="lg:col-span-7 space-y-5">

                    <!-- Paso 1: Zona de Cumplimiento (Checklist Rápido basado en la Foto 1) -->
                    <div class="tt-card rounded-2xl p-5 space-y-4">
                        <div class="flex items-center justify-between border-b border-white/10 pb-3">
                            <div>
                                <h3 class="text-sm sm:text-base font-bold text-white flex items-center gap-2">
                                    <span class="w-6 h-6 rounded-full bg-ttCyan text-black font-extrabold text-xs flex items-center justify-center">1</span>
                                    Zona de Cumplimiento (Marca si hay alguno presente)
                                </h3>
                                <p class="text-xs text-gray-400 mt-0.5">Basado en la Guía Oficial de Seguridad de TikTok LIVE</p>
                            </div>
                            <button onclick="clearPreLiveChecklist()" class="text-xs text-ttCyan hover:underline">Limpiar selección</button>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5" id="preLiveChecklist">
                            <label class="flex items-start gap-3 p-3 rounded-xl bg-black/40 border border-white/10 hover:border-ttPink/50 cursor-pointer transition">
                                <input type="checkbox" value="Humo, cigarro o vapeo visible (incluso apagado)" class="pre-check mt-1 w-4 h-4 accent-ttPink rounded">
                                <div class="text-xs">
                                    <div class="font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-smoking-ban text-rose-400"></i> Humo / Vapeo / Tabaco
                                    </div>
                                    <p class="text-gray-400 text-[11px] mt-0.5">Vaper en la mano, mesa o humo en cámara.</p>
                                </div>
                            </label>

                            <label class="flex items-start gap-3 p-3 rounded-xl bg-black/40 border border-white/10 hover:border-ttPink/50 cursor-pointer transition">
                                <input type="checkbox" value="Pedir regalos excesivamente, sorteos falsos o coerción" class="pre-check mt-1 w-4 h-4 accent-ttPink rounded">
                                <div class="text-xs">
                                    <div class="font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-gift text-amber-400"></i> Pedir Regalos Excesivamente
                                    </div>
                                    <p class="text-gray-400 text-[11px] mt-0.5">Mendicidad, prometer dinero o rifas por regalos.</p>
                                </div>
                            </label>

                            <label class="flex items-start gap-3 p-3 rounded-xl bg-black/40 border border-white/10 hover:border-ttPink/50 cursor-pointer transition">
                                <input type="checkbox" value="Conectar en PK o multi-invitado con creadores infractores o tóxicos" class="pre-check mt-1 w-4 h-4 accent-ttPink rounded">
                                <div class="text-xs">
                                    <div class="font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-link-slash text-orange-400"></i> Conectar con Infractores
                                    </div>
                                    <p class="text-gray-400 text-[11px] mt-0.5">Rival en batalla PK que insulta, fuma o muestra piel.</p>
                                </div>
                            </label>

                            <label class="flex items-start gap-3 p-3 rounded-xl bg-black/40 border border-white/10 hover:border-ttPink/50 cursor-pointer transition">
                                <input type="checkbox" value="Groserías fuertes, doble sentido sexual o vestimenta reveladora/lencería" class="pre-check mt-1 w-4 h-4 accent-ttPink rounded">
                                <div class="text-xs">
                                    <div class="font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-lips text-pink-400"></i> Groserías / Sexualidad / Ropa
                                    </div>
                                    <p class="text-gray-400 text-[11px] mt-0.5">Escotes extremos, ropa interior visible, insultos.</p>
                                </div>
                            </label>

                            <label class="flex items-start gap-3 p-3 rounded-xl bg-black/40 border border-white/10 hover:border-ttPink/50 cursor-pointer transition">
                                <input type="checkbox" value="Objetos cortopunzantes (tijeras, cuchillos, agujas) o réplicas de armas" class="pre-check mt-1 w-4 h-4 accent-ttPink rounded">
                                <div class="text-xs">
                                    <div class="font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-scissors text-red-400"></i> Objeto Cortopunzante / Armas
                                    </div>
                                    <p class="text-gray-400 text-[11px] mt-0.5">Tijeras, cuchillos de cocina cerca a la cara, pistolas de juguete.</p>
                                </div>
                            </label>

                            <label class="flex items-start gap-3 p-3 rounded-xl bg-black/40 border border-white/10 hover:border-ttPink/50 cursor-pointer transition">
                                <input type="checkbox" value="Retos de batalla extremos, castigos físicos, comer cosas crudas o humillación" class="pre-check mt-1 w-4 h-4 accent-ttPink rounded">
                                <div class="text-xs">
                                    <div class="font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-triangle-exclamation text-yellow-400"></i> Retos de Batalla Peligrosos
                                    </div>
                                    <p class="text-gray-400 text-[11px] mt-0.5">Castigos físicos, autolesión leve, retos humillantes.</p>
                                </div>
                            </label>
                        </div>
                    </div>

                    <!-- Paso 2: Descripción de lo que quieres hacer o decir en el LIVE -->
                    <div class="tt-card rounded-2xl p-5 space-y-3">
                        <div class="flex flex-wrap items-center justify-between gap-2">
                            <h3 class="text-sm sm:text-base font-bold text-white flex items-center gap-2">
                                <span class="w-6 h-6 rounded-full bg-ttCyan text-black font-extrabold text-xs flex items-center justify-center">2</span>
                                Describe tu idea, frase, reto PK o dinámica a auditar
                            </h3>
                            <span class="text-[11px] text-gray-400">Ejemplos rápidos de prueba:</span>
                        </div>

                        <!-- Botones de Casos de Prueba Rápidos -->
                        <div class="flex flex-wrap gap-1.5">
                            <button onclick="fillPreLiveScenario('Voy a hacer batallas PK y el que pierda se rompe un huevo en la cabeza y se pinta la cara con marcador.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                🥚 Reto PK: Huevo en la cabeza
                            </button>
                            <button onclick="fillPreLiveScenario('Estoy en mi cuarto con un top deportivo corto, tengo mi vaper apagado en la mesa y pondré música reggaetón de fondo.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                💨 Top deportivo + Vaper en mesa
                            </button>
                            <button onclick="fillPreLiveScenario('Haré un LIVE cocinando y cortando carne con un cuchillo grande mientras hablo con el chat.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                🔪 Cocinar con cuchillo en cámara
                            </button>
                            <button onclick="fillPreLiveScenario('Les diré a mis seguidores que el que mande más leones hoy entra a una rifa de 100 dólares por PayPal o Nequi.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                💸 Rifa de dinero por regalos
                            </button>
                        </div>

                        <textarea id="preLiveText" rows="3" placeholder="Escribe exactamente lo que vas a hacer, decir, vestir o mostrar en tu LIVE... (Ej: 'Quiero hacer un reto donde si pierdo la batalla hago 20 sentadillas, ¿me pueden quitar el 20% de los regalos?')" class="w-full rounded-xl bg-black/60 border border-white/15 focus:border-ttCyan focus:outline-none p-3.5 text-sm text-white placeholder-gray-500"></textarea>
                    </div>

                    <!-- Paso 3: Escáner Visual de Pantalla / Cámara / Subir Captura -->
                    <div class="tt-card rounded-2xl p-5 space-y-3">
                        <div class="flex flex-wrap items-center justify-between gap-2">
                            <div>
                                <h3 class="text-sm sm:text-base font-bold text-white flex items-center gap-2">
                                    <span class="w-6 h-6 rounded-full bg-ttCyan text-black font-extrabold text-xs flex items-center justify-center">3</span>
                                    Escáner Visual IA: Toma Pantallazo de tu Pantalla/Cámara o Sube Foto
                                </h3>
                                <p class="text-xs text-gray-400 mt-0.5">
                                    La IA inspecciona vestimenta, objetos de fondo, tijeras, vapers, marcas o posturas riesgosas.
                                </p>
                            </div>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-2.5">
                            <!-- Tomar captura de pantalla directa -->
                            <button type="button" onclick="captureScreenForAudit('pre')" class="flex items-center justify-center gap-2 p-3 rounded-xl bg-ttCyan/15 hover:bg-ttCyan/25 border border-ttCyan/40 text-ttCyan font-bold text-xs transition">
                                <i class="fa-solid fa-desktop"></i> Capturar mi Pantalla
                            </button>
                            <!-- Usar Cámara Web para revisar outfit/set -->
                            <button type="button" onclick="captureWebcamForAudit('pre')" class="flex items-center justify-center gap-2 p-3 rounded-xl bg-purple-500/15 hover:bg-purple-500/25 border border-purple-500/40 text-purple-300 font-bold text-xs transition">
                                <i class="fa-solid fa-video"></i> Probar mi Cámara/Set
                            </button>
                            <!-- Subir archivo de imagen -->
                            <label class="flex items-center justify-center gap-2 p-3 rounded-xl bg-white/5 hover:bg-white/10 border border-white/15 text-white font-bold text-xs cursor-pointer transition">
                                <i class="fa-solid fa-upload text-ttPink"></i> Subir Foto / Captura
                                <input type="file" id="preLiveImageInput" accept="image/*" class="hidden" onchange="handleImageUpload(event, 'pre')">
                            </label>
                        </div>

                        <!-- Vista previa de cámara en vivo (si activa webcam) -->
                        <div id="preWebcamContainer" class="hidden rounded-xl overflow-hidden bg-black border border-ttCyan/40 p-2 space-y-2">
                            <video id="preWebcamVideo" autoplay playsinline class="w-full max-h-56 object-contain rounded-lg bg-black"></video>
                            <div class="flex justify-end gap-2">
                                <button type="button" onclick="takeSnapshotFromWebcam('pre')" class="px-3 py-1.5 rounded-lg bg-ttCyan text-black font-bold text-xs">
                                    <i class="fa-solid fa-camera mr-1"></i> Tomar Foto Ahora
                                </button>
                                <button type="button" onclick="stopWebcam('pre')" class="px-3 py-1.5 rounded-lg bg-white/10 text-white text-xs">
                                    Cancelar
                                </button>
                            </div>
                        </div>

                        <!-- Vista previa de la imagen cargada -->
                        <div id="preImagePreviewWrapper" class="hidden relative rounded-xl overflow-hidden bg-black/70 border border-ttCyan/40 p-3 space-y-2.5">
                            <div class="flex items-center justify-between px-1">
                                <span class="text-xs font-bold text-ttCyan flex items-center gap-1.5">
                                    <i class="fa-solid fa-microscope"></i> Imagen cargada para Escáner Forense IA (Anti-Fotos Random)
                                </span>
                                <button type="button" onclick="removeUploadedImage('pre')" class="text-xs text-rose-400 hover:underline flex items-center gap-1 font-semibold">
                                    <i class="fa-solid fa-trash-can"></i> Quitar imagen
                                </button>
                            </div>
                            <img id="preImagePreview" src="" alt="Vista previa Pre-LIVE" class="max-h-52 w-auto mx-auto rounded-lg object-contain border border-white/10">
                            <button type="button" onclick="runPreLiveAudit(true)" class="w-full py-2.5 px-4 rounded-xl tt-btn-cyan font-extrabold text-xs sm:text-sm flex items-center justify-center gap-2 shadow-lg">
                                <i class="fa-solid fa-magnifying-glass"></i> 🔍 Auditar Esta Foto Ahora (Detectar Objetos, Ropa o Foto Random)
                            </button>
                        </div>

                        <!-- Botón Principal de Ejecución -->
                        <button type="button" onclick="runPreLiveAudit()" id="btnRunPreAudit" class="w-full py-3.5 px-6 rounded-xl tt-btn-primary text-white font-extrabold text-sm sm:text-base flex items-center justify-center gap-2.5 mt-2">
                            <i class="fa-solid fa-magnifying-glass-chart"></i>
                            AUDITAR MI LIVE AHORA (PREVENIR SANCIÓN Y -20% REGALOS)
                        </button>
                    </div>
                </div>

                <!-- Columna Derecha: Resultado Concreto del Auditor Pre-LIVE (5 cols) -->
                <div class="lg:col-span-5">
                    <div id="preLiveResultCard" class="tt-card rounded-2xl p-5 h-full flex flex-col justify-between border border-white/10 relative overflow-hidden">
                        <!-- Estado Inicial -->
                        <div id="preLivePlaceholder" class="my-auto text-center py-10 px-4 space-y-4">
                            <div class="w-16 h-16 rounded-2xl bg-ttCyan/10 border border-ttCyan/30 text-ttCyan flex items-center justify-center mx-auto text-2xl">
                                <i class="fa-solid fa-user-shield"></i>
                            </div>
                            <div class="space-y-1.5">
                                <h3 class="text-lg font-extrabold text-white">Veredicto Pre-LIVE sin Ambigüedades</h3>
                                <p class="text-xs text-gray-400 max-w-sm mx-auto leading-relaxed">
                                    Completa el paso 1, 2 o sube una captura de tu pantalla/vestimenta. Aquí verás de forma <strong class="text-white">100% directa y concreta</strong>:
                                </p>
                            </div>
                            <div class="text-left bg-black/50 rounded-xl p-3.5 border border-white/10 space-y-2 text-xs text-gray-300 max-w-sm mx-auto">
                                <div class="flex items-center gap-2"><i class="fa-solid fa-circle-check text-emerald-400"></i> <span>Si es <strong>SEGURO o INFRACTOR</strong> según TikTok LIVE.</span></div>
                                <div class="flex items-center gap-2"><i class="fa-solid fa-percent text-amber-400"></i> <span>Riesgo exacto de que te quiten el <strong>20% de tus regalos</strong>.</span></div>
                                <div class="flex items-center gap-2"><i class="fa-solid fa-arrow-trend-down text-rose-400"></i> <span>Cuántos puntos de <strong>Reputación (de 100)</strong> perderías.</span></div>
                                <div class="flex items-center gap-2"><i class="fa-solid fa-wand-magic-sparkles text-ttCyan"></i> <span>Cómo cambiarlo para transmitir sin ningún riesgo.</span></div>
                            </div>
                        </div>

                        <!-- Contenedor Dinámico del Resultado Pre-LIVE -->
                        <div id="preLiveOutput" class="hidden space-y-4"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÓDULO 2: AUDITORÍA POST-INFRACCIÓN ("EL DESPUÉS": ¿TÚ O TIKTOK?)     -->
        <!-- ===================================================================== -->
        <section id="section-postlive" class="tab-section hidden space-y-6">
            <!-- Banner Explicativo del Módulo 2 -->
            <div class="tt-card-pink rounded-2xl p-4 sm:p-5 flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
                <div class="space-y-1">
                    <div class="inline-flex items-center gap-2 text-ttPink font-bold text-xs uppercase tracking-wider">
                        <i class="fa-solid fa-gavel"></i> Defensa Inmediata Durante o Después del LIVE
                    </div>
                    <h2 class="text-lg sm:text-xl font-bold text-white">
                        Juez de Sanciones: ¿Realmente infringiste la norma o TikTok se equivocó?
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-300">
                        Ingresa la sanción exacta que te montó TikTok y sube el pantallazo. Te daremos un veredicto concreto, el texto de apelación listo y el <strong class="text-ttCyan">escalamiento directo a un Manager de TikTok</strong> si fue injusto.
                    </p>
                </div>
                <button onclick="openManagerModal()" class="px-4 py-2.5 rounded-xl tt-btn-cyan font-extrabold text-xs flex items-center gap-2 shrink-0">
                    <i class="fa-solid fa-user-tie"></i> Pedir Ayuda con Manager TikTok
                </button>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                <!-- Formulario de Auditoría Post-LIVE (7 cols) -->
                <div class="lg:col-span-7 space-y-5">

                    <!-- Pregunta Crítica 1: ¿Dónde apareció el aviso de infracción? -->
                    <div class="tt-card rounded-2xl p-5 space-y-3">
                        <h3 class="text-sm sm:text-base font-bold text-white flex items-center gap-2">
                            <span class="w-6 h-6 rounded-full bg-ttPink text-white font-extrabold text-xs flex items-center justify-center">1</span>
                            ¿Dónde te apareció exactamente el aviso de infracción?
                        </h3>
                        <p class="text-xs text-gray-400">
                            ¡OJO! Es vital diferenciar una sanción real del sistema frente a bromas en los comentarios.
                        </p>

                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-2.5">
                            <label class="cursor-pointer">
                                <input type="radio" name="postLocation" value="mitad_pantalla" checked onchange="checkAlertLocation()" class="peer hidden">
                                <div class="p-3 rounded-xl bg-black/50 border border-white/10 peer-checked:border-ttCyan peer-checked:bg-ttCyan/10 transition h-full">
                                    <div class="font-bold text-xs text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-mobile-screen text-ttCyan"></i> A mitad de pantalla
                                    </div>
                                    <p class="text-[11px] text-gray-400 mt-1">Cartel flotante en el centro del LIVE o corte directo.</p>
                                </div>
                            </label>

                            <label class="cursor-pointer">
                                <input type="radio" name="postLocation" value="estado_reputacion" onchange="checkAlertLocation()" class="peer hidden">
                                <div class="p-3 rounded-xl bg-black/50 border border-white/10 peer-checked:border-ttCyan peer-checked:bg-ttCyan/10 transition h-full">
                                    <div class="font-bold text-xs text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-bell text-amber-400"></i> Bandeja / Reputación
                                    </div>
                                    <p class="text-[11px] text-gray-400 mt-1">Notificación oficial del sistema o panel LIVE Studio.</p>
                                </div>
                            </label>

                            <label class="cursor-pointer">
                                <input type="radio" name="postLocation" value="en_comentarios" onchange="checkAlertLocation()" class="peer hidden">
                                <div class="p-3 rounded-xl bg-black/50 border border-white/10 peer-checked:border-rose-500 peer-checked:bg-rose-500/15 transition h-full">
                                    <div class="font-bold text-xs text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-comments text-rose-400"></i> En los comentarios
                                    </div>
                                    <p class="text-[11px] text-gray-400 mt-1">Apareció escrito dentro del chat de espectadores.</p>
                                </div>
                            </label>
                        </div>

                        <!-- Alerta instantánea si eligió "En los comentarios" -->
                        <div id="fakeCommentAlert" class="hidden p-3.5 rounded-xl bg-emerald-500/15 border border-emerald-500/40 text-xs text-emerald-200 space-y-1">
                            <div class="font-extrabold text-sm text-emerald-400 flex items-center gap-2">
                                <i class="fa-solid fa-face-laugh-wink"></i> ¡TRANQUILO/A! ES UNA FALSA ALARMA (TROLL EN EL CHAT)
                            </div>
                            <p>
                                TikTok <strong>NUNCA</strong> notifica infracciones escribiendo como un usuario en los comentarios. Una infracción real siempre sale <strong>a mitad de la pantalla</strong> o en tu Centro de Reputación LIVE. Bloquea o silencia a ese usuario y continúa tu transmisión con total normalidad.
                            </p>
                        </div>
                    </div>

                    <!-- Pregunta Crítica 2: Diferenciar Restricción de Visibilidad vs Sanción Dura -->
                    <div class="tt-card rounded-2xl p-5 space-y-3">
                        <h3 class="text-sm sm:text-base font-bold text-white flex items-center gap-2">
                            <span class="w-6 h-6 rounded-full bg-ttPink text-white font-extrabold text-xs flex items-center justify-center">2</span>
                            ¿Qué nivel de sanción o consecuencia te aplicó TikTok?
                        </h3>

                        <select id="postSanctionType" class="w-full rounded-xl bg-black/70 border border-white/15 focus:border-ttCyan p-3 text-xs sm:text-sm text-white font-medium">
                            <option value="visibilidad_leve">🟡 NIVEL 1: Infracción Leve / Restricción de Visibilidad (Pude continuar el LIVE pero bajaron las vistas o me restaron -1 a -3 pts)</option>
                            <option value="retencion_20_regalos">🟠 SANCIÓN DURA ECONÓMICA: Me retuvieron o quitaron el 20% de mis Regalos / Diamantes del LIVE</option>
                            <option value="bloqueo_3_7_dias">🟠 NIVEL 2 (GRAVEDAD MEDIA): Me cortaron el LIVE y me bloquearon el acceso de 3 a 7 días (-4 a -7 pts)</option>
                            <option value="perdida_total_nivel_3">🔴 NIVEL 3 (EXCESO DETECTADO GRAVE): TikTok me quitó las GANANCIAS TOTALES (100%) sin devolución o bloqueo severo</option>
                            <option value="baja_puntos_reputacion">📉 PUNTUACIÓN DE REPUTACIÓN: Mi puntuación bajó de 60 (o de 40) y perdí funciones como PK, OBS o Monetización</option>
                        </select>

                        <!-- Tarjeta informativa dinámica según el tipo de sanción -->
                        <div class="p-3 rounded-xl bg-white/5 border border-white/10 text-xs text-gray-300 flex items-start gap-2.5">
                            <i class="fa-solid fa-circle-info text-ttCyan mt-0.5"></i>
                            <div>
                                <strong class="text-white">Diferencia Clave:</strong> Una <em>Restricción de Visibilidad</em> solo deja de recomendar tu LIVE en el feed Para Ti temporalmente (puedes seguir transmitiendo), mientras que una <em>Sanción Dura</em> te quita el <strong class="text-amber-400">20% o 100% de regalos</strong>, te descuenta hasta <strong class="text-rose-400">-7 puntos de reputación</strong> o te bloquea de <strong class="text-orange-400">3 a 7 días</strong>.
                            </div>
                        </div>
                    </div>

                    <!-- Pregunta Crítica 3: Motivo que puso TikTok + Qué pasó realmente + Pantallazo -->
                    <div class="tt-card rounded-2xl p-5 space-y-4">
                        <h3 class="text-sm sm:text-base font-bold text-white flex items-center gap-2">
                            <span class="w-6 h-6 rounded-full bg-ttPink text-white font-extrabold text-xs flex items-center justify-center">3</span>
                            Escribe la sanción que te montó TikTok y qué estabas haciendo
                        </h3>

                        <!-- Casos rápidos de ejemplo post-sanción -->
                        <div class="flex flex-wrap gap-1.5">
                            <button onclick="fillPostScenario('Comportamiento peligroso o armas / Objetos cortopunzantes', 'Estaba haciendo manualidades recortando cartulina con unas tijeras escolares de punta redonda y me salió aviso a mitad de pantalla quitándome puntos y restringiendo el LIVE.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttPink/20 border border-white/10 text-gray-300 transition">
                                ✂️ Ejemplo: Tijeras en manualidades (Injusto)
                            </button>
                            <button onclick="fillPostScenario('Contenido sexualmente sugerente o vestimenta', 'Estaba hablando normal con una camiseta cuello V normal en mi sala, no mostré nada indebido y la IA de TikTok me sancionó con retención del 20% de regalos.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttPink/20 border border-white/10 text-gray-300 transition">
                                👕 Ejemplo: Falso positivo por ropa (Injusto)
                            </button>
                            <button onclick="fillPostScenario('Tabaco, alcohol o sustancias controladas', 'Saqué mi vaper un segundo y eché humo hacia un lado de la cámara mientras leía comentarios.')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttPink/20 border border-white/10 text-gray-300 transition">
                                💨 Ejemplo: Vapeé 1 segundo (TikTok tiene razón)
                            </button>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-gray-300 mb-1">¿Qué motivo exacto escribió TikTok en la notificación?</label>
                            <input id="postTikTokReason" type="text" placeholder="Ej: 'Contenido sexualmente sugerente', 'Actos peligrosos', 'Discurso de odio', 'Falta de originalidad'..." class="w-full rounded-xl bg-black/60 border border-white/15 focus:border-ttPink focus:outline-none p-3 text-sm text-white placeholder-gray-500">
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-gray-300 mb-1">Cuéntanos con total sinceridad: ¿Qué dijiste, qué llevabas puesto o qué se veía en pantalla?</label>
                            <textarea id="postCreatorStory" rows="3" placeholder="Explica exactamente qué pasó segundos antes de la infracción. Sé 100% honesto para saber si TikTok tuvo la razón o si fue un error de su IA..." class="w-full rounded-xl bg-black/60 border border-white/15 focus:border-ttPink focus:outline-none p-3 text-sm text-white placeholder-gray-500"></textarea>
                        </div>

                        <!-- Subir o capturar pantallazo de la sanción o del LIVE -->
                        <div class="space-y-2 pt-1">
                            <label class="block text-xs font-bold text-gray-300">Adjunta el pantallazo de la sanción o de cómo se veía tu LIVE (Opcional pero recomendado):</label>
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
                                <button type="button" onclick="captureScreenForAudit('post')" class="flex items-center justify-center gap-2 p-2.5 rounded-xl bg-ttCyan/15 hover:bg-ttCyan/25 border border-ttCyan/40 text-ttCyan font-bold text-xs transition">
                                    <i class="fa-solid fa-desktop"></i> Tomar Pantallazo Ahora
                                </button>
                                <label class="flex items-center justify-center gap-2 p-2.5 rounded-xl bg-white/5 hover:bg-white/10 border border-white/15 text-white font-bold text-xs cursor-pointer transition">
                                    <i class="fa-solid fa-upload text-ttPink"></i> Subir Captura de Sanción
                                    <input type="file" id="postLiveImageInput" accept="image/*" class="hidden" onchange="handleImageUpload(event, 'post')">
                                </label>
                            </div>
                            <div id="postImagePreviewWrapper" class="hidden relative rounded-xl overflow-hidden bg-black/70 border border-ttPink/40 p-3 mt-2 space-y-2.5">
                                <div class="flex items-center justify-between px-1">
                                    <span class="text-xs font-bold text-ttPink flex items-center gap-1.5">
                                        <i class="fa-solid fa-microscope"></i> Captura lista para Auditoría Forense del Juez IA
                                    </span>
                                    <button type="button" onclick="removeUploadedImage('post')" class="text-xs text-rose-400 hover:underline font-semibold">
                                        <i class="fa-solid fa-trash-can"></i> Quitar
                                    </button>
                                </div>
                                <img id="postImagePreview" src="" alt="Captura de sanción" class="max-h-48 w-auto mx-auto rounded-lg object-contain border border-white/10">
                                <button type="button" onclick="runPostLiveJudge(true)" class="w-full py-2.5 px-4 rounded-xl tt-btn-cyan font-extrabold text-xs flex items-center justify-center gap-2">
                                    <i class="fa-solid fa-magnifying-glass"></i> 🔍 Analizar Esta Captura Ahora con el Juez IA
                                </button>
                            </div>
                        </div>

                        <button type="button" onclick="runPostLiveJudge()" id="btnRunPostJudge" class="w-full py-3.5 px-6 rounded-xl tt-btn-primary text-white font-extrabold text-sm sm:text-base flex items-center justify-center gap-2.5">
                            <i class="fa-solid fa-scale-balanced"></i>
                            VERIFICAR QUIÉN TIENE LA RAZÓN Y GENERAR DEFENSA
                        </button>
                    </div>
                </div>

                <!-- Columna Derecha: Dictamen del Juez IA + Apelación + Escalamiento Manager (5 cols) -->
                <div class="lg:col-span-5">
                    <div class="tt-card rounded-2xl p-5 h-full flex flex-col justify-between border border-white/10">
                        <div id="postLivePlaceholder" class="my-auto text-center py-10 px-4 space-y-4">
                            <div class="w-16 h-16 rounded-2xl bg-ttPink/15 border border-ttPink/30 text-ttPink flex items-center justify-center mx-auto text-2xl">
                                <i class="fa-solid fa-gavel"></i>
                            </div>
                            <h3 class="text-lg font-extrabold text-white">Dictamen Directo: ¿Tú o TikTok?</h3>
                            <p class="text-xs text-gray-400 max-w-sm mx-auto leading-relaxed">
                                Analizaremos tu caso contra las Normas Oficiales de TikTok LIVE para decirte sin rodeos:
                            </p>
                            <div class="text-left bg-black/50 rounded-xl p-3.5 border border-white/10 space-y-2 text-xs text-gray-300 max-w-sm mx-auto">
                                <div class="flex items-center gap-2"><i class="fa-solid fa-check-double text-ttCyan"></i> <span>Veredicto claro: <strong>¿Quién tiene la razón?</strong></span></div>
                                <div class="flex items-center gap-2"><i class="fa-solid fa-file-signature text-emerald-400"></i> <span>Texto técnico listo para <strong>copiar y apelar en TikTok</strong>.</span></div>
                                <div class="flex items-center gap-2"><i class="fa-solid fa-user-shield text-ttPink"></i> <span>Pase directo a <strong>Manager de TikTok</strong> si rechazan tu apelación siendo 100% injusto.</span></div>
                            </div>
                        </div>

                        <!-- Contenedor Dinámico del Veredicto Post-LIVE -->
                        <div id="postLiveOutput" class="hidden space-y-4"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÓDULO 3: SIMULADOR OFICIAL DE PUNTUACIÓN DE REPUTACIÓN (BASE 100)    -->
        <!-- ===================================================================== -->
        <section id="section-reputation" class="tab-section hidden space-y-6">
            <!-- Encabezado de la Actualización Oficial de TikTok LIVE (Foto 2) -->
            <div class="tt-card rounded-2xl p-5 border border-emerald-500/30 bg-gradient-to-r from-emerald-950/30 via-ttCard to-ttCard">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
                    <div class="space-y-1">
                        <span class="text-[11px] font-extrabold uppercase tracking-widest px-2.5 py-0.5 rounded-full bg-emerald-500/20 text-emerald-300 border border-emerald-500/30">
                            Actualización Oficial TikTok LIVE (Foto 2)
                        </span>
                        <h2 class="text-xl sm:text-2xl font-extrabold text-white mt-1">
                            Puntuación de Reputación del Creador (Calificación Crediticia LIVE)
                        </h2>
                        <p class="text-xs sm:text-sm text-gray-300">
                            Todos los creadores comienzan con un máximo de <strong class="text-emerald-400">100 puntos</strong>. Tu puntuación determina qué funciones de LIVE y herramientas de monetización tienes activas o bloqueadas.
                        </p>
                    </div>
                    <div class="flex items-center gap-3 bg-black/60 px-4 py-3 rounded-2xl border border-white/10 shrink-0">
                        <div class="text-center">
                            <div class="text-[10px] uppercase font-bold text-gray-400">Máximo Inicial</div>
                            <div class="text-2xl font-black text-ttCyan">100 PTS</div>
                        </div>
                        <div class="h-8 w-px bg-white/10"></div>
                        <div class="text-center">
                            <div class="text-[10px] uppercase font-bold text-gray-400">Suma Diaria Máx</div>
                            <div class="text-lg font-extrabold text-emerald-400">+2 PTS/día</div>
                        </div>
                        <div class="h-8 w-px bg-white/10"></div>
                        <div class="text-center">
                            <div class="text-[10px] uppercase font-bold text-gray-400">Resta Diaria Máx</div>
                            <div class="text-lg font-extrabold text-rose-400">-10 PTS/día</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Calculadora y Medidor Interactivo -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                <!-- Panel de Control del Simulador (6 cols) -->
                <div class="lg:col-span-6 tt-card rounded-2xl p-5 space-y-5">
                    <div class="flex items-center justify-between">
                        <h3 class="text-base font-extrabold text-white flex items-center gap-2">
                            <i class="fa-solid fa-sliders text-ttCyan"></i> Calculadora Interactiva de tu Puntuación
                        </h3>
                        <button onclick="setRepScore(100)" class="text-xs px-2.5 py-1 rounded-lg bg-white/10 hover:bg-white/15 text-gray-200 font-semibold transition">
                            Reiniciar a 100
                        </button>
                    </div>

                    <!-- Medidor Visual Circular / Barra de Estado -->
                    <div class="p-5 rounded-2xl bg-black/60 border border-white/10 flex flex-col sm:flex-row items-center gap-6">
                        <div class="relative w-36 h-36 flex items-center justify-center shrink-0">
                            <svg class="w-full h-full -rotate-90" viewBox="0 0 120 120">
                                <circle cx="60" cy="60" r="50" stroke="#1f2433" stroke-width="12" fill="none"></circle>
                                <circle id="repGaugeCircle" cx="60" cy="60" r="50" stroke="#10b981" stroke-width="12" stroke-dasharray="314" stroke-dashoffset="0" stroke-linecap="round" fill="none" class="transition-all duration-500"></circle>
                            </svg>
                            <div class="absolute inset-0 flex flex-col items-center justify-center text-center">
                                <span id="repScoreDisplay" class="text-4xl font-black text-white">85</span>
                                <span id="repStatusBadge" class="text-[11px] font-extrabold uppercase px-2 py-0.5 rounded-full bg-emerald-500/20 text-emerald-400 mt-0.5">Bueno</span>
                            </div>
                        </div>

                        <div class="flex-1 space-y-3 w-full">
                            <label class="block text-xs font-bold text-gray-300">
                                Mueve el control o escribe tu puntuación actual (0 a 100):
                            </label>
                            <input id="repSlider" type="range" min="0" max="100" value="85" oninput="setRepScore(this.value)" class="w-full accent-ttCyan cursor-pointer h-2 bg-gray-800 rounded-lg">
                            <div class="flex justify-between text-[11px] text-gray-400 font-semibold">
                                <span class="text-rose-400">0-19 Bloqueo</span>
                                <span class="text-orange-400">20-39 Crítico</span>
                                <span class="text-amber-400">40-59 Alerta</span>
                                <span class="text-emerald-400">60-100 Óptimo</span>
                            </div>

                            <!-- Resumen de Días para Recuperarse -->
                            <div id="repRecoveryBox" class="p-3 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-xs text-gray-200">
                                <!-- Se llena por JS -->
                            </div>
                        </div>
                    </div>

                    <!-- Botones de Simulación de Deducción y Recuperación (Reglas exactas de Foto 2) -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                        <div class="p-3.5 rounded-xl bg-rose-500/10 border border-rose-500/30 space-y-2">
                            <div class="text-xs font-extrabold text-rose-400 uppercase flex items-center justify-between">
                                <span><i class="fa-solid fa-circle-arrow-down mr-1"></i> Simular Deducción</span>
                                <span class="text-[10px] bg-rose-500/20 px-1.5 py-0.5 rounded">Máx -10/día</span>
                            </div>
                            <p class="text-[11px] text-gray-300">De <strong>-1 a -7 pts</strong> según gravedad (se multiplica si es recurrente).</p>
                            <div class="flex flex-wrap gap-1.5 pt-1">
                                <button onclick="adjustRepScore(-1)" class="px-2.5 py-1.5 rounded-lg bg-rose-500/20 hover:bg-rose-500/30 text-rose-200 font-bold text-xs transition">-1 pt (Leve)</button>
                                <button onclick="adjustRepScore(-3)" class="px-2.5 py-1.5 rounded-lg bg-rose-500/20 hover:bg-rose-500/30 text-rose-200 font-bold text-xs transition">-3 pts (Media)</button>
                                <button onclick="adjustRepScore(-7)" class="px-2.5 py-1.5 rounded-lg bg-rose-600/40 hover:bg-rose-600/60 text-white font-bold text-xs transition">-7 pts (Grave)</button>
                                <button onclick="adjustRepScore(-10)" class="px-2.5 py-1.5 rounded-lg bg-rose-700/50 hover:bg-rose-700/70 text-white font-bold text-xs transition">-10 pts (Tope Día)</button>
                            </div>
                        </div>

                        <div class="p-3.5 rounded-xl bg-emerald-500/10 border border-emerald-500/30 space-y-2">
                            <div class="text-xs font-extrabold text-emerald-400 uppercase flex items-center justify-between">
                                <span><i class="fa-solid fa-circle-arrow-up mr-1"></i> Simular Suma / Recup.</span>
                                <span class="text-[10px] bg-emerald-500/20 px-1.5 py-0.5 rounded">Máx +2/día</span>
                            </div>
                            <p class="text-[11px] text-gray-300"><strong>+2 pts</strong> por LIVE &ge; 10 mins sin infracción, apelación exitosa o tareas educativas.</p>
                            <div class="flex flex-wrap gap-1.5 pt-1">
                                <button onclick="adjustRepScore(2)" class="px-2.5 py-1.5 rounded-lg bg-emerald-500/25 hover:bg-emerald-500/40 text-emerald-200 font-bold text-xs transition">+2 pts (LIVE &ge;10m limpio)</button>
                                <button onclick="adjustRepScore(4)" class="px-2.5 py-1.5 rounded-lg bg-ttCyan/20 hover:bg-ttCyan/35 text-ttCyan font-bold text-xs transition">+4 pts (Apelación Exitosa)</button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Tabla de Impacto "¿Cómo me afectará?" (6 cols) -->
                <div class="lg:col-span-6 tt-card rounded-2xl p-5 space-y-4">
                    <h3 class="text-base font-extrabold text-white flex items-center gap-2">
                        <i class="fa-solid fa-layer-group text-ttPink"></i> 3. ¿Cómo me afectará mi puntuación? (Rangos Oficiales)
                    </h3>
                    <p class="text-xs text-gray-400">
                        El rango iluminado corresponde a la puntuación que tienes seleccionada actualmente en el simulador:
                    </p>

                    <div class="space-y-2.5" id="repTiersList">
                        <!-- Rango 60-100 -->
                        <div id="tier-60-100" class="p-3.5 rounded-xl border border-emerald-500/40 bg-emerald-500/10 transition flex items-center justify-between gap-3">
                            <div class="flex items-center gap-3">
                                <div class="w-16 text-center py-1.5 rounded-lg bg-emerald-500/20 text-emerald-400 font-black text-sm shrink-0">
                                    60–100
                                </div>
                                <div>
                                    <div class="text-xs sm:text-sm font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-circle-check text-emerald-400"></i> Todas las funciones disponibles
                                    </div>
                                    <p class="text-[11px] text-gray-300 mt-0.5">Monetización al 100%, Batallas PK, Cofres, Multi-invitado, OBS y LIVE Studio activos.</p>
                                </div>
                            </div>
                        </div>

                        <!-- Rango 40-59 -->
                        <div id="tier-40-59" class="p-3.5 rounded-xl border border-white/10 bg-black/40 transition flex items-center justify-between gap-3">
                            <div class="flex items-center gap-3">
                                <div class="w-16 text-center py-1.5 rounded-lg bg-amber-500/20 text-amber-400 font-black text-sm shrink-0">
                                    40–59
                                </div>
                                <div>
                                    <div class="text-xs sm:text-sm font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-circle-exclamation text-amber-400"></i> Funciones de Herramientas Bloqueadas
                                    </div>
                                    <p class="text-[11px] text-gray-300 mt-0.5"><strong>NO disponibles:</strong> Star Comments, Draw & Guess, StreamElements, OBS y Restream.</p>
                                </div>
                            </div>
                        </div>

                        <!-- Rango 20-39 -->
                        <div id="tier-20-39" class="p-3.5 rounded-xl border border-white/10 bg-black/40 transition flex items-center justify-between gap-3">
                            <div class="flex items-center gap-3">
                                <div class="w-16 text-center py-1.5 rounded-lg bg-orange-500/20 text-orange-400 font-black text-sm shrink-0">
                                    20–39
                                </div>
                                <div>
                                    <div class="text-xs sm:text-sm font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-ban text-orange-400"></i> Monetización y PK Desactivados
                                    </div>
                                    <p class="text-[11px] text-gray-300 mt-0.5"><strong>NO disponibles:</strong> La mayoría de las funciones de monetización (Regalos), sociales y Batallas PK.</p>
                                </div>
                            </div>
                        </div>

                        <!-- Rango 0-19 -->
                        <div id="tier-0-19" class="p-3.5 rounded-xl border border-white/10 bg-black/40 transition flex items-center justify-between gap-3">
                            <div class="flex items-center gap-3">
                                <div class="w-16 text-center py-1.5 rounded-lg bg-rose-500/20 text-rose-400 font-black text-sm shrink-0">
                                    0–19
                                </div>
                                <div>
                                    <div class="text-xs sm:text-sm font-bold text-white flex items-center gap-1.5">
                                        <i class="fa-solid fa-lock text-rose-500"></i> Bloqueo Total de Funciones LIVE
                                    </div>
                                    <p class="text-[11px] text-gray-300 mt-0.5"><strong>Todas las funciones NO disponibles.</strong> Cuenta en estado crítico de suspensión.</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 4 Canales Oficiales para Consultarlo -->
                    <div class="pt-2 border-t border-white/10">
                        <h4 class="text-xs font-extrabold uppercase text-ttCyan mb-2.5">
                            4. ¿Dónde puedo consultar mi Puntuación de Reputación en TikTok?
                        </h4>
                        <div class="grid grid-cols-2 sm:grid-cols-4 gap-2">
                            <div class="p-2.5 rounded-xl bg-black/50 border border-white/10 text-center">
                                <i class="fa-solid fa-bell text-ttPink text-base"></i>
                                <div class="text-[11px] font-bold text-white mt-1">1. Bandeja de Entrada</div>
                                <div class="text-[10px] text-gray-400">Notificaciones del sistema</div>
                            </div>
                            <div class="p-2.5 rounded-xl bg-black/50 border border-white/10 text-center">
                                <i class="fa-solid fa-gauge text-emerald-400 text-base"></i>
                                <div class="text-[11px] font-bold text-white mt-1">2. Estado Reputación</div>
                                <div class="text-[10px] text-gray-400">Centro de seguridad LIVE</div>
                            </div>
                            <div class="p-2.5 rounded-xl bg-black/50 border border-white/10 text-center">
                                <i class="fa-solid fa-tower-broadcast text-ttCyan text-base"></i>
                                <div class="text-[11px] font-bold text-white mt-1">3. Sala de LIVE</div>
                                <div class="text-[10px] text-gray-400">Durante tu transmisión</div>
                            </div>
                            <div class="p-2.5 rounded-xl bg-black/50 border border-white/10 text-center">
                                <i class="fa-solid fa-desktop text-purple-400 text-base"></i>
                                <div class="text-[11px] font-bold text-white mt-1">4. LIVE Studio</div>
                                <div class="text-[10px] text-gray-400">Panel de PC / Mac</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÓDULO 4: CONSULTOR INTELIGENTE 24/7 & DICCIONARIO DE "CÓDIGO SEGURO" -->
        <!-- ===================================================================== -->
        <section id="section-consultant" class="tab-section hidden space-y-6">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">

                <!-- Columna Izquierda: Consultor Inteligente IA 24/7 (6 cols) -->
                <div class="lg:col-span-6 tt-card rounded-2xl p-5 flex flex-col justify-between space-y-4 border border-ttCyan/30">
                    <div class="space-y-2">
                        <div class="flex items-center justify-between">
                            <span class="text-[11px] font-extrabold uppercase tracking-wider px-2.5 py-0.5 rounded-full bg-ttCyan/15 text-ttCyan">
                                Respuestas 100% Concretas (Cero Ambigüedad)
                            </span>
                            <button onclick="clearConsultantChat()" class="text-xs text-gray-400 hover:text-white">Limpiar chat</button>
                        </div>
                        <h3 class="text-lg font-extrabold text-white flex items-center gap-2">
                            <i class="fa-solid fa-brain text-ttCyan"></i> Consultor Inteligente de Normas TikTok LIVE
                        </h3>
                        <p class="text-xs text-gray-300">
                            Haz cualquier pregunta sobre lo que quieres hacer en tu LIVE, vestimenta, música, batallas PK o sanciones. Te responderé con un <strong>SÍ o NO rotundo</strong> y cómo proteger tus regalos.
                        </p>

                        <!-- Preguntas frecuentes de 1 clic -->
                        <div class="flex flex-wrap gap-1.5 pt-1">
                            <button onclick="askQuickQuestion('¿Por qué TikTok quita el 20% de los regalos y cómo lo evito?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                💰 ¿Por qué quitan el 20% de regalos?
                            </button>
                            <button onclick="askQuickQuestion('¿Qué hago si mi rival de batalla PK empieza a fumar o insultar en vivo?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                ⚔️ Rival PK infringe normas
                            </button>
                            <button onclick="askQuickQuestion('¿Puedo mostrar a mi hijo o sobrino pequeño saludando en mi TikTok LIVE?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                👶 ¿Menores en cámara?
                            </button>
                            <button onclick="askQuickQuestion('¿Cuál es la diferencia entre restricción de visibilidad y suspensión de LIVE?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-white/5 hover:bg-ttCyan/20 border border-white/10 text-gray-300 transition">
                                👁️ Visibilidad vs Sanción Dura
                            </button>
                        </div>
                    </div>

                    <!-- Ventana de Mensajes del Consultor -->
                    <div id="consultantChatBox" class="h-80 overflow-y-auto rounded-xl bg-black/60 border border-white/10 p-3.5 space-y-3 text-xs sm:text-sm">
                        <div class="p-3 rounded-xl bg-ttCyan/10 border border-ttCyan/30 text-gray-200 space-y-1">
                            <div class="font-extrabold text-ttCyan text-xs flex items-center gap-1.5">
                                <i class="fa-solid fa-shield-halved"></i> Auditor IA Oficial (Listo)
                            </div>
                            <p class="text-xs leading-relaxed">
                                ¡Hola Creador! Escribe cualquier duda sobre tu transmisión. Te diré sin rodeos si es seguro, si arriesga el <strong>20% de tus diamantes</strong> o tus <strong>100 puntos de reputación</strong>, y cómo hacerlo legalmente.
                            </p>
                        </div>
                    </div>

                    <!-- Input de pregunta -->
                    <form onsubmit="handleConsultantSubmit(event)" class="flex gap-2">
                        <input id="consultantInput" type="text" placeholder="Escribe tu duda aquí... Ej: ¿Puedo transmitir en bikini en una piscina?" class="flex-1 rounded-xl bg-black/70 border border-white/15 focus:border-ttCyan focus:outline-none px-3.5 py-2.5 text-sm text-white placeholder-gray-500">
                        <button type="submit" id="btnAskConsultant" class="px-5 py-2.5 rounded-xl tt-btn-cyan font-extrabold text-xs sm:text-sm shrink-0 flex items-center gap-1.5">
                            <i class="fa-solid fa-paper-plane"></i> Consultar
                        </button>
                    </form>
                </div>

                <!-- Columna Derecha: Diccionario de "Código Seguro" (Palabras y Acciones) (6 cols) -->
                <div class="lg:col-span-6 tt-card rounded-2xl p-5 space-y-4">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2">
                        <div>
                            <h3 class="text-lg font-extrabold text-white flex items-center gap-2">
                                <i class="fa-solid fa-spell-check text-amber-400"></i> Diccionario de "Código Seguro" TikTok LIVE
                            </h3>
                            <p class="text-xs text-gray-400">
                                Evita que el detector automático de voz/imagen te sancione por palabras o gestos prohibidos.
                            </p>
                        </div>
                    </div>

                    <div class="relative">
                        <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-3 text-gray-400 text-xs"></i>
                        <input id="dictionarySearch" type="text" oninput="filterDictionary()" placeholder="Buscar palabra, objeto o situación (ej. dinero, rifa, cuchillo, vape, instagram)..." class="w-full pl-9 pr-4 py-2 rounded-xl bg-black/60 border border-white/15 focus:border-amber-400 focus:outline-none text-xs sm:text-sm text-white">
                    </div>

                    <div id="dictionaryList" class="h-[360px] overflow-y-auto space-y-2 pr-1">
                        <!-- Renderizado dinámicamente por JS -->
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÓDULO 5: GUÍA VISUAL OFICIAL (FOTOS 1 Y 2 + PROTOCOLO DE AGENCIA)    -->
        <!-- ===================================================================== -->
        <section id="section-guide" class="tab-section hidden space-y-6">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">

                <!-- Infografía Interactiva 1: Guía de Seguridad y Escala de Sanciones 1-2-3 -->
                <div class="tt-card rounded-2xl p-5 border border-ttCyan/30 space-y-5">
                    <div class="text-center border-b border-white/10 pb-3">
                        <span class="text-[11px] font-extrabold uppercase tracking-widest text-ttCyan">Referencia Oficial #1</span>
                        <h3 class="text-xl font-black text-white mt-0.5">GUÍA DE SEGURIDAD TIKTOK LIVE: NORMAS Y NIVELES DE SANCIÓN</h3>
                    </div>

                    <!-- Zona de Cumplimiento -->
                    <div>
                        <h4 class="text-xs font-extrabold uppercase tracking-wider text-center text-ttCyan mb-3">
                            ZONA DE CUMPLIMIENTO (LO QUE DEBES EVITAR SIEMPRE)
                        </h4>
                        <div class="grid grid-cols-2 sm:grid-cols-3 gap-2.5">
                            <div class="p-3 rounded-xl bg-black/50 border border-rose-500/30 text-center space-y-1">
                                <div class="w-10 h-10 rounded-full bg-rose-500/20 text-rose-400 flex items-center justify-center mx-auto text-lg">
                                    <i class="fa-solid fa-smoking-ban"></i>
                                </div>
                                <div class="text-xs font-extrabold text-white">SIN HUMO / VAPEO</div>
                                <p class="text-[10px] text-gray-400">Ni encendido ni apagado en cámara.</p>
                            </div>
                            <div class="p-3 rounded-xl bg-black/50 border border-rose-500/30 text-center space-y-1">
                                <div class="w-10 h-10 rounded-full bg-amber-500/20 text-amber-400 flex items-center justify-center mx-auto text-lg">
                                    <i class="fa-solid fa-hand-holding-heart"></i>
                                </div>
                                <div class="text-xs font-extrabold text-white">NO PEDIR REGALOS EXCESIVAMENTE</div>
                                <p class="text-[10px] text-gray-400">Prohibido prometer dinero o rifas.</p>
                            </div>
                            <div class="p-3 rounded-xl bg-black/50 border border-rose-500/30 text-center space-y-1">
                                <div class="w-10 h-10 rounded-full bg-orange-500/20 text-orange-400 flex items-center justify-center mx-auto text-lg">
                                    <i class="fa-solid fa-users-slash"></i>
                                </div>
                                <div class="text-xs font-extrabold text-white">NO CONECTAR CON INFRACTORES</div>
                                <p class="text-[10px] text-gray-400">Si tu rival infringe, corta el PK.</p>
                            </div>
                            <div class="p-3 rounded-xl bg-black/50 border border-rose-500/30 text-center space-y-1">
                                <div class="w-10 h-10 rounded-full bg-pink-500/20 text-pink-400 flex items-center justify-center mx-auto text-lg">
                                    <i class="fa-solid fa-comment-slash"></i>
                                </div>
                                <div class="text-xs font-extrabold text-white">CERO GROSERÍAS / SEXUALIDAD</div>
                                <p class="text-[10px] text-gray-400">Cuida escotes, ropa y vocabulario.</p>
                            </div>
                            <div class="p-3 rounded-xl bg-black/50 border border-rose-500/30 text-center space-y-1">
                                <div class="w-10 h-10 rounded-full bg-red-500/20 text-red-400 flex items-center justify-center mx-auto text-lg">
                                    <i class="fa-solid fa-scissors"></i>
                                </div>
                                <div class="text-xs font-extrabold text-white">NADA CORTOPUNZANTE</div>
                                <p class="text-[10px] text-gray-400">Sin tijeras, cuchillos ni armas.</p>
                            </div>
                            <div class="p-3 rounded-xl bg-black/50 border border-rose-500/30 text-center space-y-1">
                                <div class="w-10 h-10 rounded-full bg-yellow-500/20 text-yellow-400 flex items-center justify-center mx-auto text-lg">
                                    <i class="fa-solid fa-shield-halved"></i>
                                </div>
                                <div class="text-xs font-extrabold text-white">CUIDADO RETOS BATALLA</div>
                                <p class="text-[10px] text-gray-400">Elige bien rivales y penitencias.</p>
                            </div>
                        </div>
                    </div>

                    <!-- Escala de Restricciones y Pérdidas (Niveles 1, 2 y 3) -->
                    <div>
                        <h4 class="text-xs font-extrabold uppercase tracking-wider text-center text-ttCyan mb-3">
                            ESCALA DE RESTRICCIONES Y PÉRDIDAS (SISTEMA DE DETECCIÓN)
                        </h4>
                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                            <!-- Nivel 1 -->
                            <div class="p-4 rounded-2xl bg-yellow-500/10 border-2 border-yellow-400/70 text-center space-y-2">
                                <span class="inline-block px-2.5 py-0.5 rounded-md bg-yellow-400 text-black font-black text-xs">NIVEL 1</span>
                                <div class="text-sm font-black text-yellow-300">INFRACCIÓN LEVE</div>
                                <p class="text-xs text-gray-200 leading-relaxed">
                                    Pequeña notificación a <strong>mitad de pantalla</strong> o baja de visibilidad. Podrás <strong class="text-yellow-300">CONTINUAR</strong> con el LIVE.
                                </p>
                            </div>
                            <!-- Nivel 2 -->
                            <div class="p-4 rounded-2xl bg-orange-500/10 border-2 border-orange-500/80 text-center space-y-2">
                                <span class="inline-block px-2.5 py-0.5 rounded-md bg-orange-500 text-black font-black text-xs">NIVEL 2 (3-7 DÍAS)</span>
                                <div class="text-sm font-black text-orange-300">GRAVEDAD MEDIA / -20%</div>
                                <p class="text-xs text-gray-200 leading-relaxed">
                                    Riesgo de <strong>retención del 20% de regalos</strong> o bloqueo temporal de acceso a LIVE de <strong>3 días a 1 semana</strong>.
                                </p>
                            </div>
                            <!-- Nivel 3 -->
                            <div class="p-4 rounded-2xl bg-rose-600/15 border-2 border-rose-500 text-center space-y-2 animate-glow">
                                <span class="inline-block px-2.5 py-0.5 rounded-md bg-rose-600 text-white font-black text-xs">🚨 NIVEL 3 🚨</span>
                                <div class="text-sm font-black text-rose-400">EXCESO DETECTADO (GRAVE)</div>
                                <p class="text-xs text-gray-200 leading-relaxed">
                                    <strong class="text-white">TIKTOK QUITA GANANCIAS TOTALES. SIN DEVOLUCIÓN</strong> y bloquea monetización.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Diferenciación Clave + Protocolo de Escalamiento a Manager -->
                <div class="space-y-6">
                    <div class="tt-card rounded-2xl p-5 border border-amber-500/30 space-y-4">
                        <h3 class="text-lg font-extrabold text-white flex items-center gap-2">
                            <i class="fa-solid fa-eye-low-vision text-amber-400"></i> Cómo Diferenciar cada Alerta en tu Pantalla
                        </h3>

                        <div class="space-y-3 text-xs sm:text-sm">
                            <div class="p-3.5 rounded-xl bg-black/50 border-l-4 border-l-emerald-400">
                                <div class="font-extrabold text-emerald-400">1. Mensaje en Comentarios = FALSO (Troll)</div>
                                <p class="text-gray-300 text-xs mt-1">
                                    Si ves un texto en el chat de comentarios diciendo <em>"TikTok cerrará tu LIVE en 30 segundos"</em>, es un espectador haciéndose pasar por el sistema. <strong>Las infracciones reales jamás salen en el chat.</strong>
                                </p>
                            </div>

                            <div class="p-3.5 rounded-xl bg-black/50 border-l-4 border-l-yellow-400">
                                <div class="font-extrabold text-yellow-400">2. Restricción de Visibilidad = Corrección Inmediata</div>
                                <p class="text-gray-300 text-xs mt-1">
                                    Aparece un aviso a mitad de pantalla indicando que tu LIVE no es elegible para el feed "Para Ti" (FYP). No te cierra el LIVE, pero frena la entrada de gente nueva hasta que corrijas el ángulo, ropa o tema.
                                </p>
                            </div>

                            <div class="p-3.5 rounded-xl bg-black/50 border-l-4 border-l-rose-500">
                                <div class="font-extrabold text-rose-400">3. Sanción Dura (-20% de Regalos, -7 Pts o Corte de 3 a 7 Días)</div>
                                <p class="text-gray-300 text-xs mt-1">
                                    Ocurre cuando el sistema detecta reincidencia, objetos prohibidos, vestimenta límite o agresividad en batallas PK. Aquí debes <strong>APELAR INMEDIATAMENTE</strong>.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Protocolo Directo con Manager de TikTok -->
                    <div class="tt-card-pink rounded-2xl p-5 space-y-4">
                        <div class="flex items-center gap-3">
                            <div class="w-12 h-12 rounded-2xl bg-ttPink/20 border border-ttPink text-ttPink flex items-center justify-center text-xl shrink-0">
                                <i class="fa-solid fa-user-check"></i>
                            </div>
                            <div>
                                <span class="text-[11px] font-bold uppercase text-ttCyan">Respaldo Exclusivo para el Creador</span>
                                <h3 class="text-lg font-extrabold text-white">Protocolo de Apelación y Manager de TikTok</h3>
                            </div>
                        </div>

                        <ol class="space-y-2.5 text-xs text-gray-200 list-decimal list-inside bg-black/40 p-4 rounded-xl border border-white/10">
                            <li><strong>Apela siempre primero en TikTok:</strong> Usa el texto técnico que te genera nuestro <em>Módulo 2 (Juez Post-Infracción)</em> apenas te salga el aviso a mitad de pantalla o en tu Estado de Reputación.</li>
                            <li><strong>¿Te rechazaron la apelación automática?:</strong> Muchas veces un bot de TikTok rechaza apelaciones en segundos sin revisión humana.</li>
                            <li><strong>Si estás 100% seguro/a de que fue INJUSTO:</strong> Pídenos ayuda de inmediato con el botón de abajo. Nosotros enviaremos tu evidencia directamente a un <strong>Manager Oficial de TikTok</strong> para que revise el caso manualmente y restaure tus puntos o el acceso a LIVE.</li>
                        </ol>

                        <div class="flex flex-wrap gap-3">
                            <button onclick="openManagerModal()" class="flex-1 py-3 px-4 rounded-xl tt-btn-primary text-white font-extrabold text-xs sm:text-sm flex items-center justify-center gap-2">
                                <i class="fa-solid fa-paper-plane"></i> Solicitar Revisión con Manager de TikTok
                            </button>
                            <a href="https://www.tiktok.com/safety/es/tools-and-guides/live-safety-guide" target="_blank" rel="noopener noreferrer" class="py-3 px-4 rounded-xl bg-white/10 hover:bg-white/15 text-white font-bold text-xs sm:text-sm flex items-center justify-center gap-2 transition">
                                <i class="fa-solid fa-arrow-up-right-from-square text-ttCyan"></i> Guía Oficial TikTok LIVE
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- ===================================================================== -->
    <!-- MODAL 1: ESCALAMIENTO DIRECTO A MANAGER DE TIKTOK (VÍA AGENCIA)        -->
    <!-- ===================================================================== -->
    <div id="managerModal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="tt-card rounded-2xl max-w-lg w-full p-6 border border-ttCyan/40 space-y-4 max-h-[90vh] overflow-y-auto">
            <div class="flex items-center justify-between border-b border-white/10 pb-3">
                <div class="flex items-center gap-2.5">
                    <div class="w-9 h-9 rounded-xl bg-ttPink/20 text-ttPink flex items-center justify-center">
                        <i class="fa-solid fa-headset"></i>
                    </div>
                    <div>
                        <h3 class="text-base font-extrabold text-white">Escalar Sanción Injusta a Manager de TikTok</h3>
                        <p class="text-[11px] text-ttCyan">Solo cuando ya apelaste en la app y estás 100% seguro de que fue injusto</p>
                    </div>
                </div>
                <button onclick="closeManagerModal()" class="text-gray-400 hover:text-white text-lg">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <div class="space-y-3 text-xs">
                <div class="p-3 rounded-xl bg-amber-500/10 border border-amber-500/30 text-amber-200">
                    <strong>Requisito indispensable:</strong> Para que el Manager de TikTok acepte revisar tu caso, confirma que <strong>ya enviaste la apelación dentro de TikTok</strong> y ten a la mano la captura de pantalla del rechazo o de la infracción a mitad de pantalla.
                </div>

                <div>
                    <label class="block font-bold text-gray-300 mb-1">Tu @Usuario de TikTok:</label>
                    <input id="mgrUsername" type="text" placeholder="@tu_usuario_tiktok" class="w-full rounded-xl bg-black/70 border border-white/15 p-2.5 text-white">
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
                    <div>
                        <label class="block font-bold text-gray-300 mb-1">Puntuación de Reputación actual:</label>
                        <input id="mgrScore" type="number" min="0" max="100" value="85" class="w-full rounded-xl bg-black/70 border border-white/15 p-2.5 text-white">
                    </div>
                    <div>
                        <label class="block font-bold text-gray-300 mb-1">Estado de la apelación en la app:</label>
                        <select id="mgrAppealStatus" class="w-full rounded-xl bg-black/70 border border-white/15 p-2.5 text-white">
                            <option value="Apelación rechazada por TikTok (100% injusta)">Ya apelé y TikTok la rechazó</option>
                            <option value="Apelación en revisión pero bloqueo grave/retención 20%">Ya apelé (Retención 20% / Bloqueo 3-7 días)</option>
                            <option value="No me aparece botón de apelar en la sanción">No me dejó apelar en la app</option>
                        </select>
                    </div>
                </div>

                <div>
                    <label class="block font-bold text-gray-300 mb-1">Resumen del caso (Se autocompleta si usaste el Juez IA):</label>
                    <textarea id="mgrSummary" rows="3" placeholder="Explica por qué estás 100% seguro de que no infringiste las normas de TikTok LIVE..." class="w-full rounded-xl bg-black/70 border border-white/15 p-2.5 text-white"></textarea>
                </div>

                <button onclick="generateManagerTicket()" class="w-full py-3 rounded-xl tt-btn-cyan font-extrabold text-xs sm:text-sm flex items-center justify-center gap-2">
                    <i class="fa-solid fa-copy"></i> Copiar Reporte Oficial para Enviar a la Agencia / Manager
                </button>
            </div>
        </div>
    </div>

    <!-- PIE DE PÁGINA -->
    <footer class="mt-10 border-t border-white/10 py-5 px-4 text-center text-xs text-gray-500">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-2">
            <div>
                <strong class="text-gray-300">TikTok LIVE Shield Pro</strong> — Sistema Inteligente de Auditoría Pre/Post LIVE y Defensa de Reputación (Base 100 Pts).
            </div>
            <div class="flex flex-wrap items-center justify-center gap-4">
                <a href="https://www.tiktok.com/safety/es/tools-and-guides/live-safety-guide" target="_blank" rel="noopener noreferrer" class="text-ttCyan hover:underline">
                    Guía de Seguridad de TikTok LIVE
                </a>
                <span>•</span>
                <button onclick="openManagerModal()" class="text-ttPink hover:underline font-semibold">
                    Escalar Caso Injusto a Manager
                </button>
            </div>
        </div>
    </footer>

    <!-- ===================================================================== -->
    <!-- LÓGICA JAVASCRIPT + MOTOR HÍBRIDO DETERMINISTA + GEMINI API MULTIMODAL -->
    <!-- ===================================================================== -->
    <script>
        // Configuración de la API de Gemini con soporte prioritario para gemini-2.5-flash y respaldo en gemini-3-flash-preview
        const apiKey = "";
        const GEMINI_MODELS = ["gemini-2.5-flash", "gemini-3-flash-preview"];

        // Estado de imágenes cargadas (Base64) para Pre-LIVE y Post-LIVE
        const appState = {
            preImageBase64: null,
            preImageMime: "image/png",
            preImageMetrics: null,
            postImageBase64: null,
            postImageMime: "image/png",
            postImageMetrics: null,
            webcamStream: null,
            repScore: 85,
            lastAppealText: "",
            lastJudgeSummary: ""
        };

        // Base de datos del Diccionario de "Código Seguro" TikTok LIVE
        const SAFE_DICTIONARY = [
            {
                forbidden: "Dinero, Efectivo, Dólares, PayPal, Nequi, Zelle, Cuenta Bancaria",
                category: "Monetización / Fraude",
                risk20: "ALTO RIESGO (-20% Regalos o Nivel 3)",
                safeCode: "Di: 'Monedas', 'Diamantes', 'Puntos de apoyo' o 'Regalos de la plataforma'. Jamás menciones transacciones fuera de TikTok.",
                severity: "high"
            },
            {
                forbidden: "Rifa, Sorteo, Lotería, 'El que mande un León gana dinero'",
                category: "Juegos de Azar / Coerción",
                risk20: "CRÍTICO (Quitan 100% ganancias - Nivel 3)",
                safeCode: "Prohibido hacer sorteos condicionados a regalos. En su lugar usa las herramientas nativas de TikTok LIVE como 'Cofre del Tesoro' o dinámicas gratuitas sin prometer premios económicos.",
                severity: "critical"
            },
            {
                forbidden: "Vape, Vaper, Cigarro, Humo, Marihuana, Encendedor en mano",
                category: "Sustancias Controladas",
                risk20: "ALTO RIESGO (-20% Regalos y -4 a -7 pts)",
                safeCode: "Cero humo o vapor en cámara (ni siquiera vape sin nicotina o apagado sobre la mesa). Si necesitas fumar, apaga la cámara o sal de cuadro totalmente sin que se vea humo.",
                severity: "high"
            },
            {
                forbidden: "Cuchillo, Tijeras, Navaja, Bisturí, Pistola de juguete / Airsoft",
                category: "Objetos Cortopunzantes / Armas",
                risk20: "ALTO RIESGO (Corte de LIVE inmediato)",
                safeCode: "La visión artificial de TikTok detecta tijeras y cuchillos como armas. Si haces cocina o manualidades, mantén la herramienta baja sobre la mesa, nunca apuntando a la cámara ni cerca del rostro.",
                severity: "high"
            },
            {
                forbidden: "Retos de batalla PK con huevos, golpes, comer picante extremo o humillación",
                category: "Actos Peligrosos / Acoso",
                risk20: "ALTO RIESGO (-20% Regalos o Bloqueo 3-7 días)",
                safeCode: "Usa penitencias seguras: maquillarse de forma graciosa con pintura lavable, cantar una canción, usar un filtro divertido o hacer 5 sentadillas suaves.",
                severity: "high"
            },
            {
                forbidden: "Ropa interior visible, Bikini en habitación, Escote extremo, Topless masculino de cerca",
                category: "Desnudez y Sexualidad",
                risk20: "CRÍTICO (-20% Regalos instantáneo y -3 a -7 pts)",
                safeCode: "Usa prendas que cubran el torso y pecho adecuadamente. Si estás en piscina/playa debe verse claramente el entorno real y usar salida de baño al acercarte a la cámara.",
                severity: "critical"
            },
            {
                forbidden: "Groserías, Insultos al rival de PK, 'Te voy a matar / golpear'",
                category: "Discurso de Odio y Acoso",
                risk20: "MEDIO/ALTO (-1 a -5 pts y baja visibilidad)",
                safeCode: "Incluso en broma con amigos, el algoritmo de voz sanciona amenazas. Di: 'Te voy a ganar en esta partida', 'Te dejé en cero en la batalla'.",
                severity: "medium"
            },
            {
                forbidden: "Conectar con un rival en PK que está fumando, insultando o mostrando piel",
                category: "Infracción Compartida (Co-Host)",
                risk20: "ALTO RIESGO (Te sancionan a ti también)",
                safeCode: "Si tu invitado o rival PK hace algo ilegal, desconecta la batalla en menos de 5 segundos y di en voz alta: 'No apruebo ese comportamiento, cortamos conexión'.",
                severity: "high"
            },
            {
                forbidden: "Dejar la pantalla vacía, grabada, durmiendo o solo mirando el celular en silencio",
                category: "Falta de Interacción / Contenido Estático",
                risk20: "MEDIO (Restricción de Visibilidad FYP)",
                safeCode: "Interactúa constantemente. Si vas al baño por 1 minuto, avisa verbalmente y regresa rápido; nunca dejes la silla vacía más de 60 segundos.",
                severity: "medium"
            },
            {
                forbidden: "Mostrar niños solos en pantalla o leyendo el chat",
                category: "Seguridad de Menores",
                risk20: "CRÍTICO (Bloqueo inmediato de LIVE 7 días+)",
                safeCode: "Los menores nunca deben aparecer solos frente al LIVE ni interactuar con el chat. Siempre debe estar el adulto creador como protagonista principal.",
                severity: "critical"
            }
        ];

        // Función utilitaria para mostrar notificaciones Toast sin usar alert()
        function showToast(message, type = "info") {
            const container = document.getElementById("toastContainer");
            const toast = document.createElement("div");
            const colors = {
                info: "border-ttCyan bg-[#0e1624] text-white",
                success: "border-emerald-400 bg-[#0b1f19] text-emerald-100",
                warning: "border-amber-400 bg-[#231909] text-amber-100",
                error: "border-rose-500 bg-[#260b14] text-rose-100"
            };
            const icons = {
                info: "fa-circle-info text-ttCyan",
                success: "fa-circle-check text-emerald-400",
                warning: "fa-triangle-exclamation text-amber-400",
                error: "fa-circle-xmark text-rose-500"
            };

            toast.className = `pointer-events-auto flex items-start gap-3 p-3.5 rounded-xl border shadow-2xl transition-all duration-300 ${colors[type] || colors.info}`;
            toast.innerHTML = `
                <i class="fa-solid ${icons[type] || icons.info} mt-0.5 text-base"></i>
                <div class="text-xs font-semibold leading-snug flex-1">${message}</div>
            `;
            container.appendChild(toast);
            setTimeout(() => {
                toast.style.opacity = "0";
                toast.style.transform = "translateY(8px)";
                setTimeout(() => toast.remove(), 300);
            }, 4200);
        }

        // Copiar texto al portapapeles de forma compatible con Google Sites (iFrame)
        function copyTextToClipboard(text, successMsg = "¡Copiado al portapapeles!") {
            const textArea = document.createElement("textarea");
            textArea.value = text;
            textArea.style.position = "fixed";
            textArea.style.left = "-9999px";
            document.body.appendChild(textArea);
            textArea.focus();
            textArea.select();
            try {
                document.execCommand("copy");
                showToast(successMsg, "success");
            } catch (err) {
                showToast("No se pudo copiar automáticamente. Selecciona el texto y presiona Ctrl+C.", "warning");
            }
            document.body.removeChild(textArea);
        }

        // Cambio de pestañas principales
        function switchTab(tabId) {
            document.querySelectorAll(".tab-section").forEach(sec => sec.classList.add("hidden"));
            document.querySelectorAll(".tab-btn").forEach(btn => btn.classList.remove("tab-active"));

            const targetSection = document.getElementById(`section-${tabId}`);
            const targetBtn = document.getElementById(`tab-${tabId}`);
            if (targetSection) targetSection.classList.remove("hidden");
            if (targetBtn) targetBtn.classList.add("tab-active");
        }

        // Helpers de Pre-LIVE
        function clearPreLiveChecklist() {
            document.querySelectorAll(".pre-check").forEach(cb => cb.checked = false);
            showToast("Checklist de Zona de Cumplimiento reiniciado.", "info");
        }

        function fillPreLiveScenario(text) {
            document.getElementById("preLiveText").value = text;
            showToast("Escenario de prueba cargado. Haz clic en 'Auditar mi LIVE ahora'.", "info");
        }

        // Helpers de Post-LIVE
        function checkAlertLocation() {
            const selected = document.querySelector('input[name="postLocation"]:checked')?.value;
            const fakeAlert = document.getElementById("fakeCommentAlert");
            if (selected === "en_comentarios") {
                fakeAlert.classList.remove("hidden");
                showToast("¡Atención! Un aviso en los comentarios NO es una infracción real de TikTok.", "warning");
            } else {
                fakeAlert.classList.add("hidden");
            }
        }

        function fillPostScenario(reason, story) {
            document.getElementById("postTikTokReason").value = reason;
            document.getElementById("postCreatorStory").value = story;
            showToast("Caso cargado. Haz clic en 'Verificar quién tiene la razón'.", "info");
        }

        // =====================================================================
        // CAPTURA DE PANTALLA, WEBCAM Y SUBIDA DE IMÁGENES PARA AUDITORÍA IA
        // =====================================================================
        function analyzeImageCanvasMetrics(dataUrl, callback) {
            const img = new Image();
            img.onload = function() {
                const canvas = document.createElement("canvas");
                const w = 160;
                const h = 160;
                canvas.width = w;
                canvas.height = h;
                const ctx = canvas.getContext("2d");
                ctx.drawImage(img, 0, 0, w, h);
                const data = ctx.getImageData(0, 0, w, h).data;

                let skinPixels = 0;
                let brightPixels = 0;
                let darkPixels = 0;
                const total = w * h;

                for (let i = 0; i < data.length; i += 4) {
                    const r = data[i], g = data[i + 1], b = data[i + 2];
                    const lum = 0.299 * r + 0.587 * g + 0.114 * b;
                    if (lum > 235) brightPixels++;
                    if (lum < 25) darkPixels++;
                    // Heurística RGB para detección de tonos de piel humana
                    if (r > 95 && g > 40 && b > 20 && (Math.max(r, g, b) - Math.min(r, g, b)) > 15 && Math.abs(r - g) > 15 && r > g && r > b) {
                        skinPixels++;
                    }
                }

                callback({
                    width: img.naturalWidth,
                    height: img.naturalHeight,
                    aspectRatio: +(img.naturalWidth / Math.max(1, img.naturalHeight)).toFixed(2),
                    skinRatio: +((skinPixels / total) * 100).toFixed(1),
                    brightRatio: +((brightPixels / total) * 100).toFixed(1),
                    darkRatio: +((darkPixels / total) * 100).toFixed(1)
                });
            };
            img.src = dataUrl;
        }

        function handleImageUpload(event, mode) {
            const file = event.target.files?.[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(e) {
                const dataUrl = e.target.result;
                const base64Data = dataUrl.split(",")[1];
                const mimeType = file.type || "image/png";
                setAuditImage(mode, dataUrl, base64Data, mimeType);
                showToast("Foto cargada. Haz clic en '🔍 Auditar Esta Foto Ahora' para el análisis visual estricto.", "success");
            };
            reader.readAsDataURL(file);
        }

        function setAuditImage(mode, dataUrl, base64Data, mimeType) {
            analyzeImageCanvasMetrics(dataUrl, (metrics) => {
                if (mode === "pre") {
                    appState.preImageMetrics = metrics;
                } else {
                    appState.postImageMetrics = metrics;
                }
            });

            if (mode === "pre") {
                appState.preImageBase64 = base64Data;
                appState.preImageMime = mimeType;
                document.getElementById("preImagePreview").src = dataUrl;
                document.getElementById("preImagePreviewWrapper").classList.remove("hidden");
            } else {
                appState.postImageBase64 = base64Data;
                appState.postImageMime = mimeType;
                document.getElementById("postImagePreview").src = dataUrl;
                document.getElementById("postImagePreviewWrapper").classList.remove("hidden");
            }
        }

        function removeUploadedImage(mode) {
            if (mode === "pre") {
                appState.preImageBase64 = null;
                appState.preImageMetrics = null;
                document.getElementById("preImagePreviewWrapper").classList.add("hidden");
                document.getElementById("preLiveImageInput").value = "";
            } else {
                appState.postImageBase64 = null;
                appState.postImageMetrics = null;
                document.getElementById("postImagePreviewWrapper").classList.add("hidden");
                document.getElementById("postLiveImageInput").value = "";
            }
        }

        // Capturar pantallazo directo de la pantalla del creador (Screen Capture API)
        async function captureScreenForAudit(mode) {
            if (!navigator.mediaDevices || !navigator.mediaDevices.getDisplayMedia) {
                showToast("Tu navegador o contenedor restringe la captura directa. Usa el botón 'Subir Foto / Captura'.", "warning");
                return;
            }
            try {
                const stream = await navigator.mediaDevices.getDisplayMedia({ video: true });
                const video = document.createElement("video");
                video.srcObject = stream;
                await video.play();

                const canvas = document.createElement("canvas");
                canvas.width = Math.min(video.videoWidth, 1280);
                canvas.height = Math.min(video.videoHeight, 720);
                const ctx = canvas.getContext("2d");
                ctx.drawImage(video, 0, 0, canvas.width, canvas.height);

                // Detener transmisión de pantalla inmediatamente después de tomar la foto
                stream.getTracks().forEach(track => track.stop());

                const dataUrl = canvas.toDataURL("image/jpeg", 0.85);
                const base64Data = dataUrl.split(",")[1];
                setAuditImage(mode, dataUrl, base64Data, "image/jpeg");
                showToast("¡Pantallazo capturado con éxito! Lista para auditoría IA.", "success");
            } catch (err) {
                showToast("No se seleccionó pantalla o el permiso fue cancelado. También puedes subir la captura manualmente.", "info");
            }
        }

        // Activar cámara web para revisar vestimenta y escenario antes del LIVE
        async function captureWebcamForAudit(mode) {
            if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
                showToast("Cámara no disponible en este navegador. Usa 'Subir Foto / Captura'.", "warning");
                return;
            }
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" } });
                appState.webcamStream = stream;
                const videoEl = document.getElementById("preWebcamVideo");
                videoEl.srcObject = stream;
                document.getElementById("preWebcamContainer").classList.remove("hidden");
                showToast("Cámara activa. Posiciónate como en tu LIVE y pulsa 'Tomar Foto Ahora'.", "info");
            } catch (err) {
                showToast("Permiso de cámara denegado o bloqueado por el navegador. Usa 'Subir Foto'.", "warning");
            }
        }

        function takeSnapshotFromWebcam(mode) {
            const videoEl = document.getElementById("preWebcamVideo");
            if (!videoEl || !appState.webcamStream) return;
            const canvas = document.createElement("canvas");
            canvas.width = videoEl.videoWidth || 640;
            canvas.height = videoEl.videoHeight || 480;
            const ctx = canvas.getContext("2d");
            ctx.drawImage(videoEl, 0, 0, canvas.width, canvas.height);

            const dataUrl = canvas.toDataURL("image/jpeg", 0.85);
            const base64Data = dataUrl.split(",")[1];
            setAuditImage(mode, dataUrl, base64Data, "image/jpeg");
            stopWebcam(mode);
            showToast("¡Foto de tu cámara capturada! Ahora pulsa 'Auditar mi LIVE ahora'.", "success");
        }

        function stopWebcam(mode) {
            if (appState.webcamStream) {
                appState.webcamStream.getTracks().forEach(t => t.stop());
                appState.webcamStream = null;
            }
            document.getElementById("preWebcamContainer").classList.add("hidden");
        }

        // =====================================================================
        // LLAMADA A GEMINI API CON REINTENTO EXPONENCIAL (TEXTO + VISIÓN + JSON)
        // =====================================================================
        async function callGeminiAPI(systemPrompt, userPrompt, imageBase64 = null, imageMime = "image/jpeg", responseSchema = null) {
            const parts = [{ text: userPrompt }];
            if (imageBase64) {
                parts.push({
                    inlineData: {
                        mimeType: imageMime,
                        data: imageBase64
                    }
                });
            }

            const payload = {
                contents: [{ role: "user", parts }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };

            if (responseSchema) {
                payload.generationConfig = {
                    responseMimeType: "application/json",
                    responseSchema: responseSchema
                };
            }

            const delays = [800, 1600];
            let lastError = null;

            for (const modelName of GEMINI_MODELS) {
                const url = `https://generativelanguage.googleapis.com/v1beta/models/${modelName}:generateContent?key=${apiKey}`;
                for (let attempt = 0; attempt <= delays.length; attempt++) {
                    try {
                        const response = await fetch(url, {
                            method: "POST",
                            headers: { "Content-Type": "application/json" },
                            body: JSON.stringify(payload)
                        });
                        if (!response.ok) throw new Error(`HTTP ${response.status}`);
                        const result = await response.json();
                        const text = result?.candidates?.[0]?.content?.parts?.[0]?.text;
                        if (!text) throw new Error("Empty response");
                        return responseSchema ? JSON.parse(text) : text;
                    } catch (err) {
                        lastError = err;
                        if (attempt < delays.length) {
                            await new Promise(res => setTimeout(res, delays[attempt]));
                        }
                    }
                }
            }
            throw lastError || new Error("No se pudo conectar con el motor IA");
        }

        // =====================================================================
        // MOTOR 1: EJECUTAR AUDITORÍA PRE-LIVE (EL ANTES + AUDITORÍA VISUAL ESTRICTA)
        // =====================================================================
        async function runPreLiveAudit(onlyPhotoTrigger = false) {
            const checkedItems = Array.from(document.querySelectorAll(".pre-check:checked")).map(cb => cb.value);
            const description = document.getElementById("preLiveText").value.trim();

            if (checkedItems.length === 0 && !description && !appState.preImageBase64) {
                showToast("Por favor sube una foto/captura, describe lo que planeas hacer o marca una opción del checklist.", "warning");
                return;
            }

            const btn = document.getElementById("btnRunPreAudit");
            const placeholder = document.getElementById("preLivePlaceholder");
            const output = document.getElementById("preLiveOutput");

            btn.disabled = true;
            btn.innerHTML = `<i class="fa-solid fa-circle-notch fa-spin"></i> ESCANEANDO IMAGEN Y NORMAS CON VISIÓN FORENSE IA...`;
            placeholder.classList.add("hidden");
            output.classList.remove("hidden");
            output.innerHTML = `
                <div class="p-8 text-center space-y-3">
                    <i class="fa-solid fa-microscope fa-bounce text-3xl text-ttCyan"></i>
                    <p class="text-sm font-bold text-white">${appState.preImageBase64 ? "Inspeccionando píxel por píxel tu foto subida (Vestimenta, Objetos y Validación Anti-Foto Random)..." : "Analizando dinámica, palabras y riesgo del 20% de regalos..."}</p>
                    <p class="text-xs text-gray-400">Verificando contra la Guía de Seguridad de TikTok LIVE y el Sistema de Puntuación de 100 Puntos.</p>
                </div>
            `;

            const systemPrompt = `Eres el Auditor Forense de Visión Artificial y Seguridad de TikTok LIVE para una Agencia Oficial de Creadores.
Tu trabajo es auditar con RIGOR IMPLACABLE y CERO AMBIGÜEDAD lo que el creador planea hacer y, sobre todo, LA IMAGEN O CAPTURA DE PANTALLA SUBIDA.

REGLA CRÍTICA ANTI-FOTOS RANDOM (OBLIGATORIA):
- Si el usuario subió una imagen, primero debes verificar qué aparece literalmente en ella.
- Si la imagen es una "FOTO RANDOM" o ajena a una transmisión de TikTok LIVE (por ejemplo: un meme, un plato de comida solo, un paisaje, un perro/gato solo, un dibujo/anime, una foto de un objeto suelto o zapato, una captura de pantalla de código/WhatsApp/escritorio de Windows sin cámara de creador ni interfaz de TikTok LIVE, una imagen en blanco/negro/borrosa, o cualquier foto donde NO se vea un creador/streamer, su vestimenta, su set de transmisión ni una captura real de TikTok LIVE):
  * TIENES ESTRICTAMENTE PROHIBIDO decir que "todo está bien" o "SEGURO".
  * Debes devolver obligatoriamente verdictStatus = "FOTO_RANDOM_INVALIDA".
  * En verdictTitle debes poner: "🚫 IMAGEN RECHAZADA: FOTO RANDOM O AJENA A UN TIKTOK LIVE".
  * En forensicSceneDescription debes describir con exactitud literal qué hay en la foto subida y explicar por qué no es válida para auditar un LIVE.

SI LA IMAGEN SÍ CORRESPONDE A UN CREADOR, PERSONA, OUTFIT, SET DE GRABACIÓN O CAPTURA DE TIKTOK LIVE:
Evalúa sin piedad los siguientes 6 puntos forenses:
1. forensicSceneDescription: Describe literalmente qué ves en la foto (personas, postura, fondo, iluminación, textos en pantalla).
2. forensicLiveContextValidation: Indica claramente si es un encuadre válido de LIVE / creador o si es una foto random inválida.
3. forensicClothingAndSkin: Evalúa vestimenta y piel visible (escotes pronunciados, lencería, ropa interior, bikini fuera de piscina, torso masculino sin camisa de cerca, transparencias o ángulos sugestivos que activan la retención del 20% de regalos).
4. forensicProhibitedObjects: Busca humo, vapers (incluso apagados en mano o mesa), cigarrillos, botellas de alcohol, tijeras, cuchillos, agujas, objetos cortopunzantes o armas de juguete/reales.
5. forensicSafetyAndEnvironment: Detecta si hay niños/menores de edad en cámara (bloqueo grave), si está conduciendo un vehículo, o si muestra datos bancarios/QR/redes externas.
6. Calcula el riesgo exacto de perder el 20% de los regalos y cuántos puntos de Reputación (de 100) perdería.`;

            const userPrompt = `Datos enviados por el creador para auditoría Pre-LIVE:
- ¿Activó auditoría directa de foto?: ${onlyPhotoTrigger ? "SÍ, prioriza al 100% el análisis forense de la imagen subida." : "Evaluación integral"}
- Elementos marcados en la Zona de Cumplimiento: ${checkedItems.length > 0 ? checkedItems.join("; ") : "Ninguno marcado"}
- Descripción escrita por el creador: "${description || "Sin descripción de texto (AUDITAR ESTRICTAMENTE LA IMAGEN SUBIDA)"}"
- ¿Hay imagen adjunta?: ${appState.preImageBase64 ? "SÍ. Analiza visualmente la imagen adjunta con rigor quirúrgico. Si es una foto random que no es un creador ni un LIVE, márcala como FOTO_RANDOM_INVALIDA." : "NO se adjuntó imagen."}`;

            const schema = {
                type: "OBJECT",
                properties: {
                    verdictStatus: { type: "STRING", description: "FOTO_RANDOM_INVALIDA, PELIGRO_ALTO, RIESGO_MEDIO, o SEGURO" },
                    verdictTitle: { type: "STRING", description: "Título contundente del veredicto" },
                    gift20RiskLevel: { type: "STRING", description: "Riesgo de retención del 20% de regalos o N/A por Foto Random" },
                    reputationDeduction: { type: "STRING", description: "Puntos de reputación en riesgo (Base 100)" },
                    sanctionTier: { type: "STRING", description: "Nivel de sanción (Nivel 1, Nivel 2, Nivel 3, Sin sanción, o Imagen Inválida)" },
                    concreteExplanation: { type: "STRING", description: "Diagnóstico directo y sin rodeos" },
                    forensicSceneDescription: { type: "STRING", description: "1. Qué hay exactamente en la imagen subida (descripción literal)" },
                    forensicLiveContextValidation: { type: "STRING", description: "2. Validación de contexto LIVE (¿Es un LIVE/creador real o es una foto random?)" },
                    forensicClothingAndSkin: { type: "STRING", description: "3. Auditoría de vestimenta, escote y piel visible" },
                    forensicProhibitedObjects: { type: "STRING", description: "4. Detección de vapers, humo, tijeras, cuchillos, armas o alcohol" },
                    forensicSafetyAndEnvironment: { type: "STRING", description: "5. Seguridad y entorno (menores de edad, conducción, QR/dinero)" },
                    exactCorrection: { type: "STRING", description: "Qué debe hacer o corregir exactamente el creador" }
                },
                required: [
                    "verdictStatus",
                    "verdictTitle",
                    "gift20RiskLevel",
                    "reputationDeduction",
                    "sanctionTier",
                    "concreteExplanation",
                    "forensicSceneDescription",
                    "forensicLiveContextValidation",
                    "forensicClothingAndSkin",
                    "forensicProhibitedObjects",
                    "forensicSafetyAndEnvironment",
                    "exactCorrection"
                ]
            };

            try {
                const aiResult = await callGeminiAPI(systemPrompt, userPrompt, appState.preImageBase64, appState.preImageMime, schema);
                renderPreLiveResult(aiResult, !!appState.preImageBase64);
            } catch (err) {
                const fallback = buildDeterministicPreLiveAudit(checkedItems, description, !!appState.preImageBase64, appState.preImageMetrics);
                renderPreLiveResult(fallback, !!appState.preImageBase64);
            } finally {
                btn.disabled = false;
                btn.innerHTML = `<i class="fa-solid fa-magnifying-glass-chart"></i> AUDITAR MI LIVE AHORA (PREVENIR SANCIÓN Y -20% REGALOS)`;
            }
        }

        function buildDeterministicPreLiveAudit(checkedItems, description, hasImage, metrics) {
            const textLower = (description + " " + checkedItems.join(" ")).toLowerCase();

            // Si subió una imagen y el análisis de píxeles muestra ausencia de rostro/piel humana (< 2.5%) o captura de interfaz en blanco/negro, rechazar como Foto Random
            if (hasImage && metrics && (metrics.skinRatio < 2.5 || metrics.brightRatio > 70 || metrics.darkRatio > 80) && checkedItems.length === 0 && !description) {
                return {
                    verdictStatus: "FOTO_RANDOM_INVALIDA",
                    verdictTitle: "🚫 IMAGEN RECHAZADA (FOTO RANDOM O AJENA A UN LIVE)",
                    gift20RiskLevel: "INVÁLIDO POR FOTO RANDOM (Sube una captura real de tu cámara o TikTok LIVE)",
                    reputationDeduction: "No evaluable hasta subir encuadre real del creador",
                    sanctionTier: "Imagen no corresponde a un set de transmisión ni a un creador en cámara",
                    concreteExplanation: "El escáner visual detectó que la imagen subida es una foto o captura aleatoria que NO muestra a un creador, su vestimenta ni una transmisión activa de TikTok LIVE. Nunca aprobaremos una foto random como segura.",
                    forensicSceneDescription: `Imagen de ${metrics.width}x${metrics.height}px con apenas ${metrics.skinRatio}% de presencia de piel/rostro humano y ${metrics.brightRatio}% de áreas planas/captura externa.`,
                    forensicLiveContextValidation: "❌ RECHAZADO (Foto Random / Captura ajena a un encuadre de TikTok LIVE).",
                    forensicClothingAndSkin: "No se detecta un creador en posición de transmisión para auditar vestimenta.",
                    forensicProhibitedObjects: "Debes mostrar tu escritorio/encuadre real para verificar que no existan vapers, tijeras ni objetos cortopunzantes.",
                    forensicSafetyAndEnvironment: "Sin contexto de sala de LIVE.",
                    exactCorrection: "Toma una foto real con tu cámara ('Probar mi Cámara/Set') mostrando cómo vas a salir vestido/a y tu fondo, o sube un pantallazo real de tu transmisión en TikTok LIVE."
                };
            }

            if (hasImage && metrics && metrics.skinRatio > 38) {
                return {
                    verdictStatus: "RIESGO_MEDIO",
                    verdictTitle: "⚠️ ALERTA VISUAL: EXCESO DE PIEL VISIBLE O VESTIMENTA RIESGOSA DETECTADA",
                    gift20RiskLevel: "ALTO RIESGO (85%) DE QUE TIKTOK TE QUITE EL 20% DE TUS REGALOS",
                    reputationDeduction: "-3 a -7 pts de tu Puntuación de Reputación (Base 100)",
                    sanctionTier: "Nivel 1 (Baja de visibilidad) a Nivel 2 (Retención del 20% de regalos / Bloqueo 3-7 días)",
                    concreteExplanation: "El escáner visual detectó un alto porcentaje de exposición de piel en el encuadre (${metrics.skinRatio}%). La IA de TikTok LIVE penaliza escotes pronunciados, tops muy cortos, ropa interior visible o torso sin camisa aplicando la retención del 20% de diamantes.",
                    forensicSceneDescription: `Encuadre de ${metrics.width}x${metrics.height}px con alta exposición de tonos de piel (${metrics.skinRatio}% del cuadro).`,
                    forensicLiveContextValidation: "⚠️ Encuadre con persona/piel visible en zona de riesgo de moderación.",
                    forensicClothingAndSkin: `Alta proporción de piel detectada (${metrics.skinRatio}%). Riesgo de sanción por 'Contenido sexualmente sugerente o vestimenta reveladora'.`,
                    forensicProhibitedObjects: "Verifica además que no haya vapers, cigarrillos ni objetos cortopunzantes cerca de las manos.",
                    forensicSafetyAndEnvironment: "Aleja ligeramente la cámara y cubre hombros/pecho para evitar un falso positivo del bot.",
                    exactCorrection: "Usa una prenda que cubra completamente el pecho y abdomen, coloca la cámara del pecho hacia arriba y vuelve a escanear la foto antes de iniciar el LIVE."
                };
            }

            const isCritical = /rifa|sorteo|paypal|nequi|dinero|efectivo|dolar|desnud|lenceria|arma|pistola|menor|niño/.test(textLower);
            const isHighRisk = checkedItems.length > 0 || /vape|humo|cigarr|cuchill|tijera|huevo|castigo|golpe|bikini|escote|top|groser|insult/.test(textLower);

            if (isCritical) {
                return {
                    verdictStatus: "PELIGRO_ALTO",
                    verdictTitle: "🚫 PROHIBIDO: INFRACCIÓN GRAVE DETECTADA (NO TRANSMITAS ASÍ)",
                    gift20RiskLevel: "PELIGRO CRÍTICO: RETENCIÓN DEL 20% AL 100% DE GANANCIAS (NIVEL 3)",
                    reputationDeduction: "-5 a -7 pts por infracción (Hasta -10 pts en el día)",
                    sanctionTier: "Nivel 2 (Bloqueo 3-7 días) a Nivel 3 (TikTok quita ganancias totales sin devolución)",
                    concreteExplanation: "Lo que describes infringe directamente las Normas de la Comunidad de TikTok LIVE. Mencionar dinero/rifas por regalos, mostrar menores sin supervisión o usar vestimenta íntima activa el bloqueo automático a mitad de pantalla.",
                    forensicSceneDescription: hasImage ? "Imagen adjunta vinculada a una dinámica de riesgo crítico prohibida por TikTok LIVE." : "Sin imagen adjunta (evaluado por descripción y checklist).",
                    forensicLiveContextValidation: "⚠️ Dinámica de alto peligro para la cuenta.",
                    forensicClothingAndSkin: "Prohibido lencería, desnudez parcial o vestimenta íntima en cámara.",
                    forensicProhibitedObjects: "Prohibido armas reales/juguete, objetos cortopunzantes y papeletas de rifas por dinero.",
                    forensicSafetyAndEnvironment: "Prohibido menores de edad solos en pantalla o mostrar cuentas bancarias/PayPal/Nequi.",
                    exactCorrection: "1) Elimina cualquier mención a sorteos de dinero, PayPal o efectivo (usa solo Cofres de TikTok). 2) Usa vestimenta casual completa. 3) Retira cualquier objeto prohibido del escritorio antes de iniciar."
                };
            } else if (isHighRisk) {
                return {
                    verdictStatus: "RIESGO_MEDIO",
                    verdictTitle: "⚠️ ALTO RIESGO DE QUE TE QUITEN EL 20% DE TUS REGALOS O BAJEN PUNTOS",
                    gift20RiskLevel: "ALTO RIESGO (85%) DE RETENCIÓN DEL 20% DE REGALOS / DIAMANTES",
                    reputationDeduction: "-2 a -5 pts de tu Puntuación de Reputación (Base 100)",
                    sanctionTier: "Nivel 1 (Restricción de Visibilidad) a Nivel 2 (Suspensión de 3 a 7 días + Retención 20%)",
                    concreteExplanation: "Detectamos elementos de la Zona de Cumplimiento en riesgo (vapeo/humo, tijeras/cuchillos, vestimenta ajustada/escote o retos físicos de batalla PK como romper huevos). La IA de TikTok sanciona esto con avisos a mitad de pantalla y retención del 20% de diamantes.",
                    forensicSceneDescription: hasImage ? "Imagen adjunta analizada con elementos de riesgo medio/alto." : "Sin imagen adjunta (evaluado por texto/checklist).",
                    forensicLiveContextValidation: "Encuadre sujeto a moderación automática estricta.",
                    forensicClothingAndSkin: "Evita tops deportivos muy cortos, escotes pronunciados o ropa interior visible.",
                    forensicProhibitedObjects: "Riesgo detectado por vaper/humo o herramientas cortopunzantes (tijeras/cuchillos).",
                    forensicSafetyAndEnvironment: "Evita penitencias físicas o humillantes en batallas PK.",
                    exactCorrection: "1) Guarda cualquier vaper, encendedor, cuchillo o tijera fuera del cuarto. 2) Si haces batallas PK, cambia el castigo físico (huevos/golpes) por penitencias de canto, maquillaje divertido o filtros. 3) Usa una prenda que cubra bien el torso."
                };
            } else {
                return {
                    verdictStatus: "SEGURO",
                    verdictTitle: "✅ 100% SEGURO PARA TRANSMITIR EN TIKTOK LIVE",
                    gift20RiskLevel: "RIESGO BAJO (0% - Tus regalos y diamantes están protegidos al 100%)",
                    reputationDeduction: "0 pts deducidos (+2 pts si transmites 10+ minutos sin infracción)",
                    sanctionTier: "Zona Segura (Mantienes 60–100 pts con todas las funciones disponibles)",
                    concreteExplanation: "Tu dinámica cumple con la Guía Oficial de Seguridad de TikTok LIVE. No hay palabras prohibidas, ni objetos peligrosos, ni coerción de regalos.",
                    forensicSceneDescription: hasImage ? "Encuadre de creador válido y limpio, sin objetos prohibidos detectados." : "Sin imagen adjunta (sube una foto de tu set o cámara si deseas auditar tu vestimenta y fondo).",
                    forensicLiveContextValidation: "✅ Válido para transmisión en TikTok LIVE.",
                    forensicClothingAndSkin: "Sin exposición riesgosa detectada.",
                    forensicProhibitedObjects: "Ningún vaper, humo ni objeto cortopunzante detectado.",
                    forensicSafetyAndEnvironment: "Entorno seguro y apto para monetización al 100%.",
                    exactCorrection: "Puedes iniciar tu LIVE con confianza. Recuerda: si durante una batalla PK tu rival infringe las normas, corta la conexión de inmediato para proteger tu cuenta."
                };
            }
        }

        function renderPreLiveResult(res, hadImage = false) {
            const output = document.getElementById("preLiveOutput");
            let badgeColors = "bg-emerald-500/20 border-emerald-500 text-emerald-300";
            let icon = "fa-circle-check text-emerald-400";

            if (res.verdictStatus === "FOTO_RANDOM_INVALIDA") {
                badgeColors = "bg-rose-600/30 border-rose-500 text-rose-200 animate-glow";
                icon = "fa-ban text-rose-400";
            } else if (res.verdictStatus === "PELIGRO_ALTO") {
                badgeColors = "bg-rose-600/25 border-rose-500 text-rose-200";
                icon = "fa-radiation text-rose-500";
            } else if (res.verdictStatus === "RIESGO_MEDIO") {
                badgeColors = "bg-amber-500/20 border-amber-500 text-amber-200";
                icon = "fa-triangle-exclamation text-amber-400";
            }

            output.innerHTML = `
                <div class="p-4 rounded-2xl border-2 ${badgeColors} space-y-1.5">
                    <div class="text-[11px] font-black uppercase tracking-wider flex items-center gap-1.5">
                        <i class="fa-solid ${icon}"></i> Veredicto Oficial Pre-LIVE
                    </div>
                    <div class="text-base sm:text-lg font-black text-white leading-snug">${res.verdictTitle}</div>
                </div>

                <!-- TARJETA DESTACADA DE EVIDENCIA VISUAL FORENSE (SIEMPRE VISIBLE CUANDO HAY FOTO O RECHAZO DE FOTO RANDOM) -->
                <div class="p-4 rounded-2xl ${res.verdictStatus === 'FOTO_RANDOM_INVALIDA' ? 'bg-rose-950/50 border-2 border-rose-500/80' : 'bg-purple-950/30 border border-purple-400/40'} space-y-2.5 text-xs">
                    <div class="font-black text-purple-300 uppercase tracking-wider flex items-center justify-between">
                        <span><i class="fa-solid fa-eye mr-1.5 text-ttCyan"></i> 👁️ Evidencia Visual Detectada en tu Foto</span>
                        <span class="text-[10px] px-2 py-0.5 rounded bg-black/50 text-white">${hadImage ? "Escaneo Multimodal IA" : "Análisis de Contexto"}</span>
                    </div>
                    <div class="grid grid-cols-1 gap-2 pt-1">
                        <div class="p-2.5 rounded-xl bg-black/60 border border-white/10">
                            <span class="font-extrabold text-ttCyan block text-[11px]">1. ¿Qué hay exactamente en la imagen?:</span>
                            <span class="text-gray-200">${res.forensicSceneDescription || "No se subió imagen."}</span>
                        </div>
                        <div class="p-2.5 rounded-xl bg-black/60 border border-white/10">
                            <span class="font-extrabold text-amber-400 block text-[11px]">2. Validación de Contexto TikTok LIVE (Anti-Foto Random):</span>
                            <span class="text-white font-semibold">${res.forensicLiveContextValidation || "Evaluado"}</span>
                        </div>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-2">
                            <div class="p-2.5 rounded-xl bg-black/60 border border-white/10">
                                <span class="font-extrabold text-pink-400 block text-[11px]">3. Vestimenta y Piel:</span>
                                <span class="text-gray-200">${res.forensicClothingAndSkin || "Sin hallazgos."}</span>
                            </div>
                            <div class="p-2.5 rounded-xl bg-black/60 border border-white/10">
                                <span class="font-extrabold text-rose-400 block text-[11px]">4. Objetos Prohibidos:</span>
                                <span class="text-gray-200">${res.forensicProhibitedObjects || "Sin hallazgos."}</span>
                            </div>
                        </div>
                        <div class="p-2.5 rounded-xl bg-black/60 border border-white/10">
                            <span class="font-extrabold text-emerald-400 block text-[11px]">5. Seguridad y Entorno (Menores, Conducción, QR):</span>
                            <span class="text-gray-200">${res.forensicSafetyAndEnvironment || "Entorno estándar."}</span>
                        </div>
                    </div>
                </div>

                <!-- Indicadores de Riesgo 20% Regalos y Puntuación 100 -->
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
                    <div class="p-3 rounded-xl bg-black/60 border border-amber-500/40">
                        <div class="text-[10px] font-extrabold uppercase text-amber-400 flex items-center gap-1">
                            <i class="fa-solid fa-percent"></i> 6. Riesgo Retención 20% Regalos
                        </div>
                        <div class="text-xs font-extrabold text-white mt-1">${res.gift20RiskLevel}</div>
                    </div>
                    <div class="p-3 rounded-xl bg-black/60 border border-ttCyan/40">
                        <div class="text-[10px] font-extrabold uppercase text-ttCyan flex items-center gap-1">
                            <i class="fa-solid fa-gauge-high"></i> Impacto Reputación (Base 100)
                        </div>
                        <div class="text-xs font-extrabold text-white mt-1">${res.reputationDeduction}</div>
                    </div>
                </div>

                <div class="p-3.5 rounded-xl bg-black/50 border border-white/10 space-y-2 text-xs">
                    <div>
                        <span class="font-extrabold text-ttCyan uppercase text-[11px]">Nivel de Escala TikTok:</span>
                        <p class="text-white font-semibold mt-0.5">${res.sanctionTier}</p>
                    </div>
                    <div class="border-t border-white/10 pt-2">
                        <span class="font-extrabold text-gray-300 uppercase text-[11px]">Diagnóstico Concreto (Sin Ambigüedad):</span>
                        <p class="text-gray-200 mt-0.5 leading-relaxed">${res.concreteExplanation}</p>
                    </div>
                </div>

                <!-- Corrección Exacta -->
                <div class="p-3.5 rounded-xl bg-emerald-500/10 border border-emerald-500/40 text-xs space-y-1">
                    <div class="font-extrabold text-emerald-400 uppercase flex items-center gap-1.5">
                        <i class="fa-solid fa-wand-magic-sparkles"></i> Qué debes hacer exactamente antes de salir en LIVE:
                    </div>
                    <p class="text-gray-100 leading-relaxed">${res.exactCorrection}</p>
                </div>

                <!-- Recordatorio Obligatorio de Apelación y Manager -->
                <div class="p-3 rounded-xl bg-ttPink/15 border border-ttPink/40 text-[11px] text-gray-200 space-y-1.5">
                    <div class="font-extrabold text-ttCyan flex items-center gap-1.5">
                        <i class="fa-solid fa-shield-heart text-ttPink"></i> Protocolo de Blindaje de Agencia:
                    </div>
                    <p>
                        Si aplicas estas correcciones y aun así TikTok te lanza un aviso <strong>a mitad de pantalla</strong> por error de su IA: <strong>1° APELA de inmediato en la app.</strong> <strong>2°</strong> Si no te aprueban la apelación pero estás 100% seguro de que fue injusto, <button onclick="openManagerModal()" class="text-ttCyan font-bold underline">pídenos ayuda aquí</button> para que un <strong>Manager de TikTok</strong> revise tu caso y nos dé solución.
                    </p>
                </div>
            `;
        }

        // =====================================================================
        // MOTOR 2: JUEZ POST-LIVE (¿TÚ O TIKTOK TIENEN LA RAZÓN? + APELACIÓN)
        // =====================================================================
        async function runPostLiveJudge(onlyPhotoTrigger = false) {
            const location = document.querySelector('input[name="postLocation"]:checked')?.value || "mitad_pantalla";
            const sanctionType = document.getElementById("postSanctionType").value;
            const tiktokReason = document.getElementById("postTikTokReason").value.trim();
            const creatorStory = document.getElementById("postCreatorStory").value.trim();

            if (location === "en_comentarios") {
                checkAlertLocation();
                const placeholder = document.getElementById("postLivePlaceholder");
                const output = document.getElementById("postLiveOutput");
                placeholder.classList.add("hidden");
                output.classList.remove("hidden");
                output.innerHTML = `
                    <div class="p-5 rounded-2xl bg-emerald-500/15 border-2 border-emerald-400 space-y-2 text-xs">
                        <div class="text-base font-black text-emerald-300 flex items-center gap-2">
                            <i class="fa-solid fa-face-laugh-wink"></i> FALSA ALARMA: NO FUISTE SANCIONADO POR TIKTOK
                        </div>
                        <p class="text-gray-200 leading-relaxed">
                            Como el mensaje apareció <strong>en los comentarios del chat</strong> y NO <strong>a mitad de pantalla</strong>, se trata de un espectador troll escribiendo textos falsos. No perdiste puntos de reputación ni el 20% de tus regalos. Silencia o bloquea al usuario y sigue transmitiendo.
                        </p>
                    </div>
                `;
                return;
            }

            if (!tiktokReason && !creatorStory && !appState.postImageBase64) {
                showToast("Escribe el motivo de la sanción, lo que ocurrió o adjunta la captura para auditar tu caso.", "warning");
                return;
            }

            const btn = document.getElementById("btnRunPostJudge");
            const placeholder = document.getElementById("postLivePlaceholder");
            const output = document.getElementById("postLiveOutput");

            btn.disabled = true;
            btn.innerHTML = `<i class="fa-solid fa-circle-notch fa-spin"></i> EVALUANDO EVIDENCIA Y GENERANDO DEFENSA...`;
            placeholder.classList.add("hidden");
            output.classList.remove("hidden");
            output.innerHTML = `
                <div class="p-8 text-center space-y-3">
                    <i class="fa-solid fa-scale-balanced fa-bounce text-3xl text-ttPink"></i>
                    <p class="text-sm font-bold text-white">Analizando si TikTok tuvo la razón o si fue un Falso Positivo...</p>
                    <p class="text-xs text-gray-400">Redactando apelación técnica y expediente para Manager de TikTok.</p>
                </div>
            `;

            const systemPrompt = `Eres el Juez Auditor de Sanciones de TikTok LIVE para una Agencia Oficial.
Evalúa sin ambigüedad quién tiene la razón: EL CREADOR (Falso positivo de TikTok) o TIKTOK (Infracción real de las normas).
Si se adjunta una imagen que es una foto random ajena a una notificación o transmisión de TikTok LIVE, indícalo claramente en imageForensicNote.
Siempre recuerda la regla de oro: 1) Primero apelar en la app con el texto técnico. 2) Si TikTok rechaza la apelación pero el creador está 100% seguro de que fue injusto, escalar con un Manager Oficial de TikTok.`;

            const userPrompt = `Caso Post-LIVE:
- Ubicación del aviso: ${location}
- Tipo de sanción recibida: ${sanctionType}
- Motivo que puso TikTok: "${tiktokReason || "No especificado"}"
- Relato del creador: "${creatorStory || "Analizar captura adjunta"}"
- ¿Adjuntó captura?: ${appState.postImageBase64 ? "SÍ, analiza la captura adjunta." : "NO"}`;

            const schema = {
                type: "OBJECT",
                properties: {
                    whoIsRight: { type: "STRING", description: "CREADOR_RAZON, TIKTOK_RAZON, o FOTO_RANDOM" },
                    verdictHeadline: { type: "STRING", description: "Titular directo de quién tiene la razón" },
                    sanctionClassification: { type: "STRING", description: "Explicación clara de si es Restricción de Visibilidad vs Sanción Dura (-20% regalos, 3-7 días o Nivel 3)" },
                    reputationImpact: { type: "STRING", description: "Puntos descontados y cómo recuperarlos (+2 pts/día o apelación exitosa)" },
                    concreteAnalysis: { type: "STRING", description: "Explicación directa de por qué ocurrió la sanción" },
                    imageForensicNote: { type: "STRING", description: "Qué se observa exactamente en la captura adjunta" },
                    appealText: { type: "STRING", description: "Texto formal en primera persona listo para copiar y pegar en la apelación de TikTok" }
                },
                required: [
                    "whoIsRight",
                    "verdictHeadline",
                    "sanctionClassification",
                    "reputationImpact",
                    "concreteAnalysis",
                    "imageForensicNote",
                    "appealText"
                ]
            };

            try {
                const aiJudge = await callGeminiAPI(systemPrompt, userPrompt, appState.postImageBase64, appState.postImageMime, schema);
                renderPostLiveResult(aiJudge);
            } catch (err) {
                const fallback = buildDeterministicPostLiveJudge(sanctionType, tiktokReason, creatorStory, !!appState.postImageBase64);
                renderPostLiveResult(fallback);
            } finally {
                btn.disabled = false;
                btn.innerHTML = `<i class="fa-solid fa-scale-balanced"></i> VERIFICAR QUIÉN TIENE LA RAZÓN Y GENERAR DEFENSA`;
            }
        }

        function buildDeterministicPostLiveJudge(sanctionType, tiktokReason, creatorStory, hasImage) {
            const combined = (tiktokReason + " " + creatorStory).toLowerCase();
            const admittedViolation = /vape|fume|fumé|humo|cigarr|rifa|sorteo|paypal|nequi|insult|groser|desnud|lenceria|cuchillo en la cara/.test(combined);

            const typeMap = {
                visibilidad_leve: "NIVEL 1 (Restricción de Visibilidad): Puedes continuar el LIVE, pero no sales en el feed Para Ti temporalmente y pierdes de -1 a -3 pts.",
                retencion_20_regalos: "SANCIÓN DURA ECONÓMICA (-20% de Regalos): TikTok retiene el 20% de los diamantes por detectar riesgo en vestimenta, vocabulario, pedir regalos en exceso o co-host infractor.",
                bloqueo_3_7_dias: "SANCIÓN DURA NIVEL 2 (Bloqueo de 3 a 7 días): Suspensión temporal del acceso a LIVE y deducción de -4 a -7 pts de Reputación.",
                perdida_total_nivel_3: "SANCIÓN CRÍTICA NIVEL 3 (Exceso Detectado): TikTok quita las ganancias totales sin devolución y aplica deducción severa.",
                baja_puntos_reputacion: "IMPACTO EN PUNTUACIÓN DE REPUTACIÓN (Base 100): Al bajar de 60 pts pierdes OBS/StreamElements; al bajar de 40 pts pierdes PK y Monetización."
            };

            const appealScript = `Hola equipo de Seguridad de TikTok LIVE. Presento apelación formal respecto a la notificación por "${tiktokReason || "supuesta infracción de normas"}" recibida a mitad de pantalla. Durante mi transmisión estuve cumpliendo estrictamente la Guía de Seguridad de TikTok LIVE: ${creatorStory || "realizando contenido legítimo, seguro y sin infringir ninguna política comunitaria"}. Solicito respetuosamente una revisión humana del fragmento para levantar la sanción y restaurar mis puntos de Reputación del Creador. Muchas gracias.`;

            if (admittedViolation) {
                return {
                    whoIsRight: "TIKTOK_RAZON",
                    verdictHeadline: "⚠️ TIKTOK TIENE LA RAZÓN SEGÚN LA NORMA (PERO IGUAL DEBES APELAR)",
                    sanctionClassification: typeMap[sanctionType] || typeMap.visibilidad_leve,
                    reputationImpact: "Deducción de -3 a -7 pts (Tope -10 pts/día). Recuperas +2 pts por día transmitiendo 10+ mins sin infracciones o con tareas educativas.",
                    concreteAnalysis: "En tu relato aparece un elemento prohibido por la Zona de Cumplimiento (humo/vapeo, rifas de dinero, insultos o exposición riesgosa). El sistema automático actuó bajo la regla oficial.",
                    imageForensicNote: hasImage ? "Captura adjunta registrada para expediente." : "Sin captura adjunta.",
                    appealText: appealScript
                };
            }

            return {
                whoIsRight: "CREADOR_RAZON",
                verdictHeadline: "✅ TÚ TIENES LA RAZÓN: FALSO POSITIVO DE LA IA DE TIKTOK",
                sanctionClassification: typeMap[sanctionType] || typeMap.visibilidad_leve,
                reputationImpact: "Si tu apelación es aprobada, TikTok te devuelve automáticamente los puntos descontados (1 a 7 pts).",
                concreteAnalysis: "El bot de visión o audio de TikTok interpretó por error un objeto cotidiano (como tijeras de manualidades, un termo o una prenda normal) como una infracción. Debes apelar de inmediato y, si el bot rechaza la apelación, escalarlo con nuestro Manager de TikTok.",
                imageForensicNote: hasImage ? "Captura recibida y lista para adjuntar al Manager de TikTok." : "Te recomendamos tomar captura del aviso a mitad de pantalla o de tu Estado de Reputación.",
                appealText: appealScript
            };
        }

        function renderPostLiveResult(res) {
            const output = document.getElementById("postLiveOutput");
            appState.lastAppealText = res.appealText || "";
            appState.lastJudgeSummary = `${res.verdictHeadline} — ${res.concreteAnalysis}`;

            const isCreatorRight = res.whoIsRight === "CREADOR_RAZON";
            const bannerClass = isCreatorRight
                ? "bg-emerald-500/20 border-emerald-400 text-emerald-200"
                : "bg-amber-500/20 border-amber-400 text-amber-200";

            output.innerHTML = `
                <div class="p-4 rounded-2xl border-2 ${bannerClass} space-y-1">
                    <div class="text-[11px] font-black uppercase tracking-wider">Dictamen Oficial del Juez IA</div>
                    <div class="text-base sm:text-lg font-black text-white">${res.verdictHeadline}</div>
                </div>

                <div class="p-3.5 rounded-xl bg-black/60 border border-white/10 space-y-2 text-xs">
                    <div>
                        <span class="font-extrabold text-ttCyan uppercase text-[11px]">Diferenciación de Sanción:</span>
                        <p class="text-gray-200 mt-0.5">${res.sanctionClassification}</p>
                    </div>
                    <div class="border-t border-white/10 pt-2">
                        <span class="font-extrabold text-amber-400 uppercase text-[11px]">Impacto en Puntuación (100 Pts):</span>
                        <p class="text-gray-200 mt-0.5">${res.reputationImpact}</p>
                    </div>
                    <div class="border-t border-white/10 pt-2">
                        <span class="font-extrabold text-white uppercase text-[11px]">Por qué ocurrió:</span>
                        <p class="text-gray-300 mt-0.5 leading-relaxed">${res.concreteAnalysis}</p>
                    </div>
                </div>

                <!-- Paso 1: Texto de Apelación -->
                <div class="p-3.5 rounded-xl bg-ttCyan/10 border border-ttCyan/40 space-y-2 text-xs">
                    <div class="flex items-center justify-between">
                        <span class="font-extrabold text-ttCyan uppercase">1° Paso Obligatorio: Apelar en TikTok</span>
                        <button type="button" onclick="copyTextToClipboard(appState.lastAppealText, '¡Texto de apelación copiado! Pégalo en TikTok.')" class="px-2.5 py-1 rounded-lg bg-ttCyan text-black font-extrabold text-[11px]">
                            <i class="fa-solid fa-copy mr-1"></i> Copiar Apelación
                        </button>
                    </div>
                    <p class="p-2.5 rounded-lg bg-black/70 border border-white/10 text-gray-200 italic select-all">${res.appealText}</p>
                </div>

                <!-- Paso 2: Escalar a Manager de TikTok -->
                <div class="p-4 rounded-xl bg-ttPink/15 border-2 border-ttPink space-y-2.5 text-xs">
                    <div class="font-extrabold text-white flex items-center gap-1.5 text-sm">
                        <i class="fa-solid fa-headset text-ttCyan"></i> 2° ¿No te aprobaron la apelación pero estás 100% seguro de que fue INJUSTO?
                    </div>
                    <p class="text-gray-200 leading-relaxed">
                        Si TikTok rechaza tu apelación automática y estás <strong>100% seguro/a de que fue injusto</strong>, pídenos ayuda inmediatamente. Nosotros enviaremos tu caso directo a un <strong>Manager de TikTok</strong> para que lo revise manualmente y nos dé solución.
                    </p>
                    <button type="button" onclick="openManagerWithJudgeData()" class="w-full py-2.5 px-4 rounded-xl tt-btn-primary text-white font-extrabold text-xs flex items-center justify-center gap-2">
                        <i class="fa-solid fa-user-shield"></i> PEDIR AYUDA PARA ESCALAR CON MANAGER DE TIKTOK
                    </button>
                </div>
            `;
        }

        function openManagerWithJudgeData() {
            if (appState.lastJudgeSummary) {
                document.getElementById("mgrSummary").value = appState.lastJudgeSummary;
            }
            openManagerModal();
        }

        // =====================================================================
        // MOTOR 3: SIMULADOR DE PUNTUACIÓN DE REPUTACIÓN (BASE 100 PUNTOS)
        // =====================================================================
        function setRepScore(val) {
            const score = Math.max(0, Math.min(100, parseInt(val, 10) || 0));
            appState.repScore = score;

            const slider = document.getElementById("repSlider");
            const display = document.getElementById("repScoreDisplay");
            const badge = document.getElementById("repStatusBadge");
            const circle = document.getElementById("repGaugeCircle");
            const recoveryBox = document.getElementById("repRecoveryBox");

            if (slider) slider.value = score;
            if (display) display.textContent = score;

            // Actualizar círculo SVG (circunferencia = 314)
            if (circle) {
                const offset = 314 - (314 * score) / 100;
                circle.style.strokeDashoffset = offset;
            }

            // Resetear resaltado de rangos
            ["tier-60-100", "tier-40-59", "tier-20-39", "tier-0-19"].forEach(id => {
                const el = document.getElementById(id);
                if (el) el.className = "p-3.5 rounded-xl border border-white/10 bg-black/40 transition flex items-center justify-between gap-3 opacity-60";
            });

            const daysTo60 = score < 60 ? Math.ceil((60 - score) / 2) : 0;
            const daysTo100 = score < 100 ? Math.ceil((100 - score) / 2) : 0;

            if (score >= 60) {
                if (circle) circle.setAttribute("stroke", "#10b981");
                if (badge) {
                    badge.textContent = "Bueno (60-100)";
                    badge.className = "text-[11px] font-extrabold uppercase px-2 py-0.5 rounded-full bg-emerald-500/20 text-emerald-400 mt-0.5";
                }
                const activeTier = document.getElementById("tier-60-100");
                if (activeTier) activeTier.className = "p-3.5 rounded-xl border-2 border-emerald-400 bg-emerald-500/15 transition flex items-center justify-between gap-3";
                if (recoveryBox) {
                    recoveryBox.className = "p-3 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-xs text-gray-200";
                    recoveryBox.innerHTML = score === 100
                        ? `<strong class="text-emerald-400">¡Puntuación Perfecta (100/100)!</strong> Todas las funciones de LIVE y monetización están activas al 100%.`
                        : `<strong class="text-emerald-400">Zona Segura:</strong> Tienes todas las funciones activas. Necesitas <strong>${daysTo100} días</strong> transmitiendo &ge;10 mins sin infracción (+2 pts/día) para llegar a 100 pts.`;
                }
            } else if (score >= 40) {
                if (circle) circle.setAttribute("stroke", "#f59e0b");
                if (badge) {
                    badge.textContent = "Alerta (40-59)";
                    badge.className = "text-[11px] font-extrabold uppercase px-2 py-0.5 rounded-full bg-amber-500/20 text-amber-400 mt-0.5";
                }
                const activeTier = document.getElementById("tier-40-59");
                if (activeTier) activeTier.className = "p-3.5 rounded-xl border-2 border-amber-400 bg-amber-500/15 transition flex items-center justify-between gap-3";
                if (recoveryBox) {
                    recoveryBox.className = "p-3 rounded-xl bg-amber-500/10 border border-amber-500/30 text-xs text-gray-200";
                    recoveryBox.innerHTML = `<strong class="text-amber-400">Herramientas Bloqueadas:</strong> Star Comments, Draw & Guess, StreamElements, OBS y Restream NO disponibles. Necesitas <strong>${daysTo60} días</strong> limpios (+2 pts/día) o ganar una apelación para volver a 60 pts.`;
                }
            } else if (score >= 20) {
                if (circle) circle.setAttribute("stroke", "#f97316");
                if (badge) {
                    badge.textContent = "Crítico (20-39)";
                    badge.className = "text-[11px] font-extrabold uppercase px-2 py-0.5 rounded-full bg-orange-500/20 text-orange-400 mt-0.5";
                }
                const activeTier = document.getElementById("tier-20-39");
                if (activeTier) activeTier.className = "p-3.5 rounded-xl border-2 border-orange-500 bg-orange-500/15 transition flex items-center justify-between gap-3";
                if (recoveryBox) {
                    recoveryBox.className = "p-3 rounded-xl bg-orange-500/10 border border-orange-500/30 text-xs text-gray-200";
                    recoveryBox.innerHTML = `<strong class="text-orange-400">Monetización y PK Desactivados:</strong> Necesitas <strong>${daysTo60} días</strong> transmitiendo &ge;10 mins sin infracciones (+2 pts/día) o completar tareas educativas / apelación exitosa.`;
                }
            } else {
                if (circle) circle.setAttribute("stroke", "#f43f5e");
                if (badge) {
                    badge.textContent = "Bloqueo (0-19)";
                    badge.className = "text-[11px] font-extrabold uppercase px-2 py-0.5 rounded-full bg-rose-500/20 text-rose-400 mt-0.5";
                }
                const activeTier = document.getElementById("tier-0-19");
                if (activeTier) activeTier.className = "p-3.5 rounded-xl border-2 border-rose-500 bg-rose-500/15 transition flex items-center justify-between gap-3";
                if (recoveryBox) {
                    recoveryBox.className = "p-3 rounded-xl bg-rose-500/15 border border-rose-500/40 text-xs text-gray-200";
                    recoveryBox.innerHTML = `<strong class="text-rose-400">Bloqueo Total (0-19 pts):</strong> Todas las funciones de LIVE están desactivadas. Apela tu última sanción y pídenos ayuda con un Manager de TikTok si fue injusta.`;
                }
            }
        }

        function adjustRepScore(delta) {
            setRepScore(appState.repScore + delta);
            const sign = delta > 0 ? `+${delta}` : `${delta}`;
            showToast(`Simulación aplicada: ${sign} puntos. Puntuación actual: ${appState.repScore}/100 pts.`, delta > 0 ? "success" : "warning");
        }

        // =====================================================================
        // MOTOR 4: CONSULTOR INTELIGENTE 24/7 Y DICCIONARIO DE CÓDIGO SEGURO
        // =====================================================================
        function renderDictionary(items) {
            const list = document.getElementById("dictionaryList");
            if (!list) return;
            if (items.length === 0) {
                list.innerHTML = `<div class="p-4 text-center text-xs text-gray-400">No se encontraron términos con esa búsqueda.</div>`;
                return;
            }
            list.innerHTML = items.map(item => `
                <div class="p-3.5 rounded-xl bg-black/50 border border-white/10 space-y-1.5 text-xs">
                    <div class="flex flex-wrap items-center justify-between gap-1">
                        <span class="font-extrabold text-rose-400"><i class="fa-solid fa-ban mr-1"></i> Prohibido: ${item.forbidden}</span>
                        <span class="text-[10px] font-bold px-2 py-0.5 rounded bg-amber-500/20 text-amber-300 border border-amber-500/30">${item.risk20}</span>
                    </div>
                    <div class="text-emerald-300 font-semibold">
                        <i class="fa-solid fa-shield-check mr-1"></i> Código Seguro: <span class="text-gray-200 font-normal">${item.safeCode}</span>
                    </div>
                </div>
            `).join("");
        }

        function filterDictionary() {
            const query = (document.getElementById("dictionarySearch")?.value || "").toLowerCase().trim();
            if (!query) {
                renderDictionary(SAFE_DICTIONARY);
                return;
            }
            const filtered = SAFE_DICTIONARY.filter(item =>
                item.forbidden.toLowerCase().includes(query) ||
                item.category.toLowerCase().includes(query) ||
                item.safeCode.toLowerCase().includes(query)
            );
            renderDictionary(filtered);
        }

        function clearConsultantChat() {
            const box = document.getElementById("consultantChatBox");
            if (!box) return;
            box.innerHTML = `
                <div class="p-3 rounded-xl bg-ttCyan/10 border border-ttCyan/30 text-gray-200 space-y-1">
                    <div class="font-extrabold text-ttCyan text-xs flex items-center gap-1.5">
                        <i class="fa-solid fa-shield-halved"></i> Auditor IA Oficial (Listo)
                    </div>
                    <p class="text-xs leading-relaxed">
                        Chat reiniciado. Escribe cualquier duda sobre tu transmisión y te responderé con un SÍ o NO rotundo.
                    </p>
                </div>
            `;
        }

        function askQuickQuestion(q) {
            const input = document.getElementById("consultantInput");
            if (input) {
                input.value = q;
                handleConsultantSubmit(new Event("submit"));
            }
        }

        async function handleConsultantSubmit(event) {
            if (event && event.preventDefault) event.preventDefault();
            const input = document.getElementById("consultantInput");
            const chatBox = document.getElementById("consultantChatBox");
            const btn = document.getElementById("btnAskConsultant");
            const question = (input?.value || "").trim();
            if (!question) return;

            input.value = "";
            chatBox.innerHTML += `
                <div class="p-3 rounded-xl bg-white/10 border border-white/15 text-white text-xs ml-6">
                    <div class="font-bold text-ttPink text-[11px] mb-0.5">Tú (Creador):</div>
                    <div>${question}</div>
                </div>
            `;
            chatBox.scrollTop = chatBox.scrollHeight;

            if (btn) btn.disabled = true;

            const qLower = question.toLowerCase();
            let directReply = "";
            if (qLower.includes("20%") || qLower.includes("regalo") || qLower.includes("diamante")) {
                directReply = `<strong>RESPUESTA DIRECTA:</strong> TikTok te retiene el <strong>20% de tus regalos</strong> cuando conectas en batalla PK con un creador infractor, cuando pides regalos de forma coercitiva/excesiva o cuando acumulas advertencias de vestimenta/lenguaje. Si llega a Nivel 3 (Exceso Detectado), TikTok quita el 100% de las ganancias sin devolución.`;
            } else if (qLower.includes("rival") || qLower.includes("pk") || qLower.includes("batalla")) {
                directReply = `<strong>RESPUESTA DIRECTA: CORTA LA BATALLA EN MENOS DE 5 SEGUNDOS.</strong> Si tu rival de PK fuma, insulta o muestra objetos prohibidos, TikTok te sanciona a ti también por conectar con infractores y te pone en riesgo de perder el 20% de tus regalos.`;
            } else if (qLower.includes("menor") || qLower.includes("hijo") || qLower.includes("niño")) {
                directReply = `<strong>RESPUESTA DIRECTA: NO DEJES MENORES EN CÁMARA.</strong> Si un menor aparece solo o interactuando con el chat, TikTok corta el LIVE de inmediato (Nivel 2 o Nivel 3) y descuenta hasta -7 puntos de reputación.`;
            } else if (qLower.includes("visibilidad") || qLower.includes("mitad de pantalla") || qLower.includes("comentario")) {
                directReply = `<strong>DIFERENCIA EXACTA:</strong> 1) Si sale en <strong>comentarios</strong> es FALSO (un troll). 2) Si sale <strong>a mitad de pantalla como Restricción de Visibilidad</strong> (Nivel 1), puedes seguir en LIVE pero no sales en Para Ti. 3) Si es <strong>Sanción Dura</strong>, te quita el 20% de regalos o bloquea el LIVE de 3 a 7 días. ¡Apela siempre y si rechazan siendo injusto pídenos escalar con un Manager!`;
            } else {
                directReply = `<strong>DIRECTRIZ CONCRETA:</strong> Cumple las 6 reglas de la Zona de Cumplimiento (cero humo/vaper, no pedir regalos en exceso, no conectar con infractores, cero groserías/sexualidad, nada cortopunzante y cuidado en retos PK). Si te sancionan a mitad de pantalla injustamente, <strong>1° apela en la app</strong> y <strong>2° si te rechazan estando 100% seguro de que fue injusto, pídenos ayuda para escalarlo con un Manager de TikTok</strong>.`;
            }

            chatBox.innerHTML += `
                <div class="p-3 rounded-xl bg-ttCyan/10 border border-ttCyan/30 text-gray-100 text-xs mr-4 space-y-1">
                    <div class="font-extrabold text-ttCyan text-[11px] flex items-center gap-1">
                        <i class="fa-solid fa-robot"></i> Dictamen del Consultor:
                    </div>
                    <div class="leading-relaxed">${directReply}</div>
                </div>
            `;
            chatBox.scrollTop = chatBox.scrollHeight;
            if (btn) btn.disabled = false;
        }

        // =====================================================================
        // MODAL DE ESCALAMIENTO A MANAGER DE TIKTOK
        // =====================================================================
        function openManagerModal() {
            document.getElementById("mgrScore").value = appState.repScore;
            document.getElementById("managerModal").classList.remove("hidden");
        }
        function closeManagerModal() {
            document.getElementById("managerModal").classList.add("hidden");
        }

        function generateManagerTicket() {
            const username = document.getElementById("mgrUsername").value.trim() || "@creador_pendiente";
            const score = document.getElementById("mgrScore").value || appState.repScore;
            const status = document.getElementById("mgrAppealStatus").value;
            const summary = document.getElementById("mgrSummary").value.trim() || "Sanción recibida a mitad de pantalla durante transmisión cumpliendo todas las normas.";

            const ticketText = `🚨 SOLICITUD DE ESCALAMIENTO A MANAGER DE TIKTOK LIVE 🚨
• Usuario TikTok: ${username}
• Puntuación de Reputación Actual: ${score}/100 pts
• Estado de Apelación en App: ${status}
• Confirmación de Auditoría: Estoy 100% seguro/a de que la sanción fue INJUSTA (Falso positivo de moderación automática).
• Detalle del Caso: ${summary}
• Evidencia adjunta: Captura de la notificación a mitad de pantalla / Estado de Reputación LIVE y captura del rechazo de apelación.`;

            copyTextToClipboard(ticketText, "¡Expediente para Manager de TikTok copiado! Envíalo ahora junto con tus capturas.");
            closeManagerModal();
        }

        // Inicialización al cargar la página
        window.onload = function() {
            setRepScore(85);
            renderDictionary(SAFE_DICTIONARY);
        };
    </script>
</body>
</html>
