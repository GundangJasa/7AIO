# 7AIO
AI learn
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>7AIO - Explore the Universe of AI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Poppins:wght@300;400;600;700&display=swap');
        
        :root {
            --primary: #6c5ce7;
            --secondary: #00cec9;
            --accent: #fd79a8;
            --dark: #0f172a;
            --darker: #020617;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--darker);
            color: white;
            overflow-x: hidden;
        }
        
        .orbitron {
            font-family: 'Orbitron', sans-serif;
        }
        
        .gradient-text {
            background: linear-gradient(90deg, #6c5ce7, #00cec9, #fd79a8);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle var(--duration) infinite ease-in-out;
            opacity: 0;
        }
        
        @keyframes twinkle {
            0%, 100% { opacity: 0; }
            50% { opacity: var(--opacity); }
        }
        
        .floating {
            animation: floating 6s ease-in-out infinite;
        }
        
        @keyframes floating {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        .holographic-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 0 20px rgba(109, 92, 231, 0.3);
            transition: all 0.3s ease;
        }
        
        .holographic-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 30px rgba(109, 92, 231, 0.5);
        }
        
        .glow {
            text-shadow: 0 0 10px rgba(109, 92, 231, 0.7);
        }
        
        .planet {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle, var(--color1), var(--color2));
            box-shadow: 0 0 30px var(--color1);
            z-index: -1;
        }
        
        .comet {
            position: absolute;
            width: 6px;
            height: 6px;
            background: white;
            border-radius: 50%;
            box-shadow: 0 0 10px 2px white;
            animation: comet linear infinite;
        }
        
        @keyframes comet {
            0% {
                transform: translate(0, 0);
                opacity: 1;
            }
            70% {
                opacity: 1;
            }
            100% {
                transform: translate(1000px, 600px);
                opacity: 0;
            }
        }
        
        .ai-avatar {
            position: relative;
            width: 120px;
            height: 120px;
            background: linear-gradient(135deg, #6c5ce7, #00cec9);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 0 30px rgba(109, 92, 231, 0.5);
        }
        
        .ai-avatar::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: linear-gradient(135deg, #6c5ce7, #00cec9);
            filter: blur(15px);
            z-index: -1;
            opacity: 0.7;
        }
        
        .ai-avatar .eyes {
            display: flex;
            gap: 15px;
        }
        
        .ai-avatar .eye {
            width: 20px;
            height: 30px;
            background: white;
            border-radius: 50%;
            position: relative;
            overflow: hidden;
        }
        
        .ai-avatar .eye::after {
            content: '';
            position: absolute;
            width: 10px;
            height: 10px;
            background: #0f172a;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .ai-avatar .mouth {
            position: absolute;
            width: 40px;
            height: 15px;
            background: white;
            border-radius: 0 0 20px 20px;
            bottom: 25px;
        }
        
        .tool-card {
            transition: all 0.3s ease;
            background: rgba(15, 23, 42, 0.7);
            border: 1px solid rgba(109, 92, 231, 0.3);
        }
        
        .tool-card:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(109, 92, 231, 0.5);
            border: 1px solid rgba(109, 92, 231, 0.7);
        }
        
        .badge {
            display: inline-block;
            padding: 2px 8px;
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: bold;
            background: linear-gradient(90deg, #6c5ce7, #00cec9);
            color: white;
        }
        
        .progress-ring {
            position: relative;
            width: 60px;
            height: 60px;
        }
        
        .progress-ring__circle {
            transform: rotate(-90deg);
            transform-origin: 50% 50%;
        }
        
        .progress-ring__circle--track {
            stroke: rgba(255, 255, 255, 0.1);
        }
        
        .progress-ring__circle--progress {
            stroke: #6c5ce7;
            stroke-linecap: round;
            transition: stroke-dashoffset 0.5s ease;
        }
        
        .modal {
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        
        .modal-content {
            transform: translateY(20px);
            transition: transform 0.3s ease;
        }
        
        .modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal.active .modal-content {
            transform: translateY(0);
        }
    </style>
</head>
<body class="min-h-screen">
    <!-- Background Elements -->
    <div id="stars-container"></div>
    <div id="planets-container"></div>
    <div id="comets-container"></div>
    
    <!-- Navigation -->
    <nav class="fixed w-full z-50 bg-black bg-opacity-50 backdrop-filter backdrop-blur-lg border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16 items-center">
                <div class="flex items-center">
                    <div class="flex-shrink-0 flex items-center">
                        <span class="text-2xl font-bold gradient-text orbitron">7AIO</span>
                    </div>
                    <div class="hidden md:block ml-10">
                        <div class="flex space-x-8">
                            <a href="#" class="text-white hover:text-purple-300 px-3 py-2 text-sm font-medium">Home</a>
                            <a href="#learn" class="text-gray-300 hover:text-purple-300 px-3 py-2 text-sm font-medium">Learn</a>
                            <a href="#tools" class="text-gray-300 hover:text-purple-300 px-3 py-2 text-sm font-medium">Tools</a>
                            <a href="#community" class="text-gray-300 hover:text-purple-300 px-3 py-2 text-sm font-medium">Community</a>
                            <a href="#about" class="text-gray-300 hover:text-purple-300 px-3 py-2 text-sm font-medium">About</a>
                        </div>
                    </div>
                </div>
                <div class="hidden md:block">
                    <div class="ml-4 flex items-center md:ml-6 space-x-4">
                        <button id="login-btn" class="px-4 py-2 rounded-full border border-purple-500 text-purple-300 hover:bg-purple-900 hover:bg-opacity-50 transition">Login</button>
                        <button id="register-btn" class="px-4 py-2 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition">Register</button>
                    </div>
                </div>
                <div class="md:hidden">
                    <button id="mobile-menu-btn" class="text-gray-300 hover:text-white focus:outline-none">
                        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                        </svg>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Mobile menu -->
        <div id="mobile-menu" class="md:hidden hidden bg-gray-900">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="#" class="text-white block px-3 py-2 rounded-md text-base font-medium">Home</a>
                <a href="#learn" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Learn</a>
                <a href="#tools" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Tools</a>
                <a href="#community" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">Community</a>
                <a href="#about" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium">About</a>
                <div class="pt-4 border-t border-gray-800">
                    <button class="w-full px-4 py-2 rounded-full border border-purple-500 text-purple-300 hover:bg-purple-900 hover:bg-opacity-50 transition mb-2">Login</button>
                    <button class="w-full px-4 py-2 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition">Register</button>
                </div>
            </div>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section class="relative pt-32 pb-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="flex flex-col md:flex-row items-center">
            <div class="md:w-1/2 mb-12 md:mb-0">
                <h1 class="text-4xl md:text-6xl font-bold mb-6 orbitron">
                    <span class="gradient-text">Explore the Universe</span><br>
                    <span class="text-white">of AI with 7AIO</span>
                </h1>
                <p class="text-xl text-gray-300 mb-8 max-w-lg">
                    Discover the magic of artificial intelligence through interactive lessons, fun tools, and hands-on projects designed for students and young learners.
                </p>
                <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                    <button class="px-6 py-3 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                        Start Learning Now
                    </button>
                    <button class="px-6 py-3 rounded-full border border-purple-500 text-purple-300 hover:bg-purple-900 hover:bg-opacity-50 transition font-medium">
                        Try Our AI Tools
                    </button>
                </div>
            </div>
            <div class="md:w-1/2 flex justify-center relative">
                <div class="ai-avatar floating">
                    <div class="eyes">
                        <div class="eye"></div>
                        <div class="eye"></div>
                    </div>
                    <div class="mouth"></div>
                </div>
                <div class="absolute -top-20 -right-20 w-64 h-64 rounded-full bg-gradient-to-br from-purple-500 to-blue-500 opacity-20 blur-3xl"></div>
            </div>
        </div>
        
        <div class="mt-20 grid grid-cols-2 md:grid-cols-4 gap-4">
            <div class="holographic-card p-6 rounded-xl">
                <div class="text-3xl text-purple-400 mb-3">
                    <i class="fas fa-graduation-cap"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Interactive Lessons</h3>
                <p class="text-gray-300 text-sm">Learn AI concepts through engaging, hands-on activities</p>
            </div>
            <div class="holographic-card p-6 rounded-xl">
                <div class="text-3xl text-blue-400 mb-3">
                    <i class="fas fa-robot"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">AI Tools</h3>
                <p class="text-gray-300 text-sm">Experiment with real AI applications</p>
            </div>
            <div class="holographic-card p-6 rounded-xl">
                <div class="text-3xl text-pink-400 mb-3">
                    <i class="fas fa-gamepad"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Gamified Learning</h3>
                <p class="text-gray-300 text-sm">Earn badges and track your progress</p>
            </div>
            <div class="holographic-card p-6 rounded-xl">
                <div class="text-3xl text-green-400 mb-3">
                    <i class="fas fa-users"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Community</h3>
                <p class="text-gray-300 text-sm">Connect with other AI explorers</p>
            </div>
        </div>
    </section>
    
    <!-- Learn Section -->
    <section id="learn" class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-3xl md:text-4xl font-bold mb-4 orbitron">
                <span class="gradient-text">Your AI Learning Journey</span>
            </h2>
            <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                From beginner to advanced, we've got learning paths for every level of AI explorer.
            </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="holographic-card rounded-xl overflow-hidden">
                <div class="h-48 bg-gradient-to-br from-purple-500 to-blue-500 flex items-center justify-center">
                    <i class="fas fa-rocket text-6xl text-white opacity-80"></i>
                </div>
                <div class="p-6">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="text-xl font-bold">AI Basics</h3>
                        <span class="badge">Beginner</span>
                    </div>
                    <p class="text-gray-300 mb-4">Discover what AI is and how it's changing our world through fun examples and simple explanations.</p>
                    <div class="flex justify-between items-center">
                        <div class="flex space-x-1 text-yellow-400">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                        </div>
                        <button class="text-purple-300 hover:text-purple-100 text-sm font-medium">Start Course →</button>
                    </div>
                </div>
            </div>
            
            <div class="holographic-card rounded-xl overflow-hidden">
                <div class="h-48 bg-gradient-to-br from-blue-500 to-green-500 flex items-center justify-center">
                    <i class="fas fa-brain text-6xl text-white opacity-80"></i>
                </div>
                <div class="p-6">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="text-xl font-bold">Machine Learning</h3>
                        <span class="badge">Intermediate</span>
                    </div>
                    <p class="text-gray-300 mb-4">Learn how machines can learn from data with interactive demos and real-world applications.</p>
                    <div class="flex justify-between items-center">
                        <div class="flex space-x-1 text-yellow-400">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="far fa-star"></i>
                        </div>
                        <button class="text-purple-300 hover:text-purple-100 text-sm font-medium">Start Course →</button>
                    </div>
                </div>
            </div>
            
            <div class="holographic-card rounded-xl overflow-hidden">
                <div class="h-48 bg-gradient-to-br from-green-500 to-pink-500 flex items-center justify-center">
                    <i class="fas fa-project-diagram text-6xl text-white opacity-80"></i>
                </div>
                <div class="p-6">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="text-xl font-bold">Neural Networks</h3>
                        <span class="badge">Advanced</span>
                    </div>
                    <p class="text-gray-300 mb-4">Dive deep into how neural networks work with visualizations and hands-on coding exercises.</p>
                    <div class="flex justify-between items-center">
                        <div class="flex space-x-1 text-yellow-400">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                            <i class="far fa-star"></i>
                        </div>
                        <button class="text-purple-300 hover:text-purple-100 text-sm font-medium">Start Course →</button>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="mt-12 text-center">
            <button class="px-6 py-3 rounded-full border border-purple-500 text-purple-300 hover:bg-purple-900 hover:bg-opacity-50 transition font-medium">
                View All Courses
            </button>
        </div>
    </section>
    
    <!-- AI Tools Section -->
    <section id="tools" class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto bg-gradient-to-b from-gray-900 to-gray-950 rounded-3xl">
        <div class="text-center mb-16">
            <h2 class="text-3xl md:text-4xl font-bold mb-4 orbitron">
                <span class="gradient-text">AI Tools Playground</span>
            </h2>
            <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                Experiment with real AI applications and see the magic happen right before your eyes.
            </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            <div class="tool-card p-6 rounded-xl cursor-pointer" onclick="openToolModal('image-generator')">
                <div class="text-4xl text-purple-400 mb-4">
                    <i class="fas fa-image"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Image Generator</h3>
                <p class="text-gray-300 text-sm">Create amazing images from text prompts using AI</p>
                <div class="mt-4 flex justify-between items-center">
                    <span class="text-xs text-purple-300">Try it now →</span>
                    <span class="text-xs bg-purple-900 bg-opacity-50 text-purple-300 px-2 py-1 rounded">Popular</span>
                </div>
            </div>
            
            <div class="tool-card p-6 rounded-xl cursor-pointer" onclick="openToolModal('voice-changer')">
                <div class="text-4xl text-blue-400 mb-4">
                    <i class="fas fa-microphone-alt"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Voice Changer</h3>
                <p class="text-gray-300 text-sm">Transform your voice into different characters</p>
                <div class="mt-4 flex justify-between items-center">
                    <span class="text-xs text-blue-300">Try it now →</span>
                </div>
            </div>
            
            <div class="tool-card p-6 rounded-xl cursor-pointer" onclick="openToolModal('smart-calculator')">
                <div class="text-4xl text-green-400 mb-4">
                    <i class="fas fa-calculator"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Smart Calculator</h3>
                <p class="text-gray-300 text-sm">Solve complex problems with natural language</p>
                <div class="mt-4 flex justify-between items-center">
                    <span class="text-xs text-green-300">Try it now →</span>
                </div>
            </div>
            
            <div class="tool-card p-6 rounded-xl cursor-pointer" onclick="openToolModal('automation')">
                <div class="text-4xl text-pink-400 mb-4">
                    <i class="fas fa-cogs"></i>
                </div>
                <h3 class="text-xl font-bold mb-2">Automation Flows</h3>
                <p class="text-gray-300 text-sm">Create powerful automations without coding</p>
                <div class="mt-4 flex justify-between items-center">
                    <span class="text-xs text-pink-300">Try it now →</span>
                    <span class="text-xs bg-pink-900 bg-opacity-50 text-pink-300 px-2 py-1 rounded">New</span>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Community Section -->
    <section id="community" class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-3xl md:text-4xl font-bold mb-4 orbitron">
                <span class="gradient-text">Join Our AI Community</span>
            </h2>
            <p class="text-xl text-gray-300 max-w-3xl mx-auto">
                Connect with fellow AI explorers, share your projects, and get help when you need it.
            </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="holographic-card p-8 rounded-xl">
                <div class="text-5xl text-purple-400 mb-6">
                    <i class="fas fa-trophy"></i>
                </div>
                <h3 class="text-xl font-bold mb-4">Leaderboard</h3>
                <div class="space-y-4">
                    <div class="flex items-center">
                        <div class="w-8 h-8 rounded-full bg-gradient-to-r from-yellow-400 to-yellow-600 flex items-center justify-center text-xs font-bold mr-3">1</div>
                        <div class="flex-1">
                            <p class="font-medium">QuantumExplorer</p>
                            <p class="text-xs text-gray-400">1,250 points</p>
                        </div>
                        <div class="text-yellow-400">
                            <i class="fas fa-crown"></i>
                        </div>
                    </div>
                    <div class="flex items-center">
                        <div class="w-8 h-8 rounded-full bg-gradient-to-r from-gray-400 to-gray-600 flex items-center justify-center text-xs font-bold mr-3">2</div>
                        <div class="flex-1">
                            <p class="font-medium">NeuralNova</p>
                            <p class="text-xs text-gray-400">980 points</p>
                        </div>
                    </div>
                    <div class="flex items-center">
                        <div class="w-8 h-8 rounded-full bg-gradient-to-r from-amber-600 to-amber-800 flex items-center justify-center text-xs font-bold mr-3">3</div>
                        <div class="flex-1">
                            <p class="font-medium">AIAdventurer</p>
                            <p class="text-xs text-gray-400">875 points</p>
                        </div>
                    </div>
                </div>
                <button class="mt-6 w-full py-2 rounded-full border border-purple-500 text-purple-300 hover:bg-purple-900 hover:bg-opacity-50 transition text-sm font-medium">
                    View Full Leaderboard
                </button>
            </div>
            
            <div class="holographic-card p-8 rounded-xl">
                <div class="text-5xl text-blue-400 mb-6">
                    <i class="fas fa-medal"></i>
                </div>
                <h3 class="text-xl font-bold mb-4">Your Achievements</h3>
                <div class="flex items-center justify-center mb-6">
                    <div class="relative">
                        <svg class="progress-ring w-32 h-32" viewBox="0 0 100 100">
                            <circle class="progress-ring__circle--track" stroke-width="6" fill="transparent" r="45" cx="50" cy="50"/>
                            <circle class="progress-ring__circle--progress" stroke-width="6" fill="transparent" r="45" cx="50" cy="50" stroke-dasharray="283" stroke-dashoffset="70"/>
                        </svg>
                        <div class="absolute inset-0 flex items-center justify-center flex-col">
                            <span class="text-2xl font-bold">75%</span>
                            <span class="text-xs text-gray-400">Complete</span>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-3 gap-2">
                    <div class="bg-purple-900 bg-opacity-30 rounded p-2 flex flex-col items-center">
                        <i class="fas fa-star text-yellow-400 mb-1"></i>
                        <span class="text-xs">Novice</span>
                    </div>
                    <div class="bg-blue-900 bg-opacity-30 rounded p-2 flex flex-col items-center">
                        <i class="fas fa-rocket text-blue-400 mb-1"></i>
                        <span class="text-xs">Explorer</span>
                    </div>
                    <div class="bg-gray-800 rounded p-2 flex flex-col items-center opacity-50">
                        <i class="fas fa-brain text-gray-400 mb-1"></i>
                        <span class="text-xs">Master</span>
                    </div>
                </div>
                <button class="mt-6 w-full py-2 rounded-full bg-gradient-to-r from-blue-500 to-purple-500 text-white hover:opacity-90 transition text-sm font-medium">
                    Continue Learning
                </button>
            </div>
            
            <div class="holographic-card p-8 rounded-xl">
                <div class="text-5xl text-pink-400 mb-6">
                    <i class="fas fa-comments"></i>
                </div>
                <h3 class="text-xl font-bold mb-4">Recent Discussions</h3>
                <div class="space-y-4">
                    <div class="flex">
                        <div class="w-8 h-8 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 flex items-center justify-center text-xs font-bold mr-3">
                            <i class="fas fa-user text-white text-xs"></i>
                        </div>
                        <div class="flex-1">
                            <p class="font-medium">How do neural networks learn?</p>
                            <p class="text-xs text-gray-400">by AI_Newbie · 2h ago</p>
                        </div>
                        <div class="text-xs text-gray-500">
                            12
                        </div>
                    </div>
                    <div class="flex">
                        <div class="w-8 h-8 rounded-full bg-gradient-to-r from-green-500 to-teal-500 flex items-center justify-center text-xs font-bold mr-3">
                            <i class="fas fa-user text-white text-xs"></i>
                        </div>
                        <div class="flex-1">
                            <p class="font-medium">Check out my image generator project!</p>
                            <p class="text-xs text-gray-400">by CreativeCoder · 5h ago</p>
                        </div>
                        <div class="text-xs text-gray-500">
                            24
                        </div>
                    </div>
                    <div class="flex">
                        <div class="w-8 h-8 rounded-full bg-gradient-to-r from-pink-500 to-red-500 flex items-center justify-center text-xs font-bold mr-3">
                            <i class="fas fa-user text-white text-xs"></i>
                        </div>
                        <div class="flex-1">
                            <p class="font-medium">Help with voice changer tool</p>
                            <p class="text-xs text-gray-400">by SoundWizard · 1d ago</p>
                        </div>
                        <div class="text-xs text-gray-500">
                            8
                        </div>
                    </div>
                </div>
                <button class="mt-6 w-full py-2 rounded-full border border-pink-500 text-pink-300 hover:bg-pink-900 hover:bg-opacity-50 transition text-sm font-medium">
                    Join the Discussion
                </button>
            </div>
        </div>
    </section>
    
    <!-- About Section -->
    <section id="about" class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto bg-gradient-to-b from-gray-950 to-black rounded-3xl">
        <div class="flex flex-col md:flex-row items-center">
            <div class="md:w-1/2 mb-12 md:mb-0">
                <h2 class="text-3xl md:text-4xl font-bold mb-6 orbitron">
                    <span class="gradient-text">About 7AIO</span>
                </h2>
                <p class="text-gray-300 mb-6">
                    7AIO was created with a simple mission: to make artificial intelligence education accessible, engaging, and fun for students and young learners.
                </p>
                <p class="text-gray-300 mb-8">
                    Our platform combines interactive lessons, hands-on tools, and gamification to create a learning experience that's as exciting as exploring the universe.
                </p>
                <div class="flex space-x-4">
                    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-gray-700 flex items-center justify-center text-white">
                        <i class="fab fa-twitter"></i>
                    </a>
                    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-gray-700 flex items-center justify-center text-white">
                        <i class="fab fa-discord"></i>
                    </a>
                    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-gray-700 flex items-center justify-center text-white">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-gray-700 flex items-center justify-center text-white">
                        <i class="fab fa-youtube"></i>
                    </a>
                </div>
            </div>
            <div class="md:w-1/2 md:pl-12">
                <div class="holographic-card p-8 rounded-xl">
                    <h3 class="text-xl font-bold mb-6">Meet the Team</h3>
                    <div class="grid grid-cols-2 gap-6">
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 flex items-center justify-center text-white font-bold mr-3">JD</div>
                            <div>
                                <p class="font-medium">Jane Doe</p>
                                <p class="text-xs text-gray-400">Founder & CEO</p>
                            </div>
                        </div>
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gradient-to-r from-blue-500 to-green-500 flex items-center justify-center text-white font-bold mr-3">JS</div>
                            <div>
                                <p class="font-medium">John Smith</p>
                                <p class="text-xs text-gray-400">Lead Developer</p>
                            </div>
                        </div>
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gradient-to-r from-pink-500 to-red-500 flex items-center justify-center text-white font-bold mr-3">AM</div>
                            <div>
                                <p class="font-medium">Alex Morgan</p>
                                <p class="text-xs text-gray-400">Education Expert</p>
                            </div>
                        </div>
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gradient-to-r from-yellow-500 to-amber-500 flex items-center justify-center text-white font-bold mr-3">TP</div>
                            <div>
                                <p class="font-medium">Taylor Park</p>
                                <p class="text-xs text-gray-400">UI/UX Designer</p>
                            </div>
                        </div>
                    </div>
                    <button class="mt-8 w-full py-2 rounded-full bg-gradient-to-r from-purple-500 to-pink-500 text-white hover:opacity-90 transition text-sm font-medium">
                        Contact Us
                    </button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Newsletter -->
    <section class="py-16 px-4 sm:px-6 lg:px-8 max-w-4xl mx-auto">
        <div class="holographic-card p-8 rounded-xl text-center">
            <h3 class="text-2xl font-bold mb-2 orbitron">
                <span class="gradient-text">Stay Updated</span>
            </h3>
            <p class="text-gray-300 mb-6 max-w-lg mx-auto">
                Subscribe to our newsletter for the latest AI discoveries, course updates, and community news.
            </p>
            <div class="flex flex-col sm:flex-row gap-3 max-w-md mx-auto">
                <input type="email" placeholder="Your email address" class="flex-1 px-4 py-3 rounded-full bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                <button class="px-6 py-3 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                    Subscribe
                </button>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="py-12 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto border-t border-gray-800">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
            <div>
                <h4 class="text-lg font-bold mb-4 orbitron gradient-text">7AIO</h4>
                <p class="text-gray-400 text-sm">
                    Exploring the universe of artificial intelligence, one star at a time.
                </p>
            </div>
            <div>
                <h4 class="text-sm font-semibold text-gray-300 uppercase tracking-wider mb-4">Learn</h4>
                <ul class="space-y-2">
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Courses</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Tutorials</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Projects</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Resources</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-sm font-semibold text-gray-300 uppercase tracking-wider mb-4">Tools</h4>
                <ul class="space-y-2">
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Image Generator</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Voice Changer</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Smart Calculator</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Automation</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-sm font-semibold text-gray-300 uppercase tracking-wider mb-4">Company</h4>
                <ul class="space-y-2">
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">About</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Team</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Careers</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-white text-sm">Contact</a></li>
                </ul>
            </div>
        </div>
        <div class="mt-12 pt-8 border-t border-gray-800 flex flex-col md:flex-row justify-between items-center">
            <p class="text-gray-500 text-sm mb-4 md:mb-0">
                © 2023 7AIO. All rights reserved.
            </p>
            <div class="flex space-x-6">
                <a href="#" class="text-gray-500 hover:text-white">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="#" class="text-gray-500 hover:text-white">
                    <i class="fab fa-discord"></i>
                </a>
                <a href="#" class="text-gray-500 hover:text-white">
                    <i class="fab fa-github"></i>
                </a>
                <a href="#" class="text-gray-500 hover:text-white">
                    <i class="fab fa-youtube"></i>
                </a>
            </div>
        </div>
    </footer>
    
    <!-- Login Modal -->
    <div id="login-modal" class="modal fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50 opacity-0 invisible transition">
        <div class="modal-content bg-gray-900 rounded-xl max-w-md w-full p-8 relative">
            <button class="absolute top-4 right-4 text-gray-400 hover:text-white" onclick="closeModal('login-modal')">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="text-2xl font-bold mb-6 text-center orbitron gradient-text">Login to 7AIO</h3>
            <div class="space-y-4">
                <button class="w-full flex items-center justify-center px-4 py-3 rounded-lg border border-gray-700 hover:bg-gray-800 transition">
                    <i class="fab fa-google text-red-500 mr-3"></i>
                    <span>Continue with Google</span>
                </button>
                <button class="w-full flex items-center justify-center px-4 py-3 rounded-lg border border-gray-700 hover:bg-gray-800 transition">
                    <i class="fab fa-apple text-gray-300 mr-3"></i>
                    <span>Continue with Apple</span>
                </button>
                <button class="w-full flex items-center justify-center px-4 py-3 rounded-lg border border-gray-700 hover:bg-gray-800 transition">
                    <i class="fab fa-facebook text-blue-500 mr-3"></i>
                    <span>Continue with Facebook</span>
                </button>
            </div>
            <div class="flex items-center my-6">
                <div class="flex-1 h-px bg-gray-700"></div>
                <span class="px-4 text-gray-500 text-sm">OR</span>
                <div class="flex-1 h-px bg-gray-700"></div>
            </div>
            <form>
                <div class="mb-4">
                    <label class="block text-gray-400 text-sm mb-2">Email</label>
                    <input type="email" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                </div>
                <div class="mb-6">
                    <label class="block text-gray-400 text-sm mb-2">Password</label>
                    <input type="password" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                </div>
                <button class="w-full py-3 rounded-lg bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                    Login
                </button>
            </form>
            <p class="text-center text-gray-500 text-sm mt-6">
                Don't have an account? <a href="#" class="text-purple-400 hover:text-purple-300" onclick="openRegisterModal()">Register</a>
            </p>
        </div>
    </div>
    
    <!-- Register Modal -->
    <div id="register-modal" class="modal fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50 opacity-0 invisible transition">
        <div class="modal-content bg-gray-900 rounded-xl max-w-md w-full p-8 relative">
            <button class="absolute top-4 right-4 text-gray-400 hover:text-white" onclick="closeModal('register-modal')">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="text-2xl font-bold mb-6 text-center orbitron gradient-text">Join 7AIO</h3>
            <div class="space-y-4">
                <button class="w-full flex items-center justify-center px-4 py-3 rounded-lg border border-gray-700 hover:bg-gray-800 transition">
                    <i class="fab fa-google text-red-500 mr-3"></i>
                    <span>Continue with Google</span>
                </button>
                <button class="w-full flex items-center justify-center px-4 py-3 rounded-lg border border-gray-700 hover:bg-gray-800 transition">
                    <i class="fab fa-apple text-gray-300 mr-3"></i>
                    <span>Continue with Apple</span>
                </button>
                <button class="w-full flex items-center justify-center px-4 py-3 rounded-lg border border-gray-700 hover:bg-gray-800 transition">
                    <i class="fab fa-facebook text-blue-500 mr-3"></i>
                    <span>Continue with Facebook</span>
                </button>
            </div>
            <div class="flex items-center my-6">
                <div class="flex-1 h-px bg-gray-700"></div>
                <span class="px-4 text-gray-500 text-sm">OR</span>
                <div class="flex-1 h-px bg-gray-700"></div>
            </div>
            <form>
                <div class="mb-4">
                    <label class="block text-gray-400 text-sm mb-2">Email</label>
                    <input type="email" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                </div>
                <div class="mb-4">
                    <label class="block text-gray-400 text-sm mb-2">Password</label>
                    <input type="password" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                </div>
                <div class="mb-6">
                    <label class="block text-gray-400 text-sm mb-2">Confirm Password</label>
                    <input type="password" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                </div>
                <button class="w-full py-3 rounded-lg bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                    Create Account
                </button>
            </form>
            <p class="text-center text-gray-500 text-sm mt-6">
                Already have an account? <a href="#" class="text-purple-400 hover:text-purple-300" onclick="openLoginModal()">Login</a>
            </p>
        </div>
    </div>
    
    <!-- AI Tool Modals -->
    <div id="image-generator-modal" class="modal fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50 opacity-0 invisible transition p-4">
        <div class="modal-content bg-gray-900 rounded-xl max-w-4xl w-full p-8 relative">
            <button class="absolute top-4 right-4 text-gray-400 hover:text-white" onclick="closeToolModal('image-generator')">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="text-2xl font-bold mb-6 orbitron gradient-text">AI Image Generator</h3>
            <div class="flex flex-col md:flex-row gap-6">
                <div class="md:w-1/2">
                    <div class="h-64 bg-gray-800 rounded-lg mb-4 flex items-center justify-center border border-gray-700">
                        <p class="text-gray-500">Your generated image will appear here</p>
                    </div>
                    <div class="grid grid-cols-4 gap-2 mb-6">
                        <div class="h-16 bg-gray-800 rounded border border-gray-700"></div>
                        <div class="h-16 bg-gray-800 rounded border border-gray-700"></div>
                        <div class="h-16 bg-gray-800 rounded border border-gray-700"></div>
                        <div class="h-16 bg-gray-800 rounded border border-gray-700"></div>
                    </div>
                    <div class="flex space-x-3">
                        <button class="flex-1 py-2 rounded-lg bg-gray-800 border border-gray-700 hover:bg-gray-700 transition text-sm">
                            <i class="fas fa-download mr-2"></i> Download
                        </button>
                        <button class="flex-1 py-2 rounded-lg bg-gray-800 border border-gray-700 hover:bg-gray-700 transition text-sm">
                            <i class="fas fa-share-alt mr-2"></i> Share
                        </button>
                    </div>
                </div>
                <div class="md:w-1/2">
                    <div class="mb-4">
                        <label class="block text-gray-400 text-sm mb-2">Prompt</label>
                        <textarea class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white h-32" placeholder="Describe the image you want to generate..."></textarea>
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-400 text-sm mb-2">Style</label>
                        <select class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                            <option>Digital Art</option>
                            <option>Photorealistic</option>
                            <option>Watercolor</option>
                            <option>Pixel Art</option>
                            <option>Anime</option>
                        </select>
                    </div>
                    <div class="grid grid-cols-2 gap-4 mb-6">
                        <div>
                            <label class="block text-gray-400 text-sm mb-2">Resolution</label>
                            <select class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                                <option>512x512</option>
                                <option>768x768</option>
                                <option>1024x1024</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-gray-400 text-sm mb-2">Quality</label>
                            <select class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                                <option>Standard</option>
                                <option>High</option>
                                <option>Ultra</option>
                            </select>
                        </div>
                    </div>
                    <button class="w-full py-3 rounded-lg bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                        Generate Image
                    </button>
                    <p class="text-xs text-gray-500 mt-3">
                        Note: Image generation may take a few seconds. You'll earn 5 learning points for each image generated!
                    </p>
                </div>
            </div>
        </div>
    </div>
    
    <div id="voice-changer-modal" class="modal fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50 opacity-0 invisible transition p-4">
        <div class="modal-content bg-gray-900 rounded-xl max-w-2xl w-full p-8 relative">
            <button class="absolute top-4 right-4 text-gray-400 hover:text-white" onclick="closeToolModal('voice-changer')">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="text-2xl font-bold mb-6 orbitron gradient-text">AI Voice Changer</h3>
            <div class="mb-6">
                <div class="h-32 bg-gray-800 rounded-lg mb-4 flex items-center justify-center border border-gray-700">
                    <p class="text-gray-500">Your voice recording will appear here</p>
                </div>
                <div class="flex justify-center space-x-4">
                    <button class="w-12 h-12 rounded-full bg-gradient-to-r from-purple-500 to-blue-500 flex items-center justify-center text-white hover:opacity-90 transition">
                        <i class="fas fa-microphone"></i>
                    </button>
                    <button class="px-6 py-3 rounded-full bg-gray-800 border border-gray-700 hover:bg-gray-700 transition font-medium" disabled>
                        <i class="fas fa-play mr-2"></i> Play
                    </button>
                </div>
            </div>
            <div class="mb-6">
                <label class="block text-gray-400 text-sm mb-2">Voice Style</label>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-3">
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Robot
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Alien
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-purple-500 transition text-sm">
                        Cartoon
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Deep Voice
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Chipmunk
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Ghost
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Celebrity
                    </button>
                    <button class="py-2 px-4 rounded-lg bg-gray-800 border border-gray-700 hover:border-purple-500 transition text-sm">
                        Custom
                    </button>
                </div>
            </div>
            <div class="flex space-x-3">
                <button class="flex-1 py-3 rounded-lg bg-gray-800 border border-gray-700 hover:bg-gray-700 transition font-medium">
                    Save Voice
                </button>
                <button class="flex-1 py-3 rounded-lg bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                    Apply Changes
                </button>
            </div>
        </div>
    </div>
    
    <div id="smart-calculator-modal" class="modal fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50 opacity-0 invisible transition p-4">
        <div class="modal-content bg-gray-900 rounded-xl max-w-md w-full p-8 relative">
            <button class="absolute top-4 right-4 text-gray-400 hover:text-white" onclick="closeToolModal('smart-calculator')">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="text-2xl font-bold mb-6 orbitron gradient-text">Smart AI Calculator</h3>
            <div class="mb-6">
                <div class="bg-gray-800 rounded-lg p-4 border border-gray-700 mb-3">
                    <div class="text-right text-gray-400 text-sm">Your question</div>
                    <div class="text-right text-2xl font-mono">2x² + 5x - 3 = 0</div>
                </div>
                <div class="bg-gray-800 rounded-lg p-4 border border-purple-500">
                    <div class="text-right text-purple-400 text-sm">AI Solution</div>
                    <div class="text-right text-xl font-mono">x = 0.5 or x = -3</div>
                </div>
            </div>
            <div class="mb-4">
                <label class="block text-gray-400 text-sm mb-2">Enter your math problem</label>
                <input type="text" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white" placeholder="E.g., 2x² + 5x - 3 = 0">
            </div>
            <div class="mb-6">
                <label class="block text-gray-400 text-sm mb-2">Problem type</label>
                <select class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                    <option>Algebra</option>
                    <option>Calculus</option>
                    <option>Geometry</option>a
                    <option>Trigonometry</option>
                    <option>Statistics</option>
                </select>
            </div>
            <button class="w-full py-3 rounded-lg bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                Solve
            </button>
            <p class="text-xs text-gray-500 mt-3">
                Tip: You can ask in natural language like "Find the roots of 2x squared plus 5x minus 3"
            </p>
        </div>
    </div>
    
    <div id="automation-modal" class="modal fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50 opacity-0 invisible transition p-4">
        <div class="modal-content bg-gray-900 rounded-xl max-w-4xl w-full p-8 relative">
            <button class="absolute top-4 right-4 text-gray-400 hover:text-white" onclick="closeToolModal('automation')">
                <i class="fas fa-times"></i>
            </button>
            <h3 class="text-2xl font-bold mb-6 orbitron gradient-text">AI Automation Builder</h3>
            <div class="flex flex-col md:flex-row gap-6">
                <div class="md:w-1/2">
                    <div class="bg-gray-800 rounded-lg p-6 border border-gray-700 mb-6 h-64 overflow-y-auto">
                        <div class="flex items-start mb-4">
                            <div class="w-8 h-8 rounded-full bg-purple-500 flex items-center justify-center text-white text-sm font-bold mr-3">1</div>
                            <div class="flex-1">
                                <div class="font-medium mb-1">Trigger</div>
                                <select class="w-full px-3 py-2 rounded bg-gray-700 border border-gray-600 text-white text-sm">
                                    <option>When I receive an email</option>
                                    <option>At a specific time</option>
                                    <option>When a file is uploaded</option>
                                    <option>When a form is submitted</option>
                                </select>
                            </div>
                        </div>
                        <div class="flex items-start mb-4">
                            <div class="w-8 h-8 rounded-full bg-blue-500 flex items-center justify-center text-white text-sm font-bold mr-3">2</div>
                            <div class="flex-1">
                                <div class="font-medium mb-1">Action</div>
                                <select class="w-full px-3 py-2 rounded bg-gray-700 border border-gray-600 text-white text-sm">
                                    <option>Send a notification</option>
                                    <option>Create a document</option>
                                    <option>Post to social media</option>
                                    <option>Send an email</option>
                                </select>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <div class="w-8 h-8 rounded-full bg-green-500 flex items-center justify-center text-white text-sm font-bold mr-3">3</div>
                            <div class="flex-1">
                                <div class="font-medium mb-1">Final Action</div>
                                <select class="w-full px-3 py-2 rounded bg-gray-700 border border-gray-600 text-white text-sm">
                                    <option>Log the activity</option>
                                    <option>Send a summary email</option>
                                    <option>Update a spreadsheet</option>
                                    <option>No final action</option>
                                </select>
                            </div>
                        </div>
                    </div>
                    <div class="flex space-x-3">
                        <button class="flex-1 py-2 rounded-lg bg-gray-800 border border-gray-700 hover:bg-gray-700 transition text-sm">
                            <i class="fas fa-save mr-2"></i> Save
                        </button>
                        <button class="flex-1 py-2 rounded-lg bg-gray-800 border border-gray-700 hover:bg-gray-700 transition text-sm">
                            <i class="fas fa-share-alt mr-2"></i> Share
                        </button>
                    </div>
                </div>
                <div class="md:w-1/2">
                    <div class="mb-4">
                        <label class="block text-gray-400 text-sm mb-2">Automation Name</label>
                        <input type="text" class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white" placeholder="E.g., Daily Report Generator">
                    </div>
                    <div class="mb-4">
                        <label class="block text-gray-400 text-sm mb-2">Description</label>
                        <textarea class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white h-24" placeholder="What does this automation do?"></textarea>
                    </div>
                    <div class="mb-6">
                        <label class="block text-gray-400 text-sm mb-2">Category</label>
                        <select class="w-full px-4 py-3 rounded-lg bg-gray-800 border border-gray-700 focus:border-purple-500 focus:outline-none text-white">
                            <option>Productivity</option>
                            <option>Social Media</option>
                            <option>Data Processing</option>
                            <option>Notifications</option>
                            <option>Custom</option>
                        </select>
                    </div>
                    <button class="w-full py-3 roundeda-lg bg-gradient-to-r from-purple-500 to-blue-500 text-white hover:opacity-90 transition font-medium">
                        Create Automation
                    </button>
                    <p class="text-xs text-gray-500 mt-3">
                        Pro Tip: Use AI suggestions to build complex automations with natural language.
                    </p>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        // Create stars
        function createStars() {
            const container = document.getElementById('stars-container');
            const starCount = 100;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // Random position
                const x = Math.random() * 100;
                const y = Math.random() * 100;
                star.style.left = `${x}%`;
                star.style.top = `${y}%`;
                
                // Random size
                const size = Math.random() * 3;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                // Random animation properties
                star.style.setProperty('--duration', `${5 + Math.random() * 10}s`);
                star.style.setProperty('--opacity', Math.random());
                
                // Random delay
                star.style.animationDelay = `${Math.random() * 5}s`;
                
                container.appendChild(star);
            }
        }
        
        // Create planets
        function createPlanets() {
            const container = document.getElementById('planets-container');
            const planetCount = 3;
            
            for (let i = 0; i < planetCount; i++) {
                const planet = document.createElement('div');
                planet.classList.add('planet');
                
                // Random position
                const x = 10 + Math.random() * 80;
                const y = 10 + Math.random() * 80;
                planet.style.left = `${x}%`;
                planet.style.top = `${y}%`;
                
                // Random size
                const size = 50 + Math.random() * 150;
                planet.style.width = `${size}px`;
                planet.style.height = `${size}px`;
                
                // Random colors
                const colors = [
                    '--color1: #6c5ce7; --color2: #00cec9;',
                    '--color1: #fd79a8; --color2: #e84393;',
                    '--color1: #00b894; --color2: #55efc4;',
                    '--color1: #0984e3; --color2: #74b9ff;',
                    '--color1: #fdcb6e; --color2: #e17055;'
                ];
                planet.style = colors[Math.floor(Math.random() * colors.length)];
                
                // Random animation
                planet.style.animation = `floating ${8 + Math.random() * 8}s ease-in-out infinite`;
                planet.style.animationDelay = `${Math.random() * 5}s`;
                
                container.appendChild(planet);
            }
        }
        
        // Create comets
        function createComets() {
            const container = document.getElementById('comets-container');
            const cometCount = 2;
            
            for (let i = 0; i < cometCount; i++) {
                const comet = document.createElement('div');
                comet.classList.add('comet');
                
                // Random position
                const x = Math.random() * 100;
                const y = Math.random() * 100;
                comet.style.left = `${x}%`;
                comet.style.top = `${y}%`;
                
                // Random animation duration
                comet.style.animationDuration = `${10 + Math.random() * 20}s`;
                
                // Random delay
                comet.style.animationDelay = `${Math.random() * 15}s`;
                
                container.appendChild(comet);
            }
        }
        
        // Mobile menu toggle
        document.getElementById('mobile-menu-btn').addEventListener('click', function() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        });
        
        // Modal functions
        function openLoginModal() {
            closeAllModals();
            const modal = document.getElementById('login-modal');
            modal.classList.add('active');
        }
        
        function openRegisterModal() {
            closeAllModals();
            const modal = document.getElementById('register-modal');
            modal.classList.add('active');
        }
        
        function closeModal(modalId) {
            const modal = document.getElementById(modalId);
            modal.classList.remove('active');
        }
        
        function closeAllModals() {
            document.querySelectorAll('.modal').forEach(modal => {
                modal.classList.remove('active');
            });
        }
        
        // Tool modal functions
        function openToolModal(toolName) {
            closeAllModals();
            const modal = document.getElementById(`${toolName}-modal`);
            modal.classList.add('active');
        }
        
        function closeToolModal(toolName) {
            const modal = document.getElementById(`${toolName}-modal`);
            modal.classList.remove('active');
        }
        
        // Event listeners
        document.getElementById('login-btn').addEventListener('click', openLoginModal);
        document.getElementById('register-btn').addEventListener('click', openRegisterModal);
        
        // Close modals when clicking outside
        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.remove('active');
                }
            });
        });
        
        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            createPlanets();
            createComets();
            
            // Set progress ring
            const circle = document.querySelector('.progress-ring__circle--progress');
            const radius = circle.r.baseVal.value;
            const circumference = 2 * Math.PI * radius;
            
            circle.style.strokeDasharray = circumference;
            circle.style.strokeDashoffset = circumference - (75 / 100) * circumference;
        });
    </script>
</body>
<script link="js.js"></script>
</html>
