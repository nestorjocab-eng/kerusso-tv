index.html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Luz Eterna TV - Tu Fe en Movimiento</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        serif: ['Cormorant Garamond', 'serif'],
                        sans: ['Montserrat', 'sans-serif'],
                    },
                    colors: {
                        gold: {
                            400: '#D4AF37',
                            500: '#C5A028',
                            600: '#B8941D',
                        },
                        navy: {
                            900: '#0A1628',
                            800: '#0F1F38',
                            700: '#162B4D',
                        }
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                        'shimmer': 'shimmer 2s linear infinite',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-20px)' },
                        },
                        shimmer: {
                            '0%': { backgroundPosition: '-1000px 0' },
                            '100%': { backgroundPosition: '1000px 0' },
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .glass-effect {
            background: rgba(15, 31, 56, 0.7);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(212, 175, 55, 0.2);
        }
        
        .text-gradient {
            background: linear-gradient(135deg, #D4AF37 0%, #FFF 50%, #D4AF37 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .hero-bg {
            background: linear-gradient(135deg, #0A1628 0%, #162B4D 50%, #0F1F38 100%);
            position: relative;
            overflow: hidden;
        }
        
        .hero-bg::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(212,175,55,0.1) 0%, transparent 70%);
            animation: rotate 30s linear infinite;
        }
        
        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        .program-card {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .program-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(212, 175, 55, 0.3);
        }
        
        .live-indicator {
            animation: pulse-red 2s infinite;
        }
        
        @keyframes pulse-red {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.7; transform: scale(1.1); }
        }
        
        .scroll-reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }
        
        .scroll-reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        .video-container {
            position: relative;
            background: linear-gradient(45deg, #0A1628, #1a365d);
            overflow: hidden;
        }
        
        .video-container::after {
            content: '';
            position: absolute;
            inset: 0;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23D4AF37' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            opacity: 0.3;
        }
    </style>
<base target="_blank">
</head>
<body class="font-sans bg-navy-900 text-white overflow-x-hidden">

    <!-- Navigation -->
    <nav class="fixed w-full z-50 glass-effect transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <div class="flex items-center space-x-3 group cursor-pointer">
                    <div class="w-10 h-10 rounded-full bg-gradient-to-br from-gold-400 to-gold-600 flex items-center justify-center transform group-hover:rotate-12 transition-transform">
                        <i class="fas fa-cross text-navy-900 text-lg"></i>
                    </div>
                    <span class="font-serif text-2xl font-bold text-gradient tracking-wide">Luz Eterna TV</span>
                </div>
                
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#inicio" class="text-gray-300 hover:text-gold-400 transition-colors text-sm uppercase tracking-wider font-medium">Inicio</a>
                    <a href="#envivo" class="text-gray-300 hover:text-gold-400 transition-colors text-sm uppercase tracking-wider font-medium">En Vivo</a>
                    <a href="#programas" class="text-gray-300 hover:text-gold-400 transition-colors text-sm uppercase tracking-wider font-medium">Programas</a>
                    <a href="#horarios" class="text-gray-300 hover:text-gold-400 transition-colors text-sm uppercase tracking-wider font-medium">Horarios</a>
                    <a href="#nosotros" class="text-gray-300 hover:text-gold-400 transition-colors text-sm uppercase tracking-wider font-medium">Nosotros</a>
                    <button class="bg-gradient-to-r from-gold-500 to-gold-600 text-navy-900 px-6 py-2 rounded-full font-bold hover:shadow-lg hover:shadow-gold-500/30 transition-all transform hover:scale-105">
                        Donar <i class="fas fa-heart ml-2"></i>
                    </button>
                </div>
                
                <button class="md:hidden text-gold-400 text-2xl" onclick="toggleMobileMenu()">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
        
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden glass-effect border-t border-gold-500/20">
            <div class="px-4 pt-2 pb-6 space-y-2">
                <a href="#inicio" class="block px-3 py-2 text-gray-300 hover:text-gold-400 hover:bg-white/5 rounded-md">Inicio</a>
                <a href="#envivo" class="block px-3 py-2 text-gray-300 hover:text-gold-400 hover:bg-white/5 rounded-md">En Vivo</a>
                <a href="#programas" class="block px-3 py-2 text-gray-300 hover:text-gold-400 hover:bg-white/5 rounded-md">Programas</a>
                <a href="#horarios" class="block px-3 py-2 text-gray-300 hover:text-gold-400 hover:bg-white/5 rounded-md">Horarios</a>
                <a href="#nosotros" class="block px-3 py-2 text-gray-300 hover:text-gold-400 hover:bg-white/5 rounded-md">Nosotros</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="inicio" class="hero-bg min-h-screen flex items-center justify-center relative pt-20">
        <div class="absolute inset-0 overflow-hidden">
            <div class="absolute top-20 left-10 w-72 h-72 bg-gold-500/20 rounded-full blur-3xl animate-float"></div>
            <div class="absolute bottom-20 right-10 w-96 h-96 bg-blue-500/10 rounded-full blur-3xl animate-float" style="animation-delay: 2s;"></div>
        </div>
        
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 text-center">
            <div class="inline-flex items-center space-x-2 bg-white/10 backdrop-blur-sm rounded-full px-4 py-2 mb-8 border border-gold-500/30 animate-pulse-slow">
                <span class="w-2 h-2 bg-red-500 rounded-full live-indicator"></span>
                <span class="text-gold-400 text-sm font-semibold tracking-wider uppercase">Transmitiendo Ahora</span>
            </div>
            
            <h1 class="font-serif text-5xl md:text-7xl lg:text-8xl font-bold mb-6 leading-tight">
                <span class="block text-white">Tu Fe en</span>
                <span class="text-gradient italic">Movimiento</span>
            </h1>
            
            <p class="text-xl md:text-2xl text-gray-300 mb-12 max-w-3xl mx-auto font-light leading-relaxed">
                Transmisión cristiana las 24 horas. Mensajes de esperanza, alabanza y palabra viva para tu corazón.
            </p>
            
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <button onclick="scrollToSection('envivo')" class="group bg-gradient-to-r from-gold-500 to-gold-600 text-navy-900 px-8 py-4 rounded-full font-bold text-lg hover:shadow-2xl hover:shadow-gold-500/40 transition-all transform hover:scale-105 flex items-center space-x-2">
                    <i class="fas fa-play"></i>
                    <span>Ver Transmisión</span>
                </button>
                <button class="group border-2 border-gold-400 text-gold-400 px-8 py-4 rounded-full font-bold text-lg hover:bg-gold-400 hover:text-navy-900 transition-all flex items-center space-x-2">
                    <i class="fas fa-calendar-alt"></i>
                    <span>Ver Programación</span>
                </button>
            </div>
            
            <div class="mt-16 grid grid-cols-2 md:grid-cols-4 gap-8 max-w-4xl mx-auto">
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-gold-400 mb-2 counter" data-target="24">0</div>
                    <div class="text-sm text-gray-400 uppercase tracking-wider">Horas al día</div>
                </div>
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-gold-400 mb-2 counter" data-target="150">0</div>
                    <div class="text-sm text-gray-400 uppercase tracking-wider">Países</div>
                </div>
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-gold-400 mb-2 counter" data-target="50">0</div>
                    <div class="text-sm text-gray-400 uppercase tracking-wider">Programas</div>
                </div>
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-gold-400 mb-2 counter" data-target="2">0</div>
                    <div class="text-sm text-gray-400 uppercase tracking-wider">Millones de Hogares</div>
                </div>
            </div>
        </div>
        
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
            <i class="fas fa-chevron-down text-gold-400 text-2xl"></i>
        </div>
    </section>

    <!-- Live Stream Section -->
    <section id="envivo" class="py-20 bg-navy-800 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12 scroll-reveal">
                <h2 class="font-serif text-4xl md:text-5xl font-bold mb-4 text-white">
                    Transmisión <span class="text-gold-400">En Vivo</span>
                </h2>
                <div class="w-24 h-1 bg-gradient-to-r from-transparent via-gold-400 to-transparent mx-auto mb-4"></div>
                <p class="text-gray-400 max-w-2xl mx-auto">Únete a nuestra comunidad en este momento. La palabra de Dios no tiene horario.</p>
            </div>
            
            <div class="grid lg:grid-cols-3 gap-8">
                <!-- Main Player -->
                <div class="lg:col-span-2 scroll-reveal">
                    <div class="video-container rounded-2xl overflow-hidden shadow-2xl shadow-black/50 aspect-video relative group cursor-pointer" onclick="playVideo()">
                        <div class="absolute inset-0 bg-gradient-to-t from-navy-900/80 via-transparent to-transparent z-10"></div>
                        <img src="https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?w=1200&h=675&fit=crop" alt="Live Stream" class="w-full h-full object-cover opacity-80 group-hover:scale-105 transition-transform duration-700">
                        
                        <div class="absolute inset-0 flex items-center justify-center z-20">
                            <div class="w-20 h-20 bg-gold-500/90 rounded-full flex items-center justify-center transform group-hover:scale-110 transition-transform shadow-2xl">
                                <i class="fas fa-play text-navy-900 text-3xl ml-1"></i>
                            </div>
                        </div>
                        
                        <div class="absolute top-4 left-4 z-20 flex items-center space-x-2 bg-red-600/90 backdrop-blur-sm px-3 py-1 rounded-full">
                            <span class="w-2 h-2 bg-white rounded-full animate-pulse"></span>
                            <span class="text-white text-xs font-bold uppercase tracking-wider">LIVE</span>
                        </div>
                        
                        <div class="absolute bottom-4 left-4 right-4 z-20">
                            <h3 class="text-white font-bold text-xl mb-1">Alabanza y Adoración Matutina</h3>
                            <p class="text-gray-300 text-sm">Con el Pastor Roberto Mendoza • 6:00 AM - 9:00 AM</p>
                        </div>
                    </div>
                    
                    <!-- Video Controls Bar -->
                    <div class="mt-4 flex items-center justify-between bg-navy-700/50 rounded-xl p-4 backdrop-blur-sm">
                        <div class="flex items-center space-x-4">
                            <button class="text-gold-400 hover:text-white transition-colors"><i class="fas fa-play"></i></button>
                            <button class="text-gray-400 hover:text-white transition-colors"><i class="fas fa-volume-up"></i></button>
                            <div class="w-32 h-1 bg-gray-600 rounded-full overflow-hidden">
                                <div class="w-2/3 h-full bg-gold-400"></div>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4">
                            <button class="text-gray-400 hover:text-gold-400 transition-colors"><i class="fas fa-cog"></i></button>
                            <button class="text-gray-400 hover:text-gold-400 transition-colors"><i class="fas fa-expand"></i></button>
                        </div>
                    </div>
                </div>
                
                <!-- Live Chat & Info -->
                <div class="space-y-6 scroll-reveal">
                    <div class="glass-effect rounded-2xl p-6">
                        <h3 class="font-serif text-2xl font-bold text-gold-400 mb-4">Próximos Programas</h3>
                        <div class="space-y-4" id="upcoming-programs">
                            <!-- Programas generados por JS -->
                        </div>
                    </div>
                    
                    <div class="glass-effect rounded-2xl p-6">
                        <h3 class="font-serif text-xl font-bold text-white mb-4">Compartir</h3>
                        <div class="grid grid-cols-4 gap-3">
                            <button class="bg-blue-600/20 hover:bg-blue-600/40 border border-blue-500/30 rounded-lg p-3 text-blue-400 transition-all"><i class="fab fa-facebook-f"></i></button>
                            <button class="bg-sky-500/20 hover:bg-sky-500/40 border border-sky-500/30 rounded-lg p-3 text-sky-400 transition-all"><i class="fab fa-twitter"></i></button>
                            <button class="bg-green-600/20 hover:bg-green-600/40 border border-green-500/30 rounded-lg p-3 text-green-400 transition-all"><i class="fab fa-whatsapp"></i></button>
                            <button class="bg-pink-600/20 hover:bg-pink-600/40 border border-pink-500/30 rounded-lg p-3 text-pink-400 transition-all"><i class="fas fa-share"></i></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Programs Grid -->
    <section id="programas" class="py-20 bg-navy-900 relative overflow-hidden">
        <div class="absolute top-0 left-0 w-full h-px bg-gradient-to-r from-transparent via-gold-400/50 to-transparent"></div>
        
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 scroll-reveal">
                <span class="text-gold-400 text-sm font-bold tracking-widest uppercase mb-2 block">Nuestra Programación</span>
                <h2 class="font-serif text-4xl md:text-5xl font-bold mb-6 text-white">
                    Contenido que <span class="italic text-gold-400">Transforma</span>
                </h2>
                <div class="flex flex-wrap justify-center gap-4 mt-8">
                    <button class="filter-btn active bg-gold-500 text-navy-900 px-6 py-2 rounded-full font-semibold text-sm transition-all" data-filter="all">Todos</button>
                    <button class="filter-btn bg-navy-800 text-gray-300 hover:bg-navy-700 px-6 py-2 rounded-full font-semibold text-sm transition-all border border-gold-500/30" data-filter="predicas">Prédicas</button>
                    <button class="filter-btn bg-navy-800 text-gray-300 hover:bg-navy-700 px-6 py-2 rounded-full font-semibold text-sm transition-all border border-gold-500/30" data-filter="musica">Música</button>
                    <button class="filter-btn bg-navy-800 text-gray-300 hover:bg-navy-700 px-6 py-2 rounded-full font-semibold text-sm transition-all border border-gold-500/30" data-filter="familia">Familia</button>
                    <button class="filter-btn bg-navy-800 text-gray-300 hover:bg-navy-700 px-6 py-2 rounded-full font-semibold text-sm transition-all border border-gold-500/30" data-filter="jovenes">Jóvenes</button>
                </div>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8" id="programs-grid">
                <!-- Program cards generated by JS -->
            </div>
            
            <div class="text-center mt-12">
                <button class="border-2 border-gold-400 text-gold-400 px-8 py-3 rounded-full font-bold hover:bg-gold-400 hover:text-navy-900 transition-all">
                    Ver Todos los Programas <i class="fas fa-arrow-right ml-2"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Schedule Section -->
    <section id="horarios" class="py-20 bg-navy-800 relative">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12 scroll-reveal">
                <h2 class="font-serif text-4xl md:text-5xl font-bold mb-4 text-white">Horarios de <span class="text-gold-400">Transmisión</span></h2>
                <p class="text-gray-400">Planifica tu día espiritual con nuestra programación</p>
            </div>
            
            <div class="glass-effect rounded-3xl p-8 md:p-12 scroll-reveal">
                <div class="grid md:grid-cols-2 gap-12 items-center">
                    <div>
                        <div class="space-y-6" id="schedule-list">
                            <!-- Schedule items generated by JS -->
                        </div>
                    </div>
                    
                    <div class="relative">
                        <div class="aspect-square rounded-2xl overflow-hidden relative">
                            <img src="https://images.unsplash.com/photo-1504052434569-70ad5836ab65?w=800&h=800&fit=crop" alt="Bible Study" class="w-full h-full object-cover opacity-90">
                            <div class="absolute inset-0 bg-gradient-to-t from-navy-900 via-transparent to-transparent"></div>
                            <div class="absolute bottom-6 left-6 right-6">
                                <div class="bg-white/10 backdrop-blur-md rounded-xl p-4 border border-white/20">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gold-400 font-bold">Ahora Transmitiendo</span>
                                        <span class="text-white text-sm" id="current-time">00:00</span>
                                    </div>
                                    <h4 class="text-white font-bold text-lg">Reflexiones de la Mañana</h4>
                                    <p class="text-gray-300 text-sm">Con Pastora María González</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="py-20 bg-navy-900 relative overflow-hidden">
        <div class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-5"></div>
        
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="text-center mb-16 scroll-reveal">
                <h2 class="font-serif text-4xl md:text-5xl font-bold mb-4 text-white">Testimonios de <span class="text-gold-400">Fe</span></h2>
                <p class="text-gray-400">Historias de vida transformadas por el mensaje</p>
            </div>
            
            <div class="grid md:grid-cols-3 gap-8">
                <div class="glass-effect rounded-2xl p-8 transform hover:-translate-y-2 transition-all duration-300 scroll-reveal">
                    <div class="flex items-center mb-4">
                        <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&h=100&fit=crop" alt="Testimonial" class="w-12 h-12 rounded-full object-cover border-2 border-gold-400">
                        <div class="ml-4">
                            <h4 class="text-white font-bold">Ana Martínez</h4>
                            <p class="text-gold-400 text-sm">México</p>
                        </div>
                    </div>
                    <p class="text-gray-300 italic leading-relaxed">"Luz Eterna TV ha sido un faro en momentos de oscuridad. Los programas de oración me han ayudado a reconectar con mi fe."</p>
                    <div class="mt-4 flex text-gold-400 text-sm">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                </div>
                
                <div class="glass-effect rounded-2xl p-8 transform hover:-translate-y-2 transition-all duration-300 scroll-reveal" style="transition-delay: 100ms;">
                    <div class="flex items-center mb-4">
                        <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=100&h=100&fit=crop" alt="Testimonial" class="w-12 h-12 rounded-full object-cover border-2 border-gold-400">
                        <div class="ml-4">
                            <h4 class="text-white font-bold">Carlos Rodríguez</h4>
                            <p class="text-gold-400 text-sm">Colombia</p>
                        </div>
                    </div>
                    <p class="text-gray-300 italic leading-relaxed">"La calidad de la programación es excepcional. Mi familia completa disfruta los programas de valores familiares cada noche."</p>
                    <div class="mt-4 flex text-gold-400 text-sm">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                </div>
                
                <div class="glass-effect rounded-2xl p-8 transform hover:-translate-y-2 transition-all duration-300 scroll-reveal" style="transition-delay: 200ms;">
                    <div class="flex items-center mb-4">
                        <img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?w=100&h=100&fit=crop" alt="Testimonial" class="w-12 h-12 rounded-full object-cover border-2 border-gold-400">
                        <div class="ml-4">
                            <h4 class="text-white font-bold">Lucía Fernández</h4>
                            <p class="text-gold-400 text-sm">Argentina</p>
                        </div>
                    </div>
                    <p class="text-gray-300 italic leading-relaxed">"Gracias a este canal descubrí una comunidad de fe increíble. Los estudios bíblicos son profundos y accesibles."</p>
                    <div class="mt-4 flex text-gold-400 text-sm">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Donation Section -->
    <section class="py-20 bg-gradient-to-br from-navy-800 to-navy-900 relative overflow-hidden">
        <div class="absolute top-0 right-0 w-1/2 h-full bg-gold-500/5 rounded-l-full blur-3xl"></div>
        
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="glass-effect rounded-3xl p-8 md:p-16 text-center scroll-reveal border border-gold-500/20">
                <div class="inline-flex items-center justify-center w-16 h-16 bg-gold-500/20 rounded-full mb-6">
                    <i class="fas fa-dove text-gold-400 text-3xl"></i>
                </div>
                <h2 class="font-serif text-4xl md:text-5xl font-bold mb-6 text-white">Apoya Nuestra <span class="text-gold-400">Misión</span></h2>
                <p class="text-gray-300 text-lg mb-8 max-w-2xl mx-auto">
                    Tu donación nos permite llevar el mensaje de esperanza a más hogares. Cada aporte contribuye a mantener esta luz encendida las 24 horas.
                </p>
                
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 max-w-3xl mx-auto mb-8">
                    <button class="donation-btn bg-navy-800 hover:bg-gold-500 hover:text-navy-900 text-white border border-gold-500/30 rounded-xl py-4 font-bold transition-all transform hover:scale-105" onclick="selectAmount(10)">$10</button>
                    <button class="donation-btn bg-navy-800 hover:bg-gold-500 hover:text-navy-900 text-white border border-gold-500/30 rounded-xl py-4 font-bold transition-all transform hover:scale-105" onclick="selectAmount(25)">$25</button>
                    <button class="donation-btn bg-navy-800 hover:bg-gold-500 hover:text-navy-900 text-white border border-gold-500/30 rounded-xl py-4 font-bold transition-all transform hover:scale-105" onclick="selectAmount(50)">$50</button>
                    <button class="donation-btn bg-navy-800 hover:bg-gold-500 hover:text-navy-900 text-white border border-gold-500/30 rounded-xl py-4 font-bold transition-all transform hover:scale-105" onclick="selectAmount(100)">$100</button>
                </div>
                
                <button class="bg-gradient-to-r from-gold-500 to-gold-600 text-navy-900 px-10 py-4 rounded-full font-bold text-lg hover:shadow-2xl hover:shadow-gold-500/30 transition-all transform hover:scale-105">
                    Donar Ahora <i class="fas fa-heart ml-2"></i>
                </button>
                
                <p class="mt-6 text-gray-400 text-sm">
                    <i class="fas fa-lock mr-2"></i>Donación segura y encriptada
                </p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-navy-900 border-t border-gold-500/20 pt-16 pb-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid md:grid-cols-4 gap-12 mb-12">
                <div class="col-span-2">
                    <div class="flex items-center space-x-3 mb-6">
                        <div class="w-10 h-10 rounded-full bg-gradient-to-br from-gold-400 to-gold-600 flex items-center justify-center">
                            <i class="fas fa-cross text-navy-900 text-lg"></i>
                        </div>
                        <span class="font-serif text-2xl font-bold text-gradient">Luz Eterna TV</span>
                    </div>
                    <p class="text-gray-400 mb-6 max-w-sm">
                        Llevando la luz del Evangelio a cada rincón del mundo a través de la televisión digital y streaming.
                    </p>
                    <div class="flex space-x-4">
                        <a href="#" class="w-10 h-10 rounded-full bg-navy-800 flex items-center justify-center text-gray-400 hover:bg-gold-500 hover:text-navy-900 transition-all"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="w-10 h-10 rounded-full bg-navy-800 flex items-center justify-center text-gray-400 hover:bg-gold-500 hover:text-navy-900 transition-all"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="w-10 h-10 rounded-full bg-navy-800 flex items-center justify-center text-gray-400 hover:bg-gold-500 hover:text-navy-900 transition-all"><i class="fab fa-youtube"></i></a>
                        <a href="#" class="w-10 h-10 rounded-full bg-navy-800 flex items-center justify-center text-gray-400 hover:bg-gold-500 hover:text-navy-900 transition-all"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                
                <div>
                    <h4 class="text-white font-bold mb-4 uppercase tracking-wider text-sm">Enlaces Rápidos</h4>
                    <ul class="space-y-3">
                        <li><a href="#" class="text-gray-400 hover:text-gold-400 transition-colors">Programación</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-gold-400 transition-colors">En Vivo</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-gold-400 transition-colors">Podcasts</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-gold-400 transition-colors">Oración</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-white font-bold mb-4 uppercase tracking-wider text-sm">Contacto</h4>
                    <ul class="space-y-3 text-gray-400">
                        <li class="flex items-start space-x-3">
                            <i class="fas fa-map-marker-alt text-gold-400 mt-1"></i>
                            <span>Calle Fe 123, Ciudad Esperanza</span>
                        </li>
                        <li class="flex items-center space-x-3">
                            <i class="fas fa-phone text-gold-400"></i>
                            <span>+1 (555) 123-4567</span>
                        </li>
                        <li class="flex items-center space-x-3">
                            <i class="fas fa-envelope text-gold-400"></i>
                            <span>contacto@luzeterna.tv</span>
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="border-t border-gold-500/10 pt-8 flex flex-col md:flex-row justify-between items-center">
                <p class="text-gray-500 text-sm mb-4 md:mb-0">&copy; 2024 Luz Eterna TV. Todos los derechos reservados.</p>
                <div class="flex space-x-6 text-sm text-gray-500">
                    <a href="#" class="hover:text-gold-400 transition-colors">Privacidad</a>
                    <a href="#" class="hover:text-gold-400 transition-colors">Términos</a>
                    <a href="#" class="hover:text-gold-400 transition-colors">Cookies</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Data
        const programs = [
            { title: "Despertar con Dios", category: "predicas", time: "6:00 AM", image: "https://images.unsplash.com/photo-1504052434569-70ad5836ab65?w=400&h=300&fit=crop", desc: "Oración matutina y reflexión bíblica" },
            { title: "Alabanza Sin Fin", category: "musica", time: "9:00 AM", image: "https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?w=400&h=300&fit=crop", desc: "Música cristiana contemporánea" },
            { title: "Familia en Cristo", category: "familia", time: "11:00 AM", image: "https://images.unsplash.com/photo-1511895426328-dc8714191300?w=400&h=300&fit=crop", desc: "Valores y educación cristiana" },
            { title: "Jóvenes de Impacto", category: "jovenes", time: "3:00 PM", image: "https://images.unsplash.com/photo-1529156069898-49953e39b3ac?w=400&h=300&fit=crop", desc: "Devocionales para jóvenes" },
            { title: "Estudio Profundo", category: "predicas", time: "6:00 PM", image: "https://images.unsplash.com/photo-1548625361-1d6c5d4695b8?w=400&h=300&fit=crop", desc: "Análisis bíblico detallado" },
            { title: "Noche de Milagros", category: "predicas", time: "9:00 PM", image: "https://images.unsplash.com/photo-1499209974431-9dddcece7f88?w=400&h=300&fit=crop", desc: "Testimonios y sanación" }
        ];

        const schedule = [
            { time: "06:00", title: "Despertar con Dios", host: "Pastor Roberto", active: true },
            { time: "09:00", title: "Alabanza Sin Fin", host: "Equipo de Alabanza", active: false },
            { time: "11:00", title: "Familia en Cristo", host: "Dra. María González", active: false },
            { time: "15:00", title: "Jóvenes de Impacto", host: "Líderes Juveniles", active: false },
            { time: "18:00", title: "Estudio Profundo", host: "Pastor Carlos Ruiz", active: false },
            { time: "21:00", title: "Noche de Milagros", host: "Evangelista Juan Pérez", active: false }
        ];

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            renderPrograms('all');
            renderUpcoming();
            renderSchedule();
            startClock();
            initCounters();
            initScrollReveal();
            initFilters();
        });

        // Render Programs
        function renderPrograms(filter) {
            const grid = document.getElementById('programs-grid');
            const filtered = filter === 'all' ? programs : programs.filter(p => p.category === filter);
            
            grid.innerHTML = filtered.map((program, index) => `
                <div class="program-card glass-effect rounded-2xl overflow-hidden group cursor-pointer scroll-reveal" style="transition-delay: ${index * 100}ms">
                    <div class="relative h-48 overflow-hidden">
                        <img src="${program.image}" alt="${program.title}" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-500">
                        <div class="absolute top-4 right-4 bg-gold-500 text-navy-900 text-xs font-bold px-3 py-1 rounded-full">
                            ${program.time}
                        </div>
                        <div class="absolute inset-0 bg-gradient-to-t from-navy-900 to-transparent opacity-60"></div>
                    </div>
                    <div class="p-6">
                        <span class="text-gold-400 text-xs font-bold uppercase tracking-wider mb-2 block">${program.category}</span>
                        <h3 class="text-xl font-bold text-white mb-2 group-hover:text-gold-400 transition-colors">${program.title}</h3>
                        <p class="text-gray-400 text-sm mb-4">${program.desc}</p>
                        <button class="text-gold-400 text-sm font-semibold flex items-center space-x-2 group-hover:translate-x-2 transition-transform">
                            <span>Ver Programa</span>
                            <i class="fas fa-arrow-right"></i>
                        </button>
                    </div>
                </div>
            `).join('');
            
            // Re-init scroll reveal for new elements
            setTimeout(initScrollReveal, 100);
        }

        // Render Upcoming Programs Sidebar
        function renderUpcoming() {
            const container = document.getElementById('upcoming-programs');
            container.innerHTML = programs.slice(1, 4).map(p => `
                <div class="flex items-center space-x-4 p-3 rounded-xl hover:bg-white/5 transition-colors cursor-pointer group">
                    <div class="w-16 h-16 rounded-lg overflow-hidden flex-shrink-0">
                        <img src="${p.image}" class="w-full h-full object-cover" alt="${p.title}">
                    </div>
                    <div class="flex-1">
                        <h4 class="text-white font-semibold text-sm group-hover:text-gold-400 transition-colors">${p.title}</h4>
                        <p class="text-gray-400 text-xs">${p.time} • ${p.desc}</p>
                    </div>
                    <button class="text-gold-400 opacity-0 group-hover:opacity-100 transition-opacity">
                        <i class="fas fa-bell"></i>
                    </button>
                </div>
            `).join('');
        }

        // Render Schedule
        function renderSchedule() {
            const container = document.getElementById('schedule-list');
            const currentHour = new Date().getHours();
            
            container.innerHTML = schedule.map((item, index) => {
                const itemHour = parseInt(item.time.split(':')[0]);
                const isActive = currentHour >= itemHour && currentHour < (schedule[index + 1] ? parseInt(schedule[index + 1].time.split(':')[0]) : 24);
                
                return `
                    <div class="flex items-center space-x-4 p-4 rounded-xl ${isActive ? 'bg-gold-500/20 border border-gold-500/30' : 'hover:bg-white/5'} transition-all cursor-pointer group">
                        <div class="w-16 text-center">
                            <span class="block text-gold-400 font-bold">${item.time}</span>
                            <span class="block text-gray-500 text-xs">HRS</span>
                        </div>
                        <div class="flex-1 border-l border-gray-700 pl-4">
                            <h4 class="text-white font-semibold ${isActive ? 'text-gold-400' : ''}">${item.title}</h4>
                            <p class="text-gray-400 text-sm">${item.host}</p>
                        </div>
                        ${isActive ? '<span class="w-2 h-2 bg-red-500 rounded-full animate-pulse"></span>' : ''}
                    </div>
                `;
            }).join('');
        }

        // Clock
        function startClock() {
            const updateTime = () => {
                const now = new Date();
                document.getElementById('current-time').textContent = now.toLocaleTimeString('es-ES', { hour: '2-digit', minute: '2-digit' });
            };
            updateTime();
            setInterval(updateTime, 1000);
        }

        // Counters Animation
        function initCounters() {
            const counters = document.querySelectorAll('.counter');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const target = parseInt(entry.target.getAttribute('data-target'));
                        animateCounter(entry.target, target);
                        observer.unobserve(entry.target);
                    }
                });
            });
            counters.forEach(counter => observer.observe(counter));
        }

        function animateCounter(element, target) {
            let current = 0;
            const increment = target / 50;
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target + (target > 100 ? '+' : '');
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current);
                }
            }, 30);
        }

        // Scroll Reveal
        function initScrollReveal() {
            const reveals = document.querySelectorAll('.scroll-reveal');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                    }
                });
            }, { threshold: 0.1 });
            
            reveals.forEach(reveal => observer.observe(reveal));
        }

        // Filters
        function initFilters() {
            const buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(btn => {
                btn.addEventListener('click', () => {
                    buttons.forEach(b => {
                        b.classList.remove('active', 'bg-gold-500', 'text-navy-900');
                        b.classList.add('bg-navy-800', 'text-gray-300');
                    });
                    btn.classList.remove('bg-navy-800', 'text-gray-300');
                    btn.classList.add('active', 'bg-gold-500', 'text-navy-900');
                    renderPrograms(btn.getAttribute('data-filter'));
                });
            });
        }

        // Mobile Menu
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // Smooth Scroll
        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        // Navbar Scroll Effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('shadow-lg');
                navbar.style.background = 'rgba(10, 22, 40, 0.95)';
            } else {
                navbar.classList.remove('shadow-lg');
                navbar.style.background = 'rgba(15, 31, 56, 0.7)';
            }
        });

        // Donation Selection
        function selectAmount(amount) {
            document.querySelectorAll('.donation-btn').forEach(btn => {
                btn.classList.remove('bg-gold-500', 'text-navy-900', 'border-gold-500');
                btn.classList.add('bg-navy-800', 'text-white', 'border-gold-500/30');
            });
            event.target.classList.remove('bg-navy-800', 'text-white', 'border-gold-500/30');
            event.target.classList.add('bg-gold-500', 'text-navy-900', 'border-gold-500');
        }

        // Play Video Simulation
        function playVideo() {
            alert('Iniciando transmisión en vivo...');
        }

        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    // Close mobile menu if open
                    document.getElementById('mobile-menu').classList.add('hidden');
                }
            });
        });
    </script>
</body>
</html>
