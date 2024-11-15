# MRDL-CREATIVE-WEBSITE
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to MRDL Creative Space</title>
    <style>
        /* General Styles */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom right, #ff9a9e, #fad0c4, #fbc2eb, #a18cd1, #8fd3f4);
            color: #fff;
            text-align: center;
            overflow-x: hidden;
        }

        /* Header Section */
        header {
            padding: 20px;
            background: linear-gradient(to right, #ff758c, #ff7eb3, #ff919a, #ffc371);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            color: #fff;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        header h1 {
            margin: 0;
            font-size: 3em;
            font-weight: bold;
            letter-spacing: 3px;
            animation: glow 3s infinite alternate;
        }

        header p {
            margin: 10px 0;
            font-size: 1.2em;
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 10px #ff758c, 0 0 20px #ff7eb3, 0 0 30px #ffc371;
            }
            to {
                text-shadow: 0 0 20px #ffc371, 0 0 30px #ff758c, 0 0 40px #ff919a;
            }
        }

        /* Date-Time */
        #datetime {
            font-size: 1.5em;
            margin: 15px 0;
            background: linear-gradient(to right, #a18cd1, #fbc2eb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: bold;
        }

        /* Button Styles */
        button {
            background: linear-gradient(to left, #fbc2eb, #ff758c, #ff7eb3);
            color: white;
            border: none;
            padding: 15px 40px;
            margin: 20px 0;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            border-radius: 30px;
            transition: all 0.4s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        button:hover {
            background: linear-gradient(to right, #ff919a, #ffc371, #fad0c4);
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
        }

        /* Inspirational Message */
        #output {
            font-size: 1.8em;
            margin-top: 20px;
            color: #fff5ba;
            animation: fadeIn 1s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        /* Social Links */
        .social-links {
            margin: 30px auto;
        }

        .social-links a {
            display: inline-block;
            margin: 0 15px;
            padding: 10px 20px;
            border-radius: 30px;
            background: linear-gradient(to left, #ff7eb3, #ff758c, #fad0c4);
            text-decoration: none;
            font-size: 1.1em;
            font-weight: bold;
            color: white;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
        }

        .social-links a:hover {
            transform: scale(1.1);
            background: linear-gradient(to right, #fad0c4, #ff758c, #ffc371);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
        }

        .social-links a img {
            width: 25px;
            height: 25px;
            vertical-align: middle;
            margin-right: 8px;
        }

        /* Footer */
        footer {
            margin-top: 40px;
            padding: 20px;
            background: linear-gradient(to right, #6a11cb, #2575fc, #a18cd1);
            color: #fff;
            font-size: 1em;
            font-weight: 500;
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header>
        <h1>Welcome to MRDL Creative Space</h1>
        <p>Where storytelling meets creativity.</p>
    </header>

    <!-- Dynamic Date-Time -->
    <div id="datetime"></div>

    <!-- Inspirational Button -->
    <p>Click to Get Inspired!</p>
    <button id="magicButton">Get Inspired</button>
    <div id="output"></div>

    <!-- Music Controls -->
    <div class="music-controls">
        <button id="playPauseButton">Pause Music</button>
    </div>

    <!-- Social Links -->
    <div class="social-links">
        <h2>Connect with me</h2>
        <a href="https://www.youtube.com/@Mirudula13_11Jiccky_2" target="_blank">
            <img src="https://upload.wikimedia.org/wikipedia/commons/4/42/YouTube_icon_%282013-2017%29.png" alt="YouTube">
            YouTube
        </a>
        <a href="https://www.instagram.com/mrdl_officials?igsh=eGFtZGs3NmkwMDFl" target="_blank">
            <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
            Instagram
        </a>
        <a href="https://mrdlquotes.wordpress.com/english-essence/" target="_blank">
            <img src="https://wordpress.org/files/2023/02/simplified.png" alt="WordPress">
            Quotes Page
        </a>
    </div>

    <!-- Footer -->
    <footer>
        &copy; <span id="currentYear"></span> MRDL Creative Space. All Rights Reserved.
    </footer>

    <!-- JavaScript -->
    <script>
        // Dynamic Year
        const currentYear = new Date().getFullYear();
        document.getElementById('currentYear').textContent = currentYear;

        // Dynamic Date-Time
        function updateDateTime() {
            const now = new Date();
            const datetime = document.getElementById('datetime');
            const options = { 
                weekday: 'long', year: 'numeric', 
                month: 'long', day: 'numeric', 
                hour: '2-digit', minute: '2-digit', second: '2-digit' 
            };
            datetime.textContent = now.toLocaleDateString('en-US', options);
        }
        setInterval(updateDateTime, 1000);

        // Inspirational Quote Generator
        document.getElementById('magicButton').addEventListener('click', function() {
            const messages = [
                "“Friends are the family we choose.” — Jennifer Aniston",
                "“My purpose: to lift your spirit and to motivate you.” — Mavis Staples",
		"“Kindness is one thing you can’t give away. It always comes back.” — George Skolsky",
                "“Great things happen to those who don't stop believing,trying, learning, and being grateful.” ― Roy T. Bennett",
		"“Try to be a rainbow in someone else’s cloud.” — Maya Angelou",
		"“Fight for the things that you care about, but do it in a way that will lead others to join you.” —Ruth Bader Ginsburg",
		"“Nothing is impossible, the word itself says ‘I’m possible.’” — Audrey Hepburn ",
		"“Each day comes bearing its gifts. Untie the ribbon.” — Ann Ruth Schabacker",
		"“If you don’t like the road you’re walking, start paving another one.” — Dolly Parton",
                "“A dead end is just a good place to turn around.” — Naomi Judd",
                "“In every day, there are 1,440 minutes. That means we have 1,440 daily opportunities to make a positive impact.” — Les Brown"
            ];
            const outputDiv = document.getElementById('output');
            const randomMessage = messages[Math.floor(Math.random() * messages.length)];
            outputDiv.textContent = randomMessage;
        });

        // Background Music
        const bgMusic = new Audio('https://www.bensound.com/bensound-music/bensound-sunny.mp3');
        bgMusic.loop = true;
        bgMusic.volume = 0.5; // Adjust volume level
        bgMusic.play();

        // Play/Pause Music
        const playPauseButton = document.getElementById('playPauseButton');
        let isPlaying = true;

        playPauseButton.addEventListener('click', () => {
            if (isPlaying) {
                bgMusic.pause();
                playPauseButton.textContent = 'Play Music';
            } else {
                bgMusic.play();
                playPauseButton.textContent = 'Pause Music';
            }
            isPlaying = !isPlaying;
        });
    </script>
</body>
</html>
