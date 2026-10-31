# Made-roadmap-HTML-site-to-competetive-programming-c-
no Ai
<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CP.cpp // Ultimate Competitive Programming Roadmap</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cpDark: '#0a0d14',
                        cpCard: '#121824',
                        cpCardHover: '#1a2333',
                        cpBorder: '#1e293b',
                        cpNeonCyan: '#00f2fe',
                        cpNeonGreen: '#00ff87',
                        cpNeonPurple: '#7928ca',
                        cpNeonPink: '#ff007f',
                        cpNeonYellow: '#f59e0b'
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['Fira Code', 'monospace']
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom Styling for Cyberpunk & Terminal Aesthetic */
        body {
            background-color: #0a0d14;
            color: #e2e8f0;
            font-family: 'Inter', sans-serif;
        }

        /* Glassmorphism elements */
        .glass-panel {
            background: rgba(18, 24, 36, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.07);
        }
        
        .glass-panel-glow {
            background: rgba(18, 24, 36, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 242, 254, 0.2);
            box-shadow: 0 0 20px rgba(0, 242, 254, 0.1);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #0a0d14;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e293b;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00f2fe;
        }

        /* Neon Glow Utility Classes */
        .glow-cyan {
            box-shadow: 0 0 15px rgba(0, 242, 254, 0.3);
        }
        .glow-green {
            box-shadow: 0 0 15px rgba(0, ff, 135, 0.3);
        }
        .text-gradient-cyan {
            background: linear-gradient(135deg, #00f2fe 0%, #4facfe 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .text-gradient-purple {
            background: linear-gradient(135deg, #7928ca 0%, #ff007f 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .text-gradient-green {
            background: linear-gradient(135deg, #00ff87 0%, #60efff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Custom Code Highlight Tweaks */
        pre code {
            font-family: 'Fira Code', monospace;
            font-size: 0.875rem;
            line-height: 1.5;
        }

        /* Scanline Effect Overlay */
        .scanline-bg {
            background: linear-gradient(
                rgba(18, 16, 16, 0) 50%, 
                rgba(0, 0, 0, 0.25) 50%
            ), linear-gradient(
                90deg,
                rgba(255, 0, 0, 0.03),
                rgba(0, 255, 0, 0.01),
                rgba(0, 0, 255, 0.03)
            );
            background-size: 100% 3px, 6px 100%;
            pointer-events: none;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col relative selection:bg-cyan-500 selection:text-black">

    <!-- Scanline Subtle Overlay for Aesthetic -->
    <div class="fixed inset-0 scanline-bg z-50 opacity-40 pointer-events-none"></div>

    <!-- MAIN HEADER / TERMINAL BANNER -->
    <header class="sticky top-0 z-40 glass-panel border-b border-cpBorder/80 px-4 py-3 lg:px-8">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row md:items-center md:justify-between gap-4">
            
            <!-- Brand / Logo -->
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-cyan-500 to-purple-600 flex items-center justify-center font-mono font-bold text-black text-xl shadow-lg glow-cyan">
                    &lt;/&gt;
                </div>
                <div>
                    <h1 class="text-xl font-bold font-mono tracking-tight flex items-center gap-2">
                        <span>CP_MASTER</span>
                        <span class="text-xs px-2 py-0.5 rounded font-mono bg-cyan-950 text-cyan-400 border border-cyan-800">C++20 v3.4</span>
                    </h1>
                    <p class="text-xs text-slate-400 font-mono">Top-Tier Competitive Programming Mastery Matrix</p>
                </div>
            </div>

            <!-- Realtime Stats & Terminal Metrics -->
            <div class="flex items-center gap-3 overflow-x-auto pb-1 md:pb-0 font-mono text-xs">
                <!-- Total Topics -->
                <div class="px-3 py-1.5 rounded-lg bg-cpCard border border-cpBorder flex items-center gap-2">
                    <i class="fa-solid fa-list-check text-slate-400"></i>
                    <span class="text-slate-400">Total:</span>
                    <span id="stat-total" class="font-bold text-white">0</span>
                </div>
                <!-- Mastered Count -->
                <div class="px-3 py-1.5 rounded-lg bg-cpCard border border-cpBorder flex items-center gap-2">
                    <i class="fa-solid fa-square-check text-emerald-400"></i>
                    <span class="text-slate-400">Done:</span>
                    <span id="stat-mastered" class="font-bold text-emerald-400">0</span>
                </div>
                <!-- Progress Percentage -->
                <div class="px-3 py-1.5 rounded-lg bg-cpCard border border-cpBorder flex items-center gap-2">
                    <i class="fa-solid fa-chart-pie text-cyan-400"></i>
                    <span id="stat-percent" class="font-bold text-cyan-400">0%</span>
                </div>
                <!-- Daily Streak Button / Counter -->
                <div class="px-3 py-1.5 rounded-lg bg-cpCard border border-cpBorder flex items-center gap-2 cursor-pointer hover:border-amber-500/50 transition-colors" onclick="incrementStreak()" title="Click to log today's solved problem!">
                    <i class="fa-solid fa-fire text-amber-500 animate-pulse"></i>
                    <span class="text-slate-400">Streak:</span>
                    <span id="stat-streak" class="font-bold text-amber-400">0 Days</span>
                </div>
            </div>
        </div>

        <!-- Progress Bar -->
        <div class="max-w-7xl mx-auto mt-3 w-full bg-cpBorder/60 h-1.5 rounded-full overflow-hidden">
            <div id="main-progress-bar" class="h-full bg-gradient-to-r from-cyan-500 via-purple-500 to-emerald-400 w-0 transition-all duration-500"></div>
        </div>
    </header>

    <!-- CONTAINER FOR CONTENT -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 py-6 lg:px-8 space-y-6">

        <!-- SEARCH BAR & UTILITY TOOLS BAR -->
        <div class="flex flex-col md:flex-row gap-4 items-stretch md:items-center justify-between">
            
            <!-- Real-time Search Box -->
            <div class="relative flex-1">
                <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-1/2 -translate-y-1/2 text-slate-500 text-sm"></i>
                <input 
                    type="text" 
                    id="search-input"
                    placeholder="Search algorithm, data structure, technique (e.g., 'Segment Tree', 'DP', 'KMP')..." 
                    class="w-full bg-cpCard border border-cpBorder focus:border-cyan-500 text-sm rounded-xl pl-10 pr-10 py-2.5 text-slate-200 placeholder-slate-500 focus:outline-none focus:ring-1 focus:ring-cyan-500 font-mono transition-all"
                    oninput="handleSearchFilter()"
                >
                <button id="clear-search" class="hidden absolute right-3 top-1/2 -translate-y-1/2 text-slate-500 hover:text-white" onclick="clearSearch()">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <!-- Action Buttons: Quick Template Generator & CP Tools -->
            <div class="flex items-center gap-2">
                <button onclick="openModal('template-modal')" class="px-3.5 py-2.5 rounded-xl bg-cpCard border border-cpBorder hover:border-cyan-500/50 hover:bg-cpCardHover text-xs font-mono font-semibold text-cyan-400 flex items-center gap-2 transition-all">
                    <i class="fa-solid fa-code"></i>
                    <span>C++ Template</span>
                </button>
                <button onclick="openModal('tools-modal')" class="px-3.5 py-2.5 rounded-xl bg-cpCard border border-cpBorder hover:border-purple-500/50 hover:bg-cpCardHover text-xs font-mono font-semibold text-purple-400 flex items-center gap-2 transition-all">
                    <i class="fa-solid fa-calculator"></i>
                    <span>CP Toolbox</span>
                </button>
                <button onclick="resetProgress()" class="px-3 py-2.5 rounded-xl bg-cpCard border border-cpBorder hover:border-red-500/50 hover:text-red-400 text-xs text-slate-500 transition-all" title="Reset saved progress">
                    <i class="fa-solid fa-rotate-right"></i>
                </button>
            </div>
        </div>

        <!-- CATEGORY & DIFFICULTY FILTER PILLS -->
        <div class="flex flex-col gap-3">
            <!-- Difficulty Filters -->
            <div class="flex items-center gap-2 overflow-x-auto pb-1 text-xs font-mono">
                <span class="text-slate-500 font-semibold uppercase text-[10px] tracking-wider pr-2 border-r border-cpBorder">Difficulty:</span>
                <button class="filter-diff-btn px-3 py-1 rounded-lg border border-cyan-500/40 bg-cyan-500/10 text-cyan-400 font-medium hover:bg-cyan-500/20 transition-all" data-diff="all" onclick="setDiffFilter('all', this)">All</button>
                <button class="filter-diff-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all" data-diff="Beginner" onclick="setDiffFilter('Beginner', this)">Beginner</button>
                <button class="filter-diff-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all" data-diff="Intermediate" onclick="setDiffFilter('Intermediate', this)">Intermediate</button>
                <button class="filter-diff-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all" data-diff="Advanced" onclick="setDiffFilter('Advanced', this)">Advanced</button>
                <button class="filter-diff-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all" data-diff="Expert" onclick="setDiffFilter('Expert', this)">Expert</button>
            </div>

            <!-- Category Pills -->
            <div id="category-pills-container" class="flex items-center gap-2 overflow-x-auto pb-1 text-xs font-mono">
                <span class="text-slate-500 font-semibold uppercase text-[10px] tracking-wider pr-2 border-r border-cpBorder">Category:</span>
                <!-- Injected via JS -->
            </div>
        </div>

        <!-- MAIN ROADMAP GRID (TOPICS DISPLAY) -->
        <div id="topics-container" class="space-y-8">
            <!-- Dynamic Category Sections Injected Here -->
        </div>

        <!-- EMPTY SEARCH STATE -->
        <div id="no-results" class="hidden py-16 text-center space-y-3">
            <i class="fa-solid fa-terminal text-4xl text-slate-600"></i>
            <p class="text-slate-400 font-mono text-sm">No CP algorithm matching search parameters standard found.</p>
            <button onclick="clearSearch()" class="px-4 py-2 bg-cpCard border border-cpBorder rounded-xl text-xs font-mono text-cyan-400 hover:border-cyan-500">Reset Search</button>
        </div>

    </main>

    <!-- FOOTER -->
    <footer class="border-t border-cpBorder/80 glass-panel mt-12 py-6 px-4 font-mono text-xs text-slate-500 text-center">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-3">
            <div>CP.cpp Matrix &copy; 2026 // Designed for Codeforces, AtCoder, USACO & CSES competitors</div>
            <div class="flex items-center gap-4 text-slate-400">
                <span class="flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-emerald-500 inline-block"></span> C++20 Ready</span>
                <span class="flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-cyan-500 inline-block"></span> LocalStorage Sync</span>
            </div>
        </div>
    </footer>

    <!-- TOPIC DETAILS MODAL -->
    <div id="topic-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-cpCard border border-cpBorder rounded-2xl w-full max-w-4xl max-h-[90vh] flex flex-col shadow-2xl overflow-hidden animate-in fade-in zoom-in duration-200">
            <!-- Modal Header -->
            <div class="p-5 border-b border-cpBorder flex items-center justify-between bg-cpCardHover/50">
                <div class="flex items-center gap-3">
                    <span id="modal-category-badge" class="px-2.5 py-1 rounded-md bg-cyan-950 border border-cyan-800 text-cyan-400 font-mono text-xs font-semibold">Category</span>
                    <h2 id="modal-title" class="text-xl font-bold font-mono text-white">Topic Title</h2>
                </div>
                <button onclick="closeModal('topic-modal')" class="w-8 h-8 rounded-lg bg-cpBorder/50 flex items-center justify-center text-slate-400 hover:text-white hover:bg-cpBorder transition-all">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            
            <!-- Modal Content (Scrollable) -->
            <div class="p-6 overflow-y-auto space-y-6 font-sans">
                <!-- Complexity & Difficulty Tags -->
                <div class="flex flex-wrap items-center gap-3">
                    <div class="px-3 py-1 rounded-lg bg-slate-900 border border-slate-700 font-mono text-xs text-slate-300 flex items-center gap-2">
                        <i class="fa-solid fa-clock text-amber-400"></i> Time: <span id="modal-time-comp" class="text-amber-400 font-bold font-mono">O(N log N)</span>
                    </div>
                    <div class="px-3 py-1 rounded-lg bg-slate-900 border border-slate-700 font-mono text-xs text-slate-300 flex items-center gap-2">
                        <i class="fa-solid fa-memory text-purple-400"></i> Space: <span id="modal-space-comp" class="text-purple-400 font-bold font-mono">O(N)</span>
                    </div>
                    <div id="modal-diff-tag" class="px-3 py-1 rounded-lg font-mono text-xs font-bold uppercase">Intermediate</div>
                </div>

                <!-- Concept Summary -->
                <div class="space-y-2">
                    <h4 class="text-xs font-mono font-bold uppercase text-slate-400 tracking-wider flex items-center gap-2">
                        <i class="fa-solid fa-brain text-cyan-400"></i> Key Concept & Intuition
                    </h4>
                    <p id="modal-description" class="text-sm text-slate-300 leading-relaxed bg-slate-900/50 p-4 rounded-xl border border-cpBorder">
                        Description loading...
                    </p>
                </div>

                <!-- Interactive C++ Code Snippet -->
                <div class="space-y-2">
                    <div class="flex items-center justify-between">
                        <h4 class="text-xs font-mono font-bold uppercase text-slate-400 tracking-wider flex items-center gap-2">
                            <i class="fa-solid fa-code text-emerald-400"></i> Standard C++ Implementation / Template
                        </h4>
                        <button onclick="copySnippetCode()" class="text-xs font-mono text-cyan-400 hover:text-cyan-300 flex items-center gap-1.5 px-2.5 py-1 rounded bg-cpBorder/40 hover:bg-cpBorder transition-all">
                            <i class="fa-regular fa-copy"></i>
                            <span id="copy-btn-text">Copy Code</span>
                        </button>
                    </div>
                    <div class="relative bg-black rounded-xl border border-cpBorder overflow-hidden">
                        <pre class="p-4 text-xs font-mono text-emerald-300 overflow-x-auto max-h-72"><code id="modal-code">// C++ Snippet loading...</code></pre>
                    </div>
                </div>

                <!-- Essential Practice Problems -->
                <div class="space-y-2">
                    <h4 class="text-xs font-mono font-bold uppercase text-slate-400 tracking-wider flex items-center gap-2">
                        <i class="fa-solid fa-trophy text-amber-400"></i> Practice Problems (Codeforces, AtCoder, CSES, USACO)
                    </h4>
                    <div id="modal-problems" class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
                        <!-- Problems injected via JS -->
                    </div>
                </div>
            </div>

            <!-- Modal Footer -->
            <div class="p-4 border-t border-cpBorder bg-cpCardHover/50 flex items-center justify-between font-mono text-xs">
                <span class="text-slate-400">Mark current status:</span>
                <div class="flex items-center gap-2" id="modal-status-buttons">
                    <!-- Status toggles -->
                </div>
            </div>
        </div>
    </div>

    <!-- C++ FAST I/O TEMPLATE MODAL -->
    <div id="template-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-cpCard border border-cpBorder rounded-2xl w-full max-w-3xl flex flex-col shadow-2xl overflow-hidden">
            <div class="p-5 border-b border-cpBorder flex items-center justify-between bg-cpCardHover/50">
                <h3 class="font-mono font-bold text-white flex items-center gap-2">
                    <i class="fa-solid fa-bolt text-amber-400"></i> Complete C++ Competitive Programming Template
                </h3>
                <button onclick="closeModal('template-modal')" class="w-8 h-8 rounded-lg bg-cpBorder/50 flex items-center justify-center text-slate-400 hover:text-white">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            <div class="p-5 space-y-3">
                <p class="text-xs text-slate-400 font-mono">High-performance template with Fast I/O, type aliases, debugging helpers, and essential macros.</p>
                <div class="relative bg-black rounded-xl border border-cpBorder p-4 overflow-x-auto max-h-96">
                    <pre class="text-xs font-mono text-cyan-300"><code id="cpp-template-text">#include &lt;bits/stdc++.h&gt;
using namespace std;

// --- OPTIMIZATION & FAST I/O ---
#pragma GCC optimize("O3,unroll-loops")
#pragma GCC target("avx2,bmi,bmi2,lzcnt,popcnt")

// --- TYPE ALIASES & MACROS ---
using ll = long long;
using ld = long double;
using pii = pair&lt;int, int&gt;;
using pll = pair&lt;ll, ll&gt;;
using vi = vector&lt;int&gt;;
using vll = vector&lt;ll&gt;;

#define pb push_back
#define eb emplace_back
#define all(x) (x).begin(), (x).end()
#define rall(x) (x).rbegin(), (x).rend()
#define sz(x) static_cast&lt;int&gt;((x).size())
#define FOR(i, a, b) for (int i = (a); i &lt; (b); ++i)
#define RFOR(i, a, b) for (int i = (a) - 1; i &gt;= (b); --i)

const int INF = 1e9 + 7;
const ll INFLL = 1e18 + 9;
const int MOD = 1e9 + 7; // 998244353

// --- SOLVE FUNCTION ---
void solve() {
    int n;
    if (!(cin &gt;&gt; n)) return;
    vll a(n);
    FOR(i, 0, n) cin &gt;&gt; a[i];
    
    // Algorithm logic here
}

int main() {
    // Fast I/O optimization
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    
    int t = 1;
    cin &gt;&gt; t; // Uncomment if multiple test cases exist
    while (t--) {
        solve();
    }
    return 0;
}</code></pre>
                </div>
            </div>
            <div class="p-4 border-t border-cpBorder bg-cpCardHover/50 flex justify-end">
                <button onclick="copyTemplateCode()" class="px-4 py-2 bg-cyan-500 hover:bg-cyan-400 text-black font-mono font-bold text-xs rounded-xl flex items-center gap-2 transition-all">
                    <i class="fa-regular fa-copy"></i> Copy Full Template
                </button>
            </div>
        </div>
    </div>

    <!-- CP TOOLBOX MODAL (Calculators & Visualizers) -->
    <div id="tools-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-cpCard border border-cpBorder rounded-2xl w-full max-w-3xl flex flex-col shadow-2xl overflow-hidden">
            <div class="p-5 border-b border-cpBorder flex items-center justify-between bg-cpCardHover/50">
                <h3 class="font-mono font-bold text-white flex items-center gap-2">
                    <i class="fa-solid fa-calculator text-purple-400"></i> CP Toolbox & Operations Estimator
                </h3>
                <button onclick="closeModal('tools-modal')" class="w-8 h-8 rounded-lg bg-cpBorder/50 flex items-center justify-center text-slate-400 hover:text-white">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            <div class="p-6 space-y-6">
                <!-- 1. Time Limit vs Operation Estimator -->
                <div class="space-y-3 bg-slate-900/60 p-4 rounded-xl border border-cpBorder">
                    <h4 class="font-mono text-sm font-bold text-cyan-400 flex items-center gap-2">
                        <i class="fa-solid fa-gauge-high"></i> Time Limit Operation Estimator (1 sec ≈ 10⁸ ops)
                    </h4>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 font-mono text-xs">
                        <div>
                            <label class="text-slate-400 block mb-1">Input Size (N):</label>
                            <input type="number" id="calc-n" value="100000" class="w-full bg-cpDark border border-cpBorder rounded px-3 py-2 text-white focus:outline-none focus:border-cyan-500" oninput="calculateComplexity()">
                        </div>
                        <div>
                            <label class="text-slate-400 block mb-1">Estimated Max Operations:</label>
                            <div id="calc-ops-result" class="text-lg font-bold text-emerald-400 pt-1">O(N log N) ≈ 1.7 × 10⁶ ops</div>
                        </div>
                    </div>
                    <div class="text-[11px] text-slate-400 font-mono mt-2 leading-relaxed">
                        • N ≤ 10..12 &rarr; O(N!) or O(2ⁿ)<br>
                        • N ≤ 20 &rarr; O(2ⁿ · N)<br>
                        • N ≤ 500 &rarr; O(N³)<br>
                        • N ≤ 5000 &rarr; O(N²)<br>
                        • N ≤ 2·10⁵ &rarr; O(N log N) or O(N log² N)<br>
                        • N ≤ 10⁷ &rarr; O(N)<br>
                        • N &gt; 10⁹ &rarr; O(log N) or O(1)
                    </div>
                </div>

                <!-- 2. Fast Bitwise Helper -->
                <div class="space-y-3 bg-slate-900/60 p-4 rounded-xl border border-cpBorder font-mono text-xs">
                    <h4 class="font-bold text-purple-400 flex items-center gap-2">
                        <i class="fa-solid fa-microchip"></i> Built-in GCC Bitwise Functions Cheat Sheet
                    </h4>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-slate-300">
                        <div class="p-2 bg-cpDark rounded border border-cpBorder">
                            <code class="text-cyan-300">__builtin_popcountll(x)</code>
                            <div class="text-[10px] text-slate-400">Count set bits (1s) in unsigned 64-bit int</div>
                        </div>
                        <div class="p-2 bg-cpDark rounded border border-cpBorder">
                            <code class="text-cyan-300">__builtin_clzll(x)</code>
                            <div class="text-[10px] text-slate-400">Count leading zeroes</div>
                        </div>
                        <div class="p-2 bg-cpDark rounded border border-cpBorder">
                            <code class="text-cyan-300">__builtin_ctzll(x)</code>
                            <div class="text-[10px] text-slate-400">Count trailing zeroes</div>
                        </div>
                        <div class="p-2 bg-cpDark rounded border border-cpBorder">
                            <code class="text-cyan-300">31 - __builtin_clz(x)</code>
                            <div class="text-[10px] text-slate-400">Floor log2(x) calculation</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- MAIN JAVASCRIPT LOGIC -->
    <script>
        // --- CP TOPICS DATABASE ---
        const cpData = [
            {
                category: "1. Language Mastery & STL Techniques",
                description: "Fundamental C++ constructs, Standard Template Library container complexities, and bitwise tricks essential for high-speed CP problem solving.",
                topics: [
                    {
                        id: "cpp-fast-io",
                        title: "C++ Fast I/O & Pragma Optimizations",
                        difficulty: "Beginner",
                        timeComp: "O(1)",
                        spaceComp: "O(1)",
                        desc: "Disables synchronization between C and C++ standard streams and unties cin from cout to prevent bottleneck delays during massive input parsing (e.g. 10^6 integers).",
                        code: `ios_base::sync_with_stdio(false);\ncin.tie(NULL);\n// Use '\n' instead of endl to avoid costly buffer flushes`,
                        problems: [
                            { name: "CSES - Weird Algorithm", link: "https://cses.fi/problemset/task/1068", platform: "CSES" },
                            { name: "Codeforces 4A - Watermelon", link: "https://codeforces.com/problemset/problem/4/A", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "cpp-stl-containers",
                        title: "C++ STL (Vector, Set, Map, Priority Queue)",
                        difficulty: "Beginner",
                        timeComp: "O(log N)",
                        spaceComp: "O(N)",
                        desc: "Mastering std::vector, std::set (red-black tree), std::unordered_map (hash table with O(1) average), and std::priority_queue (max/min heap).",
                        code: `vector<int> v;\nset<int> st; // O(log N) insertion & find\nunordered_map<int, int> mp; // O(1) avg lookup\npriority_queue<int, vector<int>, greater<int>> min_heap;`,
                        problems: [
                            { name: "CSES - Distinct Numbers", link: "https://cses.fi/problemset/task/1621", platform: "CSES" },
                            { name: "Codeforces 1020B - Badge", link: "https://codeforces.com/problemset/problem/1020/B", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "cpp-binary-search-stl",
                        title: "std::lower_bound & std::upper_bound",
                        difficulty: "Beginner",
                        timeComp: "O(log N)",
                        spaceComp: "O(1)",
                        desc: "STL functions for binary searching on sorted containers. lower_bound finds first element >= target; upper_bound finds first element > target.",
                        code: `vector<int> a = {1, 3, 3, 5, 8};\nauto it1 = lower_bound(a.begin(), a.end(), 3); // Points to index 1\nauto it2 = upper_bound(a.begin(), a.end(), 3); // Points to index 3\nint count_3 = it2 - it1; // 2`,
                        problems: [
                            { name: "CSES - Concert Tickets", link: "https://cses.fi/problemset/task/1091", platform: "CSES" },
                            { name: "Codeforces 706B - Interesting Drink", link: "https://codeforces.com/problemset/problem/706/B", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "cpp-bitwise-ops",
                        title: "Bitwise Manipulations & GCC Intrinsics",
                        difficulty: "Intermediate",
                        timeComp: "O(1)",
                        spaceComp: "O(1)",
                        desc: "Performing set operations, mask checks, and power-of-two tests using bitwise operators (`&`, `|`, `^`, `<<`, `>>`) and hardware-accelerated intrinsics.",
                        code: `int mask = (1 << k); // k-th bit set\nbool is_set = (n & (1 << k));\nint set_bits = __builtin_popcountll(n); // Number of 1s\nint leading_zeros = __builtin_clzll(n);`,
                        problems: [
                            { name: "CSES - Creating Strings", link: "https://cses.fi/problemset/task/1622", platform: "CSES" },
                            { name: "Codeforces 550B - Preparing Olympiad", link: "https://codeforces.com/problemset/problem/550/B", platform: "Codeforces" }
                        ]
                    }
                ]
            },
            {
                category: "2. Basic Math & Number Theory",
                description: "Fundamental mathematical algorithms required for integer arithmetic, modular calculations, prime factorizations, and combinatorics.",
                topics: [
                    {
                        id: "math-gcd-lcm",
                        title: "Euclidean GCD & LCM",
                        difficulty: "Beginner",
                        timeComp: "O(log(min(A, B)))",
                        spaceComp: "O(1)",
                        desc: "Greatest Common Divisor using recursive Euclidean subtraction/modulo, and Least Common Multiple derived via (A * B) / GCD(A, B).",
                        code: `long long gcd(long long a, long long b) {\n    return b == 0 ? a : gcd(b, a % b);\n}\nlong long lcm(long long a, long long b) {\n    return (a / gcd(a, b)) * b;\n}`,
                        problems: [
                            { name: "Codeforces 1342A - Road to Zero", link: "https://codeforces.com/problemset/problem/1342/A", platform: "Codeforces" },
                            { name: "CSES - Common Divisors", link: "https://cses.fi/problemset/task/1081", platform: "CSES" }
                        ]
                    },
                    {
                        id: "math-sieve",
                        title: "Sieve of Eratosthenes",
                        difficulty: "Beginner",
                        timeComp: "O(N log log N)",
                        spaceComp: "O(N)",
                        desc: "Precalculating prime numbers up to N by iteratively marking multiples of each prime starting from 2.",
                        code: `const int MAXN = 1e7;\nvector<bool> is_prime(MAXN + 1, true);\nis_prime[0] = is_prime[1] = false;\nfor (int p = 2; p * p <= MAXN; p++) {\n    if (is_prime[p]) {\n        for (int i = p * p; i <= MAXN; i += p)\n            is_prime[i] = false;\n    }\n}`,
                        problems: [
                            { name: "CSES - Counting Divisors", link: "https://cses.fi/problemset/task/1713", platform: "CSES" },
                            { name: "Codeforces 26A - Almost Prime", link: "https://codeforces.com/problemset/problem/26/A", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "math-binary-exp",
                        title: "Binary Exponentiation & Modular Inverse",
                        difficulty: "Intermediate",
                        timeComp: "O(log exponent)",
                        spaceComp: "O(1)",
                        desc: "Computing (base^exp) % MOD in logarithmic time using bit decomposition. Compute modular inverse via Fermat's Little Theorem a^(MOD-2) % MOD for prime MOD.",
                        code: `long long power(long long base, long long exp, long long mod) {\n    long long res = 1;\n    base %= mod;\n    while (exp > 0) {\n        if (exp % 2 == 1) res = (res * base) % mod;\n        base = (base * base) % mod;\n        exp /= 2;\n    }\n    return res;\n}\nlong long modInverse(long long n, long long mod) {\n    return power(n, mod - 2, mod);\n}`,
                        problems: [
                            { name: "CSES - Exponentiation", link: "https://cses.fi/problemset/task/1095", platform: "CSES" },
                            { name: "Codeforces 300C - Beautiful Numbers", link: "https://codeforces.com/problemset/problem/300/C", platform: "Codeforces" }
                        ]
                    }
                ]
            },
            {
                category: "3. Array & Sequence Techniques",
                description: "High-efficiency 1D/2D array manipulation techniques to compute range queries, sliding subsegments, and pointer bounds in linear time.",
                topics: [
                    {
                        id: "seq-prefix-sum",
                        title: "1D & 2D Prefix Sums",
                        difficulty: "Beginner",
                        timeComp: "O(1) per Query",
                        spaceComp: "O(N * M)",
                        desc: "Preprocessing array cumulative totals allowing subsegment sum queries in constant time. 2D prefix sums extend this principle to sub-rectangle queries.",
                        code: `// 1D Prefix Sum\nvector<long long> pref(n + 1, 0);\nfor(int i = 0; i < n; i++) pref[i+1] = pref[i] + a[i];\n// Range sum [L, R] = pref[R+1] - pref[L]`,
                        problems: [
                            { name: "CSES - Static Range Sum Queries", link: "https://cses.fi/problemset/task/1646", platform: "CSES" },
                            { name: "USACO - Subsequences Summing to Sevens", link: "http://www.usaco.org/index.php?page=viewproblem2&cpid=595", platform: "USACO" }
                        ]
                    },
                    {
                        id: "seq-two-pointers",
                        title: "Two Pointers Technique",
                        difficulty: "Beginner",
                        timeComp: "O(N)",
                        spaceComp: "O(1)",
                        desc: "Iterating two indices across monotonic sequence structures to solve pair searching, target sum matching, or subsegment conditions in a single pass.",
                        code: `int l = 0, r = n - 1;\nwhile (l < r) {\n    int sum = a[l] + a[r];\n    if (sum == target) return true;\n    else if (sum < target) l++;\n    else r--;\n}`,
                        problems: [
                            { name: "CSES - Sum of Two Values", link: "https://cses.fi/problemset/task/1640", platform: "CSES" },
                            { name: "Codeforces 601A - The Two Routes", link: "https://codeforces.com/problemset/problem/601/A", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "seq-sliding-window",
                        title: "Sliding Window & Deque Optimization",
                        difficulty: "Intermediate",
                        timeComp: "O(N)",
                        spaceComp: "O(K)",
                        desc: "Maintaining a sliding interval over an array to maintain dynamic properties like range maximum/minimum using std::deque in linear time.",
                        code: `deque<int> dq; // Stores indices\nfor (int i = 0; i < n; i++) {\n    if (!dq.empty() && dq.front() <= i - k) dq.pop_front();\n    while (!dq.empty() && a[dq.back()] <= a[i]) dq.pop_back();\n    dq.push_back(i);\n    if (i >= k - 1) cout << a[dq.front()] << " ";\n}`,
                        problems: [
                            { name: "CSES - Sliding Window Median", link: "https://cses.fi/problemset/task/1076", platform: "CSES" },
                            { name: "Codeforces 1195E - Open-pit Mining", link: "https://codeforces.com/problemset/problem/1195/E", platform: "Codeforces" }
                        ]
                    }
                ]
            },
            {
                category: "4. Searching & Custom Sorting",
                description: "Using binary searching beyond standard arrays onto answer spaces (Monotonic Decision Functions), ternary search, and custom lambda ordering.",
                topics: [
                    {
                        id: "search-binary-answer",
                        title: "Binary Search on Answer Space",
                        difficulty: "Intermediate",
                        timeComp: "O(N log(SearchSpace))",
                        spaceComp: "O(1)",
                        desc: "Converting optimization problems ('Find min/max X') into decision problems ('Is X feasible?') over a monotonic predicate function.",
                        code: `long long low = 1, high = 1e18, ans = high;\nauto check = [&](long long mid) -> bool {\n    // Return true if mid satisfies problem condition\n    return true;\n};\nwhile (low <= high) {\n    long long mid = low + (high - low) / 2;\n    if (check(mid)) { ans = mid; high = mid - 1; }\n    else { low = mid + 1; }\n}`,
                        problems: [
                            { name: "CSES - Factory Machines", link: "https://cses.fi/problemset/task/1620", platform: "CSES" },
                            { name: "Codeforces 1201C - Maximum Median", link: "https://codeforces.com/problemset/problem/1201/C", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "search-ternary",
                        title: "Ternary Search",
                        difficulty: "Intermediate",
                        timeComp: "O(log3(SearchSpace))",
                        spaceComp: "O(1)",
                        desc: "Finding the local minimum or maximum of a unimodal function by dividing search domain into three equal sub-parts.",
                        code: `double low = 0, high = 1e9;\nfor (int i = 0; i < 100; i++) {\n    double m1 = low + (high - low) / 3;\n    double m2 = high - (high - low) / 3;\n    if (f(m1) < f(m2)) low = m1; // To find maximum\n    else high = m2;\n}`,
                        problems: [
                            { name: "Codeforces 578C - Weakness and Algorithms", link: "https://codeforces.com/problemset/problem/578/C", platform: "Codeforces" },
                            { name: "AtCoder - Restructuring", link: "https://atcoder.jp/contests/abc130/tasks", platform: "AtCoder" }
                        ]
                    }
                ]
            },
            {
                category: "5. Dynamic Programming (DP)",
                description: "Breaking complex optimization problems into overlapping subproblems with state memoization, space compression, and advanced optimizations.",
                topics: [
                    {
                        id: "dp-classics",
                        title: "Classic DP (Knapsack, LIS, LCS)",
                        difficulty: "Intermediate",
                        timeComp: "O(N * W) or O(N log N)",
                        spaceComp: "O(N * W)",
                        desc: "Core DP paradigms including 0/1 Knapsack, Longest Common Subsequence (LCS), and Patient Sorting LIS in O(N log N).",
                        code: `// LIS in O(N log N) using std::lower_bound\nvector<int> dp;\nfor (int x : a) {\n    auto it = lower_bound(dp.begin(), dp.end(), x);\n    if (it == dp.end()) dp.push_back(x);\n    else *it = x;\n}\nint lis = dp.size();`,
                        problems: [
                            { name: "CSES - Dice Combinations", link: "https://cses.fi/problemset/task/1633", platform: "CSES" },
                            { name: "CSES - Increasing Subsequence", link: "https://cses.fi/problemset/task/1145", platform: "CSES" },
                            { name: "Codeforces 1114D - Flood Fill", link: "https://codeforces.com/problemset/problem/1114/D", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "dp-bitmask",
                        title: "Bitmask DP",
                        difficulty: "Advanced",
                        timeComp: "O(2^N * N^2)",
                        spaceComp: "O(2^N * N)",
                        desc: "Representing set state selections using integer binary bitmasks, used heavily in TSP-like problems where N <= 20.",
                        code: `int dp[1 << N][N];\n// dp[mask][u] = min cost to visit sub-set 'mask' ending at vertex 'u'\nfor (int mask = 0; mask < (1 << N); mask++) {\n    for (int u = 0; u < N; u++) {\n        if (!(mask & (1 << u))) continue;\n        // Transition to next unvisited node v\n    }\n}`,
                        problems: [
                            { name: "CSES - Elevator Rides", link: "https://cses.fi/problemset/task/1653", platform: "CSES" },
                            { name: "AtCoder Educational DP - Grouping", link: "https://atcoder.jp/contests/dp/tasks/dp_u", platform: "AtCoder" }
                        ]
                    },
                    {
                        id: "dp-tree",
                        title: "Tree DP & Rerooting DP",
                        difficulty: "Advanced",
                        timeComp: "O(N)",
                        spaceComp: "O(N)",
                        desc: "Computing optimal sub-tree values recursively via DFS and using two-pass DFS techniques to reroot trees in linear time.",
                        code: `void dfs(int u, int p) {\n    dp[u] = 1;\n    for (int v : adj[u]) {\n        if (v == p) continue;\n        dfs(v, u);\n        dp[u] += dp[v]; // Combine subtree answers\n    }\n}`,
                        problems: [
                            { name: "CSES - Tree Matching", link: "https://cses.fi/problemset/task/1130", platform: "CSES" },
                            { name: "CSES - Tree Distances I", link: "https://cses.fi/problemset/task/1132", platform: "CSES" }
                        ]
                    },
                    {
                        id: "dp-optimizations",
                        title: "Convex Hull Trick (CHT) & SOS DP",
                        difficulty: "Expert",
                        timeComp: "O(N) or O(N 2^N)",
                        spaceComp: "O(N)",
                        desc: "Advanced techniques like Convex Hull Trick for linear state transitions (y = mx + c) and Sum Over Subsets (SOS DP).",
                        code: `// Line container structure for dynamic CHT\nstruct Line { long long m, k; long long eval(long long x){ return m*x + k; } };`,
                        problems: [
                            { name: "Codeforces 319C - Kalila and Dimna in the Logging Industry", link: "https://codeforces.com/problemset/problem/319/C", platform: "Codeforces" },
                            { name: "CSES - Subarray Squares", link: "https://cses.fi/problemset/task/2084", platform: "CSES" }
                        ]
                    }
                ]
            },
            {
                category: "6. Data Structures (Basic to Advanced)",
                description: "Hierarchical, tree-based, dynamic range query, and point modification structures engineered for rapid competitive queries.",
                topics: [
                    {
                        id: "ds-dsu",
                        title: "Disjoint Set Union (DSU / Union-Find)",
                        difficulty: "Intermediate",
                        timeComp: "O(α(N)) ≈ O(1)",
                        spaceComp: "O(N)",
                        desc: "Tracks partitioned sets with Path Compression and Union by Rank/Size algorithms.",
                        code: `struct DSU {\n    vector<int> parent, size;\n    DSU(int n) {\n        parent.resize(n);\n        iota(parent.begin(), parent.end(), 0);\n        size.assign(n, 1);\n    }\n    int find(int i) {\n        if (parent[i] == i) return i;\n        return parent[i] = find(parent[i]);\n    }\n    void unite(int i, int j) {\n        int root_i = find(i), root_j = find(j);\n        if (root_i != root_j) {\n            if (size[root_i] < size[root_j]) swap(root_i, root_j);\n            parent[root_j] = root_i;\n            size[root_i] += size[root_j];\n        }\n    }\n};`,
                        problems: [
                            { name: "CSES - Road Construction", link: "https://cses.fi/problemset/task/1676", platform: "CSES" },
                            { name: "Codeforces 25D - Roads not only in Berland", link: "https://codeforces.com/problemset/problem/25/D", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "ds-fenwick",
                        title: "Fenwick Tree (Binary Indexed Tree - BIT)",
                        difficulty: "Intermediate",
                        timeComp: "O(log N)",
                        spaceComp: "O(N)",
                        desc: "Space-efficient structure supporting point updates and prefix sum range queries using lowest set bit (`idx & -idx`).",
                        code: `struct Fenwick {\n    int n; vector<long long> tree;\n    Fenwick(int n) : n(n), tree(n + 1, 0) {}\n    void add(int i, long long delta) {\n        for (; i <= n; i += i & -i) tree[i] += delta;\n    }\n    long long query(int i) {\n        long long sum = 0;\n        for (; i > 0; i -= i & -i) sum += tree[i];\n        return sum;\n    }\n};`,
                        problems: [
                            { name: "CSES - Dynamic Range Sum Queries", link: "https://cses.fi/problemset/task/1648", platform: "CSES" },
                            { name: "Codeforces 339D - Xenia and Bit Operations", link: "https://codeforces.com/problemset/problem/339/D", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "ds-segment-tree",
                        title: "Segment Tree with Lazy Propagation",
                        difficulty: "Advanced",
                        timeComp: "O(log N)",
                        spaceComp: "O(4N)",
                        desc: "Versatile binary tree structure capable of range minimum/maximum/sum queries and arbitrary range updates using lazy propagation.",
                        code: `// Segment Tree node representation\nvoid updateRange(int node, int start, int end, int l, int r, long long val) {\n    if (lazy[node] != 0) { // Push lazy updates down\n        tree[node] += (end - start + 1) * lazy[node];\n        if (start != end) { lazy[2*node] += lazy[node]; lazy[2*node+1] += lazy[node]; }\n        lazy[node] = 0;\n    }\n    // Standard range update logic...\n}`,
                        problems: [
                            { name: "CSES - Range Update Queries", link: "https://cses.fi/problemset/task/1651", platform: "CSES" },
                            { name: "Codeforces 52C - Circular RMQ", link: "https://codeforces.com/problemset/problem/52/C", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "ds-sparse-table",
                        title: "Sparse Table (Static Range Minimum Query)",
                        difficulty: "Intermediate",
                        timeComp: "O(N log N) Build, O(1) Query",
                        spaceComp: "O(N log N)",
                        desc: "Precomputes static range idempotent queries (min, max, gcd) to answer range queries in pure constant O(1) time.",
                        code: `int st[20][MAXN];\nvoid build(vector<int>& a) {\n    int n = a.size();\n    for (int i = 0; i < n; i++) st[0][i] = a[i];\n    for (int j = 1; j < 20; j++)\n        for (int i = 0; i + (1 << j) <= n; i++)\n            st[j][i] = min(st[j-1][i], st[j-1][i + (1 << (j-1))]);\n}\nint query(int L, int R) {\n    int j = 31 - __builtin_clz(R - L + 1);\n    return min(st[j][L], st[j][R - (1 << j) + 1]);\n}`,
                        problems: [
                            { name: "CSES - Static Range Minimum Queries", link: "https://cses.fi/problemset/task/1647", platform: "CSES" },
                            { name: "Codeforces 1454F - Array Partition", link: "https://codeforces.com/problemset/problem/1454/F", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "ds-pbds",
                        title: "Policy-Based Data Structures (pbds / indexed_set)",
                        difficulty: "Advanced",
                        timeComp: "O(log N)",
                        spaceComp: "O(N)",
                        desc: "GNU C++ extension providing order-statistic trees that support finding the K-th smallest element and rank of an element in O(log N).",
                        code: `#include <ext/pb_ds/assoc_container.hpp>\n#include <ext/pb_ds/tree_policy.hpp>\nusing namespace __gnu_pbds;\ntemplate <typename T>\nusing ordered_set = tree<T, null_type, less<T>, rb_tree_tag, tree_order_statistics_node_update>;\n\nordered_set<int> st;\nst.insert(5);\nst.find_by_order(0); // Iterator to 0th smallest\nst.order_of_key(5);   // Number of elements strictly smaller than 5`,
                        problems: [
                            { name: "CSES - List Removals", link: "https://cses.fi/problemset/task/1749", platform: "CSES" },
                            { name: "Codeforces 1042D - Parray Pairs", link: "https://codeforces.com/problemset/problem/1042/D", platform: "Codeforces" }
                        ]
                    }
                ]
            },
            {
                category: "7. Graph Theory & Network Algorithms",
                description: "Comprehensive algorithms spanning graph traversals, shortest path routing, tree LCA decomposition, flow networks, and connectivity.",
                topics: [
                    {
                        id: "graph-bfs-dfs",
                        title: "BFS, DFS & Flood Fill Traversals",
                        difficulty: "Beginner",
                        timeComp: "O(V + E)",
                        spaceComp: "O(V)",
                        desc: "Breadth-First Search (queue) for unweighted shortest paths and Depth-First Search (stack/recursion) for connected components and topological discovery.",
                        code: `void dfs(int u) {\n    visited[u] = true;\n    for (int v : adj[u]) {\n        if (!visited[v]) dfs(v);\n    }\n}`,
                        problems: [
                            { name: "CSES - Counting Rooms", link: "https://cses.fi/problemset/task/1192", platform: "CSES" },
                            { name: "CSES - Labyrinth", link: "https://cses.fi/problemset/task/1193", platform: "CSES" }
                        ]
                    },
                    {
                        id: "graph-shortest-path",
                        title: "Shortest Paths (Dijkstra, 0-1 BFS, Floyd-Warshall)",
                        difficulty: "Intermediate",
                        timeComp: "O(E log V) / O(V^3)",
                        spaceComp: "O(V + E)",
                        desc: "Dijkstra using priority_queue for non-negative weights; 0-1 BFS using deque for binary weights; Floyd-Warshall for all-pairs shortest paths.",
                        code: `priority_queue<pll, vector<pll>, greater<pll>> pq;\ndist[src] = 0; pq.push({0, src});\nwhile (!pq.empty()) {\n    auto [d, u] = pq.top(); pq.pop();\n    if (d > dist[u]) continue;\n    for (auto& edge : adj[u]) {\n        if (dist[u] + edge.weight < dist[edge.v]) {\n            dist[edge.v] = dist[u] + edge.weight;\n            pq.push({dist[edge.v], edge.v});\n        }\n    }\n}`,
                        problems: [
                            { name: "CSES - Shortest Routes I", link: "https://cses.fi/problemset/task/1671", platform: "CSES" },
                            { name: "Codeforces 20C - Dijkstra?", link: "https://codeforces.com/problemset/problem/20/C", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "graph-lca-binary-lifting",
                        title: "Lowest Common Ancestor (Binary Lifting)",
                        difficulty: "Advanced",
                        timeComp: "O(N log N) Precalc, O(log N) Query",
                        spaceComp: "O(N log N)",
                        desc: "Binary lifting algorithm for computing the Lowest Common Ancestor (LCA) and tree node distances in logarithmic time.",
                        code: `int up[MAXN][LOGN];\nint get_lca(int u, int v) {\n    if (depth[u] < depth[v]) swap(u, v);\n    for (int j = LOGN - 1; j >= 0; j--) {\n        if (depth[u] - (1 << j) >= depth[v]) u = up[u][j];\n    }\n    if (u == v) return u;\n    for (int j = LOGN - 1; j >= 0; j--) {\n        if (up[u][j] != up[v][j]) { u = up[u][j]; v = up[v][j]; }\n    }\n    return up[u][0];\n}`,
                        problems: [
                            { name: "CSES - Company Queries II", link: "https://cses.fi/problemset/task/1688", platform: "CSES" },
                            { name: "Codeforces 1304E - 1-Trees and Queries", link: "https://codeforces.com/problemset/problem/1304/E", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "graph-scc-tarjan",
                        title: "Strongly Connected Components (Tarjan / Kosaraju)",
                        difficulty: "Advanced",
                        timeComp: "O(V + E)",
                        spaceComp: "O(V)",
                        desc: "Decomposing directed graphs into maximal strongly connected subgraphs where every vertex is reachable from any other vertex.",
                        code: `void kosaraju_dfs1(int u) {\n    vis[u] = true;\n    for (int v : adj[u]) if (!vis[v]) kosaraju_dfs1(v);\n    order.push_back(u);\n}\nvoid kosaraju_dfs2(int u, int component_id) {\n    comp[u] = component_id;\n    for (int v : adj_rev[u]) if (comp[v] == 0) kosaraju_dfs2(v, component_id);\n}`,
                        problems: [
                            { name: "CSES - Planets and Kingdoms", link: "https://cses.fi/problemset/task/1683", platform: "CSES" },
                            { name: "Codeforces 427C - Checkposts", link: "https://codeforces.com/problemset/problem/427/C", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "graph-max-flow",
                        title: "Network Flow (Dinic's & Push-Relabel Algorithm)",
                        difficulty: "Expert",
                        timeComp: "O(V^2 E)",
                        spaceComp: "O(V + E)",
                        desc: "Finding maximum network flow from source to sink using Dinic's layered level graph BFS/DFS augmentations.",
                        code: `// Dinic's Algorithm level graph generation & blocking flow augmentation`,
                        problems: [
                            { name: "CSES - Download Speed", link: "https://cses.fi/problemset/task/1694", platform: "CSES" },
                            { name: "CSES - Police Chase", link: "https://cses.fi/problemset/task/1695", platform: "CSES" }
                        ]
                    }
                ]
            },
            {
                category: "8. String Processing & Pattern Matching",
                description: "String matching, rolling hashes, prefix functions, trie trees, and linear exact substring searching algorithms.",
                topics: [
                    {
                        id: "str-hashing",
                        title: "String Hashing (Polynomial Double Hash)",
                        difficulty: "Intermediate",
                        timeComp: "O(N) Precalc, O(1) Substring Query",
                        spaceComp: "O(N)",
                        desc: "Converting substrings into integer hash codes modulo large primes to enable O(1) equality comparisons.",
                        code: `long long compute_hash(string const& s) {\n    const int p = 31;\n    const int m = 1e9 + 9;\n    long long hash_value = 0, p_pow = 1;\n    for (char c : s) {\n        hash_value = (hash_value + (c - 'a' + 1) * p_pow) % m;\n        p_pow = (p_pow * p) % m;\n    }\n    return hash_value;\n}`,
                        problems: [
                            { name: "CSES - String Matching", link: "https://cses.fi/problemset/task/1753", platform: "CSES" },
                            { name: "Codeforces 271D - Good Substrings", link: "https://codeforces.com/problemset/problem/271/D", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "str-kmp-z",
                        title: "KMP Algorithm & Z-Function",
                        difficulty: "Advanced",
                        timeComp: "O(N)",
                        spaceComp: "O(N)",
                        desc: "Linear pattern matching using the Knuth-Morris-Pratt prefix function array or the Z-algorithm for longest common prefixes.",
                        code: `vector<int> prefix_function(string s) {\n    int n = (int)s.length();\n    vector<int> pi(n);\n    for (int i = 1; i < n; i++) {\n        int j = pi[i-1];\n        while (j > 0 && s[i] != s[j]) j = pi[j-1];\n        if (s[i] == s[j]) j++;\n        pi[i] = j;\n    }\n    return pi;\n}`,
                        problems: [
                            { name: "CSES - Finding Borders", link: "https://cses.fi/problemset/task/1732", platform: "CSES" },
                            { name: "Codeforces 126B - Password", link: "https://codeforces.com/problemset/problem/126/B", platform: "Codeforces" }
                        ]
                    },
                    {
                        id: "str-trie",
                        title: "Trie Data Structure & Maximum XOR Pair",
                        difficulty: "Intermediate",
                        timeComp: "O(Length)",
                        spaceComp: "O(N * Σ)",
                        desc: "Prefix tree structure for rapid dictionary string lookups and binary bitwise Trie operations for finding maximum XOR pairs.",
                        code: `struct TrieNode {\n    TrieNode* child[2] = {nullptr, nullptr};\n};\nvoid insert(TrieNode* root, int val) {\n    TrieNode* curr = root;\n    for (int i = 31; i >= 0; i--) {\n        int bit = (val >> i) & 1;\n        if (!curr->child[bit]) curr->child[bit] = new TrieNode();\n        curr = curr->child[bit];\n    }\n}`,
                        problems: [
                            { name: "Codeforces 706D - Search in Bitland", link: "https://codeforces.com/problemset/problem/706/D", platform: "Codeforces" },
                            { name: "CSES - Word Combinations", link: "https://cses.fi/problemset/task/1731", platform: "CSES" }
                        ]
                    }
                ]
            },
            {
                category: "9. Advanced Techniques & Geometry",
                description: "Niche CP topics including offline Mo's query algorithm, 2D vector geometry, Graham Scan convex hull, and FFT signal processing.",
                topics: [
                    {
                        id: "adv-mo-algorithm",
                        title: "Mo's Algorithm (Offline Range Queries)",
                        difficulty: "Advanced",
                        timeComp: "O((N + Q) * sqrt(N))",
                        spaceComp: "O(N + Q)",
                        desc: "Sorting range queries in block order (size sqrt(N)) to process queries offline by expanding/shrinking pointers efficiently.",
                        code: `int BLOCK_SIZE;\nstruct Query {\n    int l, r, id;\n    bool operator<(const Query& other) const {\n        int b1 = l / BLOCK_SIZE, b2 = other.l / BLOCK_SIZE;\n        if (b1 != b2) return b1 < b2;\n        return (b1 & 1) ? r < other.r : r > other.r;\n    }\n};`,
                        problems: [
                            { name: "Codeforces 86D - Powerful array", link: "https://codeforces.com/problemset/problem/86/D", platform: "Codeforces" },
                            { name: "CSES - Distinct Values Queries", link: "https://cses.fi/problemset/task/1734", platform: "CSES" }
                        ]
                    },
                    {
                        id: "adv-geometry-convex-hull",
                        title: "2D Computational Geometry & Convex Hull",
                        difficulty: "Expert",
                        timeComp: "O(N log N)",
                        spaceComp: "O(N)",
                        desc: "2D point vector operations (dot/cross products) and Graham Scan or Andrew's Monotone Chain algorithm for Convex Hull construction.",
                        code: `struct Point { long long x, y; };\nlong long cross_product(Point a, Point b, Point c) {\n    return (b.x - a.x) * (c.y - a.y) - (b.y - a.y) * (c.x - a.x);\n}`,
                        problems: [
                            { name: "CSES - Polygon Area", link: "https://cses.fi/problemset/task/2191", platform: "CSES" },
                            { name: "CSES - Convex Hull", link: "https://cses.fi/problemset/task/2195", platform: "CSES" }
                        ]
                    }
                ]
            }
        ];

        // --- APP STATE ---
        let topicStatusMap = JSON.parse(localStorage.getItem('cp_topic_status_v1')) || {};
        let userStreak = parseInt(localStorage.getItem('cp_streak_v1')) || 0;
        let activeDiffFilter = 'all';
        let activeCategoryFilter = 'all';
        let currentModalTopic = null;

        // --- INITIALIZATION ---
        window.onload = function() {
            renderCategoryPills();
            renderRoadmap();
            updateStats();
        };

        // --- STATS COMPUTATION ---
        function updateStats() {
            let total = 0;
            let mastered = 0;

            cpData.forEach(cat => {
                cat.topics.forEach(t => {
                    total++;
                    if (topicStatusMap[t.id] === 'mastered') mastered++;
                });
            });

            const percent = total > 0 ? Math.round((mastered / total) * 100) : 0;

            document.getElementById('stat-total').innerText = total;
            document.getElementById('stat-mastered').innerText = mastered;
            document.getElementById('stat-percent').innerText = `${percent}%`;
            document.getElementById('stat-streak').innerText = `${userStreak} Days`;
            document.getElementById('main-progress-bar').style.width = `${percent}%`;
        }

        // --- STREAK MANAGEMENT ---
        function incrementStreak() {
            userStreak++;
            localStorage.setItem('cp_streak_v1', userStreak);
            updateStats();
        }

        function resetProgress() {
            if (confirm("Reset all topic progress and streak history?")) {
                topicStatusMap = {};
                userStreak = 0;
                localStorage.removeItem('cp_topic_status_v1');
                localStorage.removeItem('cp_streak_v1');
                renderRoadmap();
                updateStats();
            }
        }

        // --- RENDER CATEGORY FILTER PILLS ---
        function renderCategoryPills() {
            const container = document.getElementById('category-pills-container');
            let html = `<button class="filter-cat-btn px-3 py-1 rounded-lg border border-cyan-500/40 bg-cyan-500/10 text-cyan-400 font-medium hover:bg-cyan-500/20 transition-all" data-cat="all" onclick="setCategoryFilter('all', this)">All Categories</button>`;

            cpData.forEach((cat, idx) => {
                const catShort = cat.category.split('.')[1] ? cat.category.split('.')[1].trim() : cat.category;
                html += `<button class="filter-cat-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all whitespace-nowrap" data-cat="${idx}" onclick="setCategoryFilter('${idx}', this)">${catShort}</button>`;
            });

            container.innerHTML = html;
        }

        // --- MAIN ROADMAP RENDERER ---
        function renderRoadmap() {
            const container = document.getElementById('topics-container');
            const searchVal = document.getElementById('search-input').value.toLowerCase().trim();
            container.innerHTML = '';

            let matchesFound = 0;

            cpData.forEach((cat, catIdx) => {
                // Category Filter Check
                if (activeCategoryFilter !== 'all' && activeCategoryFilter !== String(catIdx)) {
                    return;
                }

                // Filter topics
                const filteredTopics = cat.topics.filter(t => {
                    const matchesSearch = t.title.toLowerCase().includes(searchVal) || 
                                          t.desc.toLowerCase().includes(searchVal) ||
                                          t.id.toLowerCase().includes(searchVal);
                    const matchesDiff = (activeDiffFilter === 'all') || (t.difficulty === activeDiffFilter);
                    return matchesSearch && matchesDiff;
                });

                if (filteredTopics.length === 0) return;
                matchesFound += filteredTopics.length;

                // Create Category Container
                const catBlock = document.createElement('div');
                catBlock.className = 'space-y-4';

                // Category Header
                catBlock.innerHTML = `
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between border-b border-cpBorder/60 pb-3 gap-2">
                        <div>
                            <h3 class="text-lg font-bold font-mono text-white flex items-center gap-2">
                                <span class="text-cyan-400">#</span> ${cat.category}
                            </h3>
                            <p class="text-xs text-slate-400 font-sans mt-0.5">${cat.description}</p>
                        </div>
                        <span class="text-xs font-mono px-2.5 py-1 rounded bg-cpCard border border-cpBorder text-slate-400 self-start sm:self-auto">${filteredTopics.length} Topics</span>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                        ${filteredTopics.map(topic => getTopicCardHTML(topic, cat.category)).join('')}
                    </div>
                `;

                container.appendChild(catBlock);
            });

            const noResultsEl = document.getElementById('no-results');
            if (matchesFound === 0) {
                noResultsEl.classList.remove('hidden');
            } else {
                noResultsEl.classList.add('hidden');
            }
        }

        // --- GENERATE TOPIC CARD HTML ---
        function getTopicCardHTML(topic, categoryName) {
            const status = topicStatusMap[topic.id] || 'unseen'; // 'unseen', 'learning', 'mastered'

            let statusBadge = '';
            let cardBorder = 'border-cpBorder';
            
            if (status === 'mastered') {
                statusBadge = `<span class="px-2 py-0.5 rounded text-[10px] font-mono font-bold bg-emerald-950 text-emerald-400 border border-emerald-800 flex items-center gap-1"><i class="fa-solid fa-check"></i> Mastered</span>`;
                cardBorder = 'border-emerald-500/40 hover:border-emerald-500';
            } else if (status === 'learning') {
                statusBadge = `<span class="px-2 py-0.5 rounded text-[10px] font-mono font-bold bg-amber-950 text-amber-400 border border-amber-800 flex items-center gap-1"><i class="fa-solid fa-spinner animate-spin"></i> Learning</span>`;
                cardBorder = 'border-amber-500/40 hover:border-amber-500';
            } else {
                statusBadge = `<span class="px-2 py-0.5 rounded text-[10px] font-mono font-bold bg-slate-900 text-slate-400 border border-slate-700">Unseen</span>`;
            }

            let diffBadge = '';
            if (topic.difficulty === 'Beginner') diffBadge = 'text-emerald-400 bg-emerald-950/40 border-emerald-800/40';
            else if (topic.difficulty === 'Intermediate') diffBadge = 'text-cyan-400 bg-cyan-950/40 border-cyan-800/40';
            else if (topic.difficulty === 'Advanced') diffBadge = 'text-purple-400 bg-purple-950/40 border-purple-800/40';
            else diffBadge = 'text-pink-400 bg-pink-950/40 border-pink-800/40';

            return `
                <div class="glass-panel p-5 rounded-2xl border ${cardBorder} hover:bg-cpCardHover/80 transition-all duration-200 flex flex-col justify-between group cursor-pointer" onclick="openTopicDetails('${topic.id}', '${categoryName}')">
                    <div class="space-y-3">
                        <div class="flex items-center justify-between gap-2">
                            <span class="px-2 py-0.5 rounded text-[10px] font-mono font-bold uppercase border ${diffBadge}">${topic.difficulty}</span>
                            <!-- Status Toggle Button -->
                            <div onclick="event.stopPropagation(); cycleTopicStatus('${topic.id}')">
                                ${statusBadge}
                            </div>
                        </div>

                        <h4 class="text-base font-bold font-mono text-slate-100 group-hover:text-cyan-400 transition-colors flex items-center justify-between">
                            <span>${topic.title}</span>
                            <i class="fa-solid fa-arrow-right text-xs text-slate-600 group-hover:text-cyan-400 group-hover:translate-x-1 transition-all"></i>
                        </h4>

                        <p class="text-xs text-slate-400 line-clamp-2 leading-relaxed font-sans">
                            ${topic.desc}
                        </p>
                    </div>

                    <div class="pt-4 mt-4 border-t border-cpBorder/50 flex items-center justify-between font-mono text-[11px] text-slate-400">
                        <span class="flex items-center gap-1.5"><i class="fa-solid fa-clock text-amber-400"></i> ${topic.timeComp}</span>
                        <span class="flex items-center gap-1 text-cyan-400 group-hover:underline">Details <i class="fa-solid fa-chevron-right text-[9px]"></i></span>
                    </div>
                </div>
            `;
        }

        // --- CYCLE TOPIC STATUS ON CLICK ---
        function cycleTopicStatus(topicId) {
            const current = topicStatusMap[topicId] || 'unseen';
            let next = 'learning';
            if (current === 'learning') next = 'mastered';
            else if (current === 'mastered') next = 'unseen';

            topicStatusMap[topicId] = next;
            localStorage.setItem('cp_topic_status_v1', JSON.stringify(topicStatusMap));
            renderRoadmap();
            updateStats();

            if (currentModalTopic && currentModalTopic.id === topicId) {
                renderModalStatusButtons(topicId);
            }
        }

        // --- OPEN DETAILED TOPIC MODAL ---
        function openTopicDetails(topicId, categoryName) {
            let topicObj = null;
            cpData.forEach(cat => {
                cat.topics.forEach(t => {
                    if (t.id === topicId) topicObj = t;
                });
            });

            if (!topicObj) return;
            currentModalTopic = topicObj;

            document.getElementById('modal-title').innerText = topicObj.title;
            document.getElementById('modal-category-badge').innerText = categoryName.split('.')[1] || categoryName;
            document.getElementById('modal-description').innerText = topicObj.desc;
            document.getElementById('modal-time-comp').innerText = topicObj.timeComp;
            document.getElementById('modal-space-comp').innerText = topicObj.spaceComp;
            document.getElementById('modal-code').innerText = topicObj.code;

            // Difficulty Tag Styling
            const diffEl = document.getElementById('modal-diff-tag');
            diffEl.innerText = topicObj.difficulty;
            diffEl.className = "px-3 py-1 rounded-lg font-mono text-xs font-bold uppercase ";
            if (topicObj.difficulty === 'Beginner') diffEl.className += "bg-emerald-950 text-emerald-400 border border-emerald-800";
            else if (topicObj.difficulty === 'Intermediate') diffEl.className += "bg-cyan-950 text-cyan-400 border border-cyan-800";
            else if (topicObj.difficulty === 'Advanced') diffEl.className += "bg-purple-950 text-purple-400 border border-purple-800";
            else diffEl.className += "bg-pink-950 text-pink-400 border border-pink-800";

            // Populate Problem Links
            const probContainer = document.getElementById('modal-problems');
            probContainer.innerHTML = topicObj.problems.map(p => `
                <a href="${p.link}" target="_blank" class="p-3 bg-cpDark border border-cpBorder hover:border-cyan-500/50 rounded-xl flex items-center justify-between text-xs font-mono text-slate-200 hover:text-cyan-400 transition-all group">
                    <span class="flex items-center gap-2">
                        <i class="fa-solid fa-arrow-up-right-from-square text-slate-500 group-hover:text-cyan-400"></i>
                        ${p.name}
                    </span>
                    <span class="px-2 py-0.5 bg-cpBorder rounded text-[10px] text-slate-400">${p.platform}</span>
                </a>
            `).join('');

            renderModalStatusButtons(topicId);
            openModal('topic-modal');
        }

        // --- RENDER STATUS BUTTONS IN MODAL ---
        function renderModalStatusButtons(topicId) {
            const status = topicStatusMap[topicId] || 'unseen';
            const btnContainer = document.getElementById('modal-status-buttons');

            btnContainer.innerHTML = `
                <button onclick="setSpecificStatus('${topicId}', 'unseen')" class="px-3 py-1.5 rounded-lg border text-xs font-mono ${status === 'unseen' ? 'bg-slate-700 text-white border-slate-500 font-bold' : 'bg-cpDark text-slate-400 border-cpBorder'} transition-all">
                    Unseen
                </button>
                <button onclick="setSpecificStatus('${topicId}', 'learning')" class="px-3 py-1.5 rounded-lg border text-xs font-mono ${status === 'learning' ? 'bg-amber-950 text-amber-400 border-amber-600 font-bold' : 'bg-cpDark text-slate-400 border-cpBorder'} transition-all">
                    Learning
                </button>
                <button onclick="setSpecificStatus('${topicId}', 'mastered')" class="px-3 py-1.5 rounded-lg border text-xs font-mono ${status === 'mastered' ? 'bg-emerald-950 text-emerald-400 border-emerald-600 font-bold' : 'bg-cpDark text-slate-400 border-cpBorder'} transition-all">
                    Mastered
                </button>
            `;
        }

        function setSpecificStatus(topicId, status) {
            topicStatusMap[topicId] = status;
            localStorage.setItem('cp_topic_status_v1', JSON.stringify(topicStatusMap));
            renderRoadmap();
            updateStats();
            renderModalStatusButtons(topicId);
        }

        // --- SEARCH & FILTER LOGIC ---
        function handleSearchFilter() {
            const val = document.getElementById('search-input').value;
            const clearBtn = document.getElementById('clear-search');
            if (val.length > 0) clearBtn.classList.remove('hidden');
            else clearBtn.classList.add('hidden');

            renderRoadmap();
        }

        function clearSearch() {
            document.getElementById('search-input').value = '';
            document.getElementById('clear-search').classList.add('hidden');
            renderRoadmap();
        }

        function setDiffFilter(diff, btn) {
            activeDiffFilter = diff;
            document.querySelectorAll('.filter-diff-btn').forEach(b => {
                b.className = "filter-diff-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all";
            });
            btn.className = "filter-diff-btn px-3 py-1 rounded-lg border border-cyan-500/40 bg-cyan-500/10 text-cyan-400 font-medium hover:bg-cyan-500/20 transition-all";
            renderRoadmap();
        }

        function setCategoryFilter(catIdx, btn) {
            activeCategoryFilter = catIdx;
            document.querySelectorAll('.filter-cat-btn').forEach(b => {
                b.className = "filter-cat-btn px-3 py-1 rounded-lg border border-cpBorder bg-cpCard text-slate-400 font-medium hover:bg-cpCardHover transition-all whitespace-nowrap";
            });
            btn.className = "filter-cat-btn px-3 py-1 rounded-lg border border-cyan-500/40 bg-cyan-500/10 text-cyan-400 font-medium hover:bg-cyan-500/20 transition-all whitespace-nowrap";
            renderRoadmap();
        }

        // --- MODAL UTILITIES ---
        function openModal(id) {
            document.getElementById(id).classList.remove('hidden');
        }

        function closeModal(id) {
            document.getElementById(id).classList.add('hidden');
        }

        // Copy Helper
        function copySnippetCode() {
            const text = document.getElementById('modal-code').innerText;
            copyToClipboard(text);
            const btnText = document.getElementById('copy-btn-text');
            btnText.innerText = "Copied!";
            setTimeout(() => { btnText.innerText = "Copy Code"; }, 2000);
        }

        function copyTemplateCode() {
            const text = document.getElementById('cpp-template-text').innerText;
            copyToClipboard(text);
            alert("C++ Template copied to clipboard!");
        }

        function copyToClipboard(text) {
            const dummy = document.createElement("textarea");
            document.body.appendChild(dummy);
            dummy.value = text;
            dummy.select();
            document.execCommand("copy");
            document.body.removeChild(dummy);
        }

        // --- COMPLEXITY CALCULATOR LOGIC ---
        function calculateComplexity() {
            const n = parseFloat(document.getElementById('calc-n').value) || 0;
            const resEl = document.getElementById('calc-ops-result');

            if (n <= 0) {
                resEl.innerText = "Invalid N";
                return;
            }

            if (n <= 12) {
                resEl.innerText = `O(N!) ≈ ${(factorial(n)).toExponential(2)} ops (Fits < 1 sec)`;
            } else if (n <= 22) {
                resEl.innerText = `O(2ᴺ · N) ≈ ${(Math.pow(2, n) * n).toExponential(2)} ops (Fits < 1 sec)`;
            } else if (n <= 500) {
                resEl.innerText = `O(N³) ≈ ${(Math.pow(n, 3)).toExponential(2)} ops (Fits < 1 sec)`;
            } else if (n <= 5000) {
                resEl.innerText = `O(N²) ≈ ${(Math.pow(n, 2)).toExponential(2)} ops (Fits < 1 sec)`;
            } else if (n <= 300000) {
                const ops = n * Math.log2(n);
                resEl.innerText = `O(N log N) ≈ ${ops.toExponential(2)} ops (Fits < 1 sec)`;
            } else if (n <= 10000000) {
                resEl.innerText = `O(N) ≈ ${n.toExponential(2)} ops (Fits < 1 sec)`;
            } else {
                const ops = Math.log2(n);
                resEl.innerText = `O(log N) ≈ ${Math.round(ops)} ops (Lightning fast)`;
            }
        }

        function factorial(n) {
            if (n <= 1) return 1;
            let val = 1;
            for (let i = 2; i <= n; i++) val *= i;
            return val;
        }
    </script>
</body>
</html>
