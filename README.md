<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AVS | Projects Portfolio</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: #ffffff;
            color: #111111;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
            padding-top: 80px; /* Prevents header from covering content */
        }

        /* Clean White Header Strip */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 70px;
            background-color: #ffffff;
            border-bottom: 1px solid #eaeaea;
            display: flex;
            align-items: center;
            padding: 0 40px;
            z-index: 1000;
        }

        .logo-link {
            display: flex;
            align-items: center;
            height: 100%;
            text-decoration: none;
        }

        .logo-img {
            height: 40px; /* Adjust scale of your AVS logo */
            width: auto;
            object-fit: contain;
        }

        /* Main Project Grid Container */
        main {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        .grid-heading {
            font-size: 28px;
            font-weight: 600;
            margin-bottom: 30px;
            letter-spacing: -0.5px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 30px;
        }

        /* Professional Project Card Styles */
        .project-card {
            background: #ffffff;
            border: 1px solid #e5e5e5;
            border-radius: 8px;
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .project-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            border-color: #111111;
        }

        .image-placeholder {
            width: 100%;
            height: 200px;
            background-color: #f7f7f7;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #888888;
            font-size: 14px;
            border-bottom: 1px solid #e5e5e5;
            overflow: hidden;
        }

        .image-placeholder img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .card-content {
            padding: 20px;
        }

        .card-title {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .card-desc {
            font-size: 14px;
            color: #666666;
            line-height: 1.5;
        }

        /* Fullscreen Project Page View (Modal Overlay) */
        .project-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #ffffff;
            z-index: 2000;
            display: none;
            overflow-y: auto;
            padding: 60px 20px;
        }

        .modal-container {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }

        .close-btn {
            position: absolute;
            top: -20px;
            right: 0;
            background: none;
            border: none;
            font-size: 28px;
            cursor: pointer;
            color: #111111;
        }

        .modal-hero-img {
            width: 100%;
            height: 400px;
            background-color: #f7f7f7;
            border-radius: 8px;
            margin-bottom: 30px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #888888;
        }

        .modal-hero-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .modal-title {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 15px;
            letter-spacing: -1px;
        }

        .modal-body {
            font-size: 16px;
            color: #333333;
            line-height: 1.8;
        }
    </style>
</head>
<body>

    <!-- STICKY HEADER -->
    <header>
        <a href="#" class="logo-link">
            <!-- Automatically loads your AVS logo file -->
            <img src="logo.png" alt="AVS Logo" class="logo-img" onerror="this.style.display='none'; this.after('AVS LOGO PLACEHOLDER')">
        </a>
    </header>

    <!-- MAIN PORTFOLIO STREAM -->
    <main>
        <h2 class="grid-heading">Project Index</h2>
        <div class="projects-grid">

            <!-- PROJECT 1 -->
            <div class="project-card" onclick="openProject(1)">
                <div class="image-placeholder">
                    <img src="project1.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p1-title">Project 01 Title</div>
                    <div class="card-desc" id="p1-desc">Click here to write a short overview statement about your first project system setup.</div>
                </div>
            </div>

            <!-- PROJECT 2 -->
            <div class="project-card" onclick="openProject(2)">
                <div class="image-placeholder">
                    <img src="project2.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p2-title">Project 02 Title</div>
                    <div class="card-desc" id="p2-desc">Click here to write a short overview statement about your second project system setup.</div>
                </div>
            </div>

            <!-- PROJECT 3 -->
            <div class="project-card" onclick="openProject(3)">
                <div class="image-placeholder">
                    <img src="project3.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p3-title">Project 03 Title</div>
                    <div class="card-desc" id="p3-desc">Click here to write a short overview statement about your third project system setup.</div>
                </div>
            </div>

            <!-- PROJECT 4 -->
            <div class="project-card" onclick="openProject(4)">
                <div class="image-placeholder">
                    <img src="project4.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p4-title">Project 04 Title</div>
                    <div class="card-desc" id="p4-desc">Brief summary narrative description text goes right here.</div>
                </div>
            </div>

            <!-- PROJECT 5 -->
            <div class="project-card" onclick="openProject(5)">
                <div class="image-placeholder">
                    <img src="project5.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p5-title">Project 05 Title</div>
                    <div class="card-desc" id="p5-desc">Brief summary narrative description text goes right here.</div>
                </div>
            </div>

            <!-- PROJECT 6 -->
            <div class="project-card" onclick="openProject(6)">
                <div class="image-placeholder">
                    <img src="project6.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p6-title">Project 06 Title</div>
                    <div class="card-desc" id="p6-desc">Brief summary narrative description text goes right here.</div>
                </div>
            </div>

            <!-- PROJECT 7 -->
            <div class="project-card" onclick="openProject(7)">
                <div class="image-placeholder">
                    <img src="project7.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p7-title">Project 07 Title</div>
                    <div class="card-desc" id="p7-desc">Brief summary narrative description text goes right here.</div>
                </div>
            </div>

            <!-- PROJECT 8 -->
            <div class="project-card" onclick="openProject(8)">
                <div class="image-placeholder">
                    <img src="project8.jpg" alt="" onerror="this.style.display='none';">
                    <span>[ Click to Upload Image ]</span>
                </div>
                <div class="card-content">
                    <div class="card-title" id="p8-title">Project 08 Title</div>
                    <div class="card-desc" id="p8-desc">Brief summary narrative description text goes right here.</div>
                </div>
            </div>

            <!-- PROJECT 9 -->
            <div class="project-card" onclick="openProject(9)">
