<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>scienceluke // ELECTRICAL ROCKETRY</title>
    <style>
        :root {
            --bg-dark: #0b0f17;
            --panel-bg: #121824;
            --panel-border: #1f293d;
            --neon-blue: #00f0ff;
            --neon-green: #39ff14;
            --neon-orange: #ffaa00;
            --text-main: #e2e8f0;
            --text-muted: #64748b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Courier New', Courier, monospace;
            background-color: var(--bg-dark);
            color: var(--text-main);
            overflow-x: hidden;
            background-image: 
                radial-gradient(rgba(0, 240, 255, 0.05) 1px, transparent 0),
                radial-gradient(rgba(57, 255, 20, 0.03) 1px, transparent 0);
            background-size: 40px 40px;
            background-position: 0 0, 20px 20px;
        }

        /* Mission Control Top Bar */
        header {
            background-color: rgba(18, 24, 36, 0.95);
            border-bottom: 2px solid var(--neon-blue);
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(10px);
            box-shadow: 0 5px 20px rgba(0, 240, 255, 0.15);
        }

        .sys-title {
            font-size: 20px;
            font-weight: bold;
            color: var(--neon-blue);
            text-shadow: 0 0 8px rgba(0, 240, 255, 0.5);
            letter-spacing: 2px;
        }

        .nav-links a {
            color: var(--text-main);
            text-decoration: none;
            margin-left: 20px;
            font-size: 14px;
            text-transform: uppercase;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--neon-blue);
            text-shadow: 0 0 5px var(--neon-blue);
        }

        /* Main Dashboard Grid Layout */
        .dashboard {
            max-width: 1400px;
            margin: 30px auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 1fr 3fr;
            gap: 25px;
        }

        @media (max-width: 900px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
        }

        /* Universal Panel Styling */
        .panel {
            background-color: var(--panel-bg);
            border: 1px solid var(--panel-border);
            border-radius: 8px;
            padding: 25px;
            position: relative;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .panel::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 10px;
            height: 10px;
            border-top: 2px solid var(--neon-blue);
            border-left: 2px solid var(--neon-blue);
        }

        .panel-title {
            font-size: 16px;
            color: var(--neon-blue);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 20px;
            border-bottom: 1px dashed var(--panel-border);
            padding-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* Left Column: Profile Card */
        .profile-card {
            text-align: center;
        }

        .logo-container {
            width: 160px;
            height: 160px;
            margin: 0 auto 20px auto;
            border-radius: 50%;
            border: 2px dashed var(--neon-blue);
            padding: 8px;
            animation: spin 20s linear infinite;
        }

        @keyframes spin { 100% { transform: rotate(360deg); } }

        .logo-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            transform: rotate(-12deg); /* Counteracts a bit of the loop frame rotation visually */
        }

        .profile-name {
            font-size: 24px;
            color: #fff;
            letter-spacing: 1px;
        }

        .profile-tag {
            color: var(--neon-orange);
            font-size: 13px;
            margin-top: 5px;
            margin-bottom: 25px;
            font-weight: bold;
        }

        .telemetry-item {
            display: flex;
            justify-content: space-between;
            font-size: 13px;
            margin-bottom: 12px;
            padding: 6px;
            background: rgba(255,255,255,0.02);
            border-left: 2px solid var(--panel-border);
        }

        .telemetry-item span:first-child {
            color: var(--text-muted);
        }

        .status-indicator {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            color: var(--neon-green);
            font-weight: bold;
            font-size: 14px;
            margin-top: 15px;
        }

        .pulse-dot {
            width: 8px;
            height: 8px;
            background-color: var(--neon-green);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--neon-green);
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(0.9); opacity: 0.6; }
            50% { transform: scale(1.2); opacity: 1; box-shadow: 0 0 15px var(--neon-green); }
            100% { transform: scale(0.9); opacity: 0.6; }
        }

        /* Right Column: Projects & Systems Display */
        .display-area {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        /* Mission Log Feed / Intro */
        .terminal-intro {
            background-color: #060911;
            font-size: 14px;
            line-height: 1.6;
            border-left: 3px solid var(--neon-blue);
        }

        .terminal-text {
            color: var(--neon-green);
        }

        /* Project Section Layout */
        .projects-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        @media (max-width: 1100px) {
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }

        .project-card {
            background: rgba(255,255,255,0.01);
            border: 1px solid var(--panel-border);
            border-radius: 6px;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .project-card:hover {
            border-color: var(--neon-blue);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 240, 255, 0.05);
        }

        .project-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }

        .project-id {
            font-size: 11px;
            color: var(--neon-orange);
            background: rgba(255, 170, 0, 0.1);
            padding: 2px 6px;
            border-radius: 3px;
        }

        .project-title {
            font-size: 18px;
            color: #fff;
            margin-bottom: 10px;
        }

        .project-desc {
            font-size: 14px;
            color: var(--text-muted);
            line-height: 1.5;
            margin-bottom: 15px;
        }

        /* Progress / Launch Stats Bar */
        .stat-bar-container {
            background: #000;
            height: 6px;
            border-radius: 3px;
            overflow: hidden;
            margin-top: 10px;
        }

        .stat-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--neon-blue), var(--neon-green));
        }

        .stat-labels {
            display: flex;
            justify-content: space-between;
            font-size: 11px;
            color: var(--text-muted);
            margin-top: 4px;
        }

        /* Footer Console info */
        footer {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-muted);
            font-size: 12px;
            border-top: 1px dashed var(--panel-border);
            margin-top: 50px;
        }
    </style>
</head>
<body>

    <!-- MISSION INTERFACE HEADER -->
    <header>
        <div class="sys-title">SL_AVIONICS // MC: ONLINE</div>
        <div class="nav-links">
            <a href="#overview">Overview</a>
            <a href="#projects">Projects</a>
            <a href="#telemetry">Telemetry</a>
        </div>
    </header>

    <div class="dashboard">
        
        <!-- SIDEBAR PANEL: IDENTITY & REAL-TIME STATS -->
        <aside class="panel profile-card" id="overview">
            <div class="panel-title"><span>❖</span> System Operator</div>
            
            <div class="logo-container">
                <!-- Points to your uploaded logo.png -->
                <img src="logo.png" alt="ScienceLuke Rocketry Logo" onerror="this.src='https://unsplash.com'">
            </div>

            <h1 class="profile-name">scienceluke</h1>
            <div class="profile-tag">AEROSPACE ELECTRICAL ENGINEER</div>

            <div class="telemetry-item">
                <span>SECTOR:</span>
                <span>Electrical Rocketry</span>
            </div>
            <div class="telemetry-item">
                <span>SUB-SYS:</span>
                <span>Avionics & Flight Code</span>
            </div>
            <div class="telemetry-item">
                <span>LOC:</span>
                <span>Ground Control</span>
            </div>
            <div class="telemetry-item">
                <span>BUILD ENGINE:</span>
