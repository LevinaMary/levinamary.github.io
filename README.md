<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Levina Mary Darbin | Portfolio Quest</title>
    
    <!-- Retro Pixel Font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">

    <style>
        /* Bright Sunny RPG Palette */
        :root {
            --sky-blue: #5cceff;
            --grass-green: #5cd670;
            --window-bg: #fffbf0; /* Warm cream page */
            --border-dark: #2c2c35;
            --text-dark: #2c2c35;
            --text-muted: #62627a;
            
            /* Fruit & Item Colors */
            --pixel-apple: #ff3b3b;
            --pixel-grape: #9b5de5;
            --pixel-orange: #f15bb5;
            --pixel-gold: #fee440;
            --pixel-leaf: #00f5d4;
        }

        body {
            background-color: var(--sky-blue);
            /* Pixel Art Grass Horizon at the bottom */
            background-image: linear-gradient(to top, var(--grass-green) 40px, transparent 40px);
            color: var(--text-dark);
            font-family: 'Press Start 2P', monospace;
            font-size: 11px;
            line-height: 1.8;
            margin: 0;
            padding: 40px 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            box-sizing: border-box;
            position: relative;
        }

        /* Pure CSS Pixel Clouds in the background */
        body::before {
            content: "";
            position: absolute;
            top: 10%;
            left: 10%;
            width: 120px;
            height: 30px;
            background: white;
            box-shadow: 30px 10px 0 0 white, -20px 10px 0 0 white, 10px -10px 0 0 white;
            opacity: 0.6;
            z-index: 0;
        }

        /* Main Cozy Game Menu UI Window */
        .game-container {
            width: 100%;
            max-width: 950px;
            background-color: var(--window-bg);
            border: 6px solid var(--border-dark);
            box-shadow: 12px 12px 0px rgba(0, 0, 0, 0.15);
            padding: 25px;
            z-index: 10;
            position: relative;
            border-radius: 4px;
        }

        /* Top Banner Header */
        .game-header {
            text-align: center;
            border-bottom: 6px double var(--border-dark);
            padding-bottom: 20px;
            margin-bottom: 30px;
            position: relative;
        }

        .game-header h1 {
            font-size: 20px;
            margin: 0 0 12px 0;
            color: #ff5964;
            text-shadow: 2px 2px 0px var(--pixel-gold);
            text-transform: uppercase;
        }

        .status-hud {
            font-size: 8px;
            background: #eef7fc;
            display: inline-block;
            padding: 8px 16px;
            border: 3px solid var(--border-dark);
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* Main Interactive Layout Grid */
        .menu-layout {
            display: flex;
            flex-direction: row;
            gap: 25px;
        }

        /* Sidebar Buttons */
        .tabs-sidebar {
            width: 34%;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .tab-btn {
            background-color: #ffeaa7;
            color: var(--text-dark);
            border: 4px solid var(--border-dark);
            padding: 12px 10px;
            font-family: 'Press Start 2P', monospace;
            font-size: 8px;
            text-align: left;
            cursor: pointer;
            box-shadow: 4px 4px 0px var(--border-dark);
            transition: all 0.1s ease;
        }

        .tab-btn:hover {
            background-color: #ffffcc;
            transform: translate(2px, 2px);
            box-shadow: 2px 2px 0px var(--border-dark);
        }

        /* Active Tab Accent (Selected Level) */
        .tab-btn.active {
            background-color: #ff7675;
            color: white;
            box-shadow: none;
            transform: translate(4px, 4px);
        }

        /* Monitor Display Box */
        .display-panel {
            width: 66%;
            background-color: #ffffff;
            border: 4px solid var(--border-dark);
            padding: 25px;
            min-height: 440px;
            box-sizing: border-box;
            box-shadow: inset 4px 4px 0px rgba(0,0,0,0.05);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        h2 {
            font-size: 11px;
            color: #0984e3;
            margin-top: 0;
            margin-bottom: 20px;
            text-transform: uppercase;
            border-bottom: 4px dashed #dfe6e9;
            padding-bottom: 10px;
        }

        p {
            color: var(--text-muted);
            font-size: 10px;
            line-height: 1.8;
        }

        /* Pixel Fruit Bullet Points Rules */
        ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        li {
            font-size: 10px;
            margin-bottom: 16px;
            position: relative;
            padding-left: 24px;
            color: var(--text-muted);
            line-height: 1.6;
        }

        /* Custom Pixel Icons built directly into list bullets */
        li::before {
            content: "🍒";
            position: absolute;
            left: 0;
            top: -2px;
            font-size: 12px;
        }

        .apple-list li::before { content: "🍎"; }
        .grape-list li::before { content: "🍇"; }
        .coin-list li::before { content: "🪙"; }
        .star-list li::before { content: "⭐"; }
        .banana-list li::before { content: "🍌"; }

        .highlight {
            color: var(--text-dark);
            font-weight: bold;
        }

        /* Grid box inside skills */
        .perks-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 12px;
            margin-top: 10px;
        }
        
        .perk-box {
            background: #f9f9ff;
            border: 3px solid var(--border-dark);
            padding: 10px;
            font-size: 9px;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            .menu-layout { flex-direction: column; }
            .tabs-sidebar, .display-panel { width: 100%; }
        }
    </style>
</head>
<body>

    <div class="game-container">
        <!-- Dashboard Header -->
        <div class="game-header">
            <h1>Levina Mary Darbin</h1>
            <div class="status-hud">
                📍 Passau, Bavaria | ✉️ darbin02@ads.uni-passau.de<br>
                📞 +49 1525 5833704 | 🎓 M.Sc. Econ & Business Student
            </div>
        </div>

        <div class="menu-layout">
            <!-- Left Side Interactive Item Row -->
            <nav class="tabs-sidebar">
                <button class="tab-btn active" onclick="openTab(event, 'about')">🍊 ABOUT ME</button>
                <button class="tab-btn" onclick="openTab(event, 'education')">🍎 EDUCATION</button>
                <button class="tab-btn" onclick="openTab(event, 'leadership')">🍌 LEADERSHIP</button>
                <button class="tab-btn" onclick="openTab(event, 'volunteering')">🍇 VOLUNTEERING</button>
                <button class="tab-btn" onclick="openTab(event, 'skills')">⭐ SKILLS</button>
                <button class="tab-btn" onclick="openTab(event, 'certs')">🪙 CERTIFICATES</button>
                <button class="tab-btn" onclick="openTab(event, 'honors')">🍒 HONORS & LANG</button>
            </nav>

            <!-- Right Side Dashboard Display Screen -->
            <main class="display-panel">
                
                <!-- ABOUT ME -->
                <div id="about" class="tab-content active">
                    <h2>🍊 Character Bio</h2>
                    <p>Master's student in International Economics and Business with strong analytical, organizational, and communication skills[span_0](start_span)[span_0](end_span).</p>
                    <p>Experienced in research, data analysis, and project coordination, with the unique ability to transform complex insights into actionable recommendations[span_1](start_span)[span_1](end_span).</p>
                </div>

                <!-- EDUCATION -->
                <div id="education" class="tab-content">
                    <h2>🍎 Education Quest</h2>
                    <ul class="apple-list">
                        <li><span class="highlight">Universität Passau (2025 - Current)</span><br>M.Sc. International Economics and Business[span_2](start_span)[span_2](end_span).</li>
                        <li><span class="highlight">CHRIST (Deemed to be) University (2021 - 2024)</span><br>B.A Psychology, Sociology, Economics. Final Grade: 8.97/10.0[span_3](start_span)[span_3](end_span).</li>
                    </ul>
                </div>

                <!-- LEADERSHIP / POSITIONS OF RESPONSIBILITY -->
                <div id="leadership" class="tab-content">
                    <h2>🍌 Positions of Responsibility</h2>
                    <ul class="banana-list">
                        <li><span class="highlight">Deanery Head (2022-2024)</span><br>Association of Christian Christites — Team leader for the School of Social Sciences; conducted student engagement events for minority welfare[span_4](start_span)[span_4](end_span).</li>
                        <li><span class="highlight">Promotions Head (2023-2024)</span><br>Potter and Clay Productions — Led the promotions team for a theatre group, creating posters, drafting emails, and discussing video scripts[span_5](start_span)[span_5](end_span).</li>
                    </ul>
                </div>

                <!-- VOLUNTEERING -->
                <div id="volunteering" class="tab-content">
                    <h2>🍇 Community Side Quests</h2>
                    <ul class="grape-list">
                        <li><span class="highlight">Vision Empower (2023)</span><br>Tactile Illustrator (Bangalore, India) — Created tactile STEM diagrams for the visually challenged and used Microsoft Azure services for transcription and editing[span_6](start_span)[span_6](end_span).</li>
                        <li><span class="highlight">St. Anne's Convent (2018)</span><br>English Tutor (Chinnathurai, India) — Taught spoken English to underprivileged children via role-plays, crafting, and personalized tests[span_7](start_span)[span_7](end_span).</li>
                    </ul>
                </div>

                <!-- SKILLS -->
                <div id="skills" class="tab-content">
                    <h2>⭐ Technical Skill Tree</h2>
                    <div class="perks-grid">
                        <div class="perk-box">
                            <span class="highlight">💻 Programming:</span><br>R, STATA, Python[span_8](start_span)[span_8](end_span)
                        </div>
                        <div class="perk-box">
                            <span class="highlight">📊 Applications & Analysis:</span><br>Dashboard creation, data collection, cleaning & analysis, market research, documentation, statistics, econometrics[span_9](start_span)[span_9](end_span)
                        </div>
                        <div class="perk-box">
                            <span class="highlight">🛠️ Platforms:</span><br>Microsoft Office, Google Workspace, Canva, Power BI[span_10](start_span)[span_10](end_span)
                        </div>
                    </div>
                </div>

                <!-- CERTIFICATIONS -->
                <div id="certs" class="tab-content">
                    <h2>🪙 Badge Inventory (Certifications)</h2>
                    <ul class="coin-list">
                        <li><span class="highlight">Programming Badges:</span> Regression in R (2026), Basics of STATA (2026), Python for Data Science, AI & Development (2025), Data Analytics Using R Programming (2023)[span_11](start_span)[span_11](end_span).</li>
                        <li><span class="highlight">Application Badges:</span> Computational Social Science Methods (2025), Google AI Essentials (2025), Excel/Cognos Dashboards (2025), Model Thinking (2025), Market Research & Consumer Behaviour (2025)[span_12](start_span)[span_12](end_span).</li>
                    </ul>
                </div>

                <!-- HONORS & LANGUAGES -->
                <div id="honors" class="tab-content">
                    <h2>🍒 Honors & Languages</h2>
                    <ul class="apple-list">
                        <li><span class="highlight">Nudge Impact Award (April 2026):</span> Awarded for a behavioural-science project applying nudging principles to improve decision-making and public outcomes[span_13](start_span)[span_13](end_span).</li>
                        <li><span class="highlight">Meritorious Scholarship (2023-2024):</span> Awarded for 2 years for academic performance and regular attendance[span_14](start_span)[span_14](end_span).</li>
                        <li><span class="highlight">Languages:</span> English (C2 - Proficient), German (B1 - Independent), Tamil (Native)[span_15](start_span)[span_15](end_span)[span_16](start_span)[span_16](end_span).</li>
                    </ul>
                </div>

            </main>
        </div>
    </div>

    <!-- Interface Controller Script -->
    <script>
        function openTab(evt, tabId) {
            const contents = document.getElementsByClassName("tab-content");
            for (let i = 0; i < contents.length; i++) {
                contents[i].classList.remove("active");
            }

            const buttons = document.getElementsByClassName("tab-btn");
            for (let i = 0; i < buttons.length; i++) {
                buttons[i].classList.remove("active");
            }

            document.getElementById(tabId).classList.add("active");
            evt.currentTarget.classList.add("active");
        }
    </script>
</body>
</html>
