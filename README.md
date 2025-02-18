# happybirthday
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Chandrika</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
    <style>
        body {
            background-color: black;
            color: white;
            font-family: Arial, sans-serif;
            margin: 0;
            overflow: hidden;
            text-align: center;
        }
        .intro {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-color: black;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            animation: fadeOut 3s forwards 3s;
            flex-direction: column;
        }
        .birthday-text {
            font-size: 50px;
            font-weight: bold;
            color: lavender;
            opacity: 0;
            animation: fadeIn 1.5s ease-in-out forwards;
        }
        .main-content {
            display: none;
            animation: fadeIn 1s forwards;
        }
        .profiles {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 50px;
            align-items: center;
        }
        /* Profile Styling */
        .profile-container {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .profile {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background-color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 50px;
            cursor: pointer;
            border: 3px solid white;
            overflow: hidden;
            position: relative;
        }
        .profile img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
        }
        .profile-name {
            font-size: 18px;
            font-weight: bold;
            text-align: center;
            margin-top: 10px; /* Moves name outside the circle */
        }
        .add-user {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background-color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 60px;
            cursor: pointer;
            border: 3px solid white;
            flex-direction: column;
            overflow: hidden;
        }
        .episodes {
            display: none;
            margin-top: 20px;
        }
        .episode {
            cursor: pointer;
            padding: 10px;
            border: 1px solid white;
            display: inline-block;
            margin: 5px;
        }
        .video-player {
            display: none;
            margin-top: 20px;
        }
        .message {
            display: none;
            margin-top: 20px;
            font-size: 20px;
            color: red;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }
        @keyframes fadeOut {
            0% { opacity: 1; }
            100% { opacity: 0; visibility: hidden; }
        }
    </style>
</head>
<body>
    <div class="intro">
        <audio id="netflix-sound" src="https://assets.mixkit.co/active_storage/sfx/1397/1397-preview.mp3"></audio>
        <div class="birthday-text">Happy Birthday Chandrika</div>
    </div>

    <div class="main-content">
        <h1>Who is Watching?</h1>
        <div class="profiles">
            <!-- Profile Container (Image + Name) -->
            <div class="profile-container">
                <div class="profile" onclick="showEpisodes()">
                    <img src="C:\Users\lakshmi prasanna\Downloads\WhatsApp Image 2025-02-15 at 21.06.25.jpeg" alt="Profile Photo">
                </div>
                <div class="profile-name">Chandrika</div>
            </div>

            <!-- Add User Button with '+' Symbol -->
            <div class="profile-container">
                <div class="add-user" onclick="showMessage()">+</div>
                <div class="profile-name">Add Profile</div>
            </div>
        </div>

        <!-- Message for unauthorized user -->
        <div class="message" id="message">You can't add. Only Chandrika has access to watch it.</div>

        <div class="episodes">
            <h2>Select an Episode</h2>
            <div class="episode" onclick="playVideo('C:/Users/lakshmi prasanna/Downloads/WhatsApp Video 2025-02-14 at 18.43.09.mp4')">Tanu Nenu</div>
            <div class="episode" onclick="playVideo('C:/Users/lakshmi prasanna/Downloads/sakhi.mp4')">laila</div>
            <div class="episode" onclick="playVideo('C:/Users/lakshmi prasanna/Downloads/WhatsApp Video 2025-02-18 at 22.39.09.mp4')">jigra</div>
<div class="episode" onclick="playVideo('C:\Users\lakshmi prasanna\Downloads\stuck together.mp4')">stuck with me</div>
<div class="episode" onclick="playVideo('C:\Users\lakshmi prasanna\Downloads\comfort.mp4')">comfort</div>
<div class="episode" onclick="playVideo('C:\Users\lakshmi prasanna\Downloads\uyire.mp4')">uyire</div>

<div class="episode" onclick="playVideo('C:\Users\lakshmi prasanna\Downloads\uyire.mp4')">you and me</div>



        </div>

        <div class="video-player">
            <video id="video" controls width="600">
                <source id="video-source" src="" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>

    <script>
        window.onload = function() {
            document.getElementById("netflix-sound").play();
            setTimeout(() => {
                document.querySelector(".intro").style.display = "none";
                document.querySelector(".main-content").style.display = "block";
            }, 5000);
        };

        function showEpisodes() {
            document.querySelector(".episodes").style.display = "block";
        }

        function playVideo(videoSrc) {
            document.getElementById("video-source").src = videoSrc;
            document.getElementById("video").load();
            document.querySelector(".video-player").style.display = "block";
        }

        function showMessage() {
            document.getElementById("message").style.display = "block";
            setTimeout(() => {
                document.getElementById("message").style.display = "none";
            }, 3000); // Message disappears after 3 seconds
        }
    </script>
</body>
</html>
