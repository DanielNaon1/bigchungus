<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Big Chungus - The Story of a Popular Meme</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #4CAF50; /* Green */
            --secondary-color: #FFC107; /* Yellow */
            --background-color: #f0f2f5;
            --text-color: #333;
            --light-text-color: #f4f4f9;
        }

        body {
            font-family: 'Heebo', 'Arial', sans-serif;
            background-color: var(--background-color);
            margin: 0;
            padding: 0;
            color: var(--text-color);
            direction: ltr; /* Left-to-Right for English */
            line-height: 1.6;
            cursor: default; 
            overflow-x: hidden; 
        }

        header {
            background: linear-gradient(135deg, var(--primary-color), #8BC34A);
            color: white;
            padding: 40px 0;
            text-align: center;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
        }

        header h1 {
            font-size: 3.5rem;
            margin: 0;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        header h2 {
            font-size: 1.8rem;
            margin-top: 10px;
            color: var(--secondary-color);
            font-weight: 400;
        }

        .container {
            width: 90%;
            max-width: 900px;
            margin: 30px auto;
            padding: 20px;
        }

        #main-content-block {
            transition: opacity 0.3s ease;
        }

        .content {
            background-color: white;
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            margin-bottom: 30px; 
        }

        .content p {
            font-size: 1.1rem;
            margin-bottom: 20px;
        }
        
        .content a {
            color: var(--primary-color);
            font-weight: bold;
            text-decoration: none;
            border-bottom: 2px solid var(--primary-color);
            padding-bottom: 2px;
            transition: color 0.2s, border-bottom 0.2s;
        }

        .content a:hover {
            color: #43a047;
            border-bottom-color: #43a047;
        }

        .content p strong {
            color: var(--primary-color);
        }

        .button-container {
            text-align: center;
            margin: 30px 0;
        }

        .game-button {
            display: inline-block;
            padding: 15px 20px; 
            font-size: 1rem; 
            font-weight: bold;
            color: white;
            background-color: var(--primary-color);
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.2s;
            text-decoration: none;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            margin: 5px; 
        }

        .game-button:hover {
            background-color: #43a047;
            transform: translateY(-2px);
        }

        .quiz-intro, .game-intro {
            text-align: center;
            margin-top: 50px;
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
        }
        
        /* Navigation Button Styling */
        .navigation-buttons button {
            background-color: #607D8B;
            font-size: 1rem;
            padding: 10px 15px;
            margin: 5px;
        }
        .navigation-buttons button:hover {
            background-color: #546E7A;
        }
        
        /* Reset button specific style */
        .reset-button {
            background-color: #FF5722 !important; /* Orange-Red for Reset */
        }
        .reset-button:hover {
            background-color: #E64A19 !important;
        }

        #quiz-container {
            display: none;
            background-color: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            margin-top: 20px;
        }
        
        /* Quiz Styles */
        .question-group { margin-bottom: 30px; border-bottom: 1px solid #eee; padding-bottom: 20px; }
        .question { font-size: 1.2rem; font-weight: bold; margin-bottom: 15px; color: #555; }
        .options label { display: block; background-color: #f9f9f9; padding: 12px; margin-top: 10px; border: 1px solid #ddd; border-radius: 5px; cursor: pointer; transition: background-color 0.2s, transform 0.2s; }
        .options label:hover { background-color: #e9e9e9; transform: translateX(5px); }
        .options input[type="radio"] { margin-right: 10px; } 
        .check-button { display: block; margin: 15px auto 0 0;  padding: 8px 15px; background-color: var(--primary-color); color: white; border: none; border-radius: 5px; font-size: 1rem; cursor: pointer; transition: background-color 0.2s; }
        .check-button:hover { background-color: #43a047; }
        .feedback { margin-top: 10px; font-weight: bold; text-align: center; }
        .correct-feedback { color: var(--primary-color); }
        .incorrect-feedback { color: #F44336; }
        .correct { background-color: #e8f5e9; border: 1px solid var(--primary-color); }
        .incorrect { background-color: #ffebee; border: 1px solid #e57373; }
        .correct:hover, .incorrect:hover { transform: none; }

        /* --- Game Area Styles --- */
        #game-container-wrapper {
            margin-top: 20px;
            text-align: center;
            background-color: white; 
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            display: none;
        }
        
        #level-selection {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            padding: 20px 0;
        }
        
        #level-selection button {
            width: 70%;
            font-size: 1.5rem;
            padding: 20px;
        }

        #game-area-main {
            display: none; /* Only visible when a game is running */
        }
        
        #game-container {
            /* The White Rectangle */
            position: relative;
            width: 800px; 
            height: 500px;
            margin: 0 auto;
            background-color: white;
            border: 4px solid var(--primary-color);
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            overflow: hidden; 
            cursor: none; 
            user-select: none; 
            margin-bottom: 20px;
        }
        
        #chungus {
            position: absolute; 
            width: 120px;
            height: 120px;
            pointer-events: none; 
            transition: none; 
            transform-origin: center center;
            z-index: 999;
        }

        #game-messages {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 5rem;
            font-weight: bold;
            text-align: center;
            z-index: 1000;
            display: none;
            width: 90%;
        }
        
        /* Exit Game Button (Top Left) */
        #exit-game-button {
            position: absolute;
            top: 10px;
            left: 10px; 
            width: 30px;
            height: 30px;
            background-color: #F44336;
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            z-index: 1001;
            line-height: 1;
            padding: 0;
            font-size: 18px;
            display: none; 
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        }

        /* Reset Game Button (Top Right) - New Style and Position */
        #reset-game-in-container {
            position: absolute;
            top: 10px;
            right: 10px;
            padding: 8px 12px; 
            font-size: 0.9rem;
            z-index: 1001;
            display: none;
        }
        /* --- End Game Area Styles --- */

        .win-message { color: var(--primary-color); }
        .lose-message { color: #F44336; }

        .footer {
            background-color: var(--text-color);
            color: var(--light-text-color);
            padding: 20px;
            text-align: center;
            font-size: 0.9rem;
            margin-top: 50px;
            box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.1);
        }
        
        /* Utility to hide main buttons/intro */
        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>

<header>
    <h1>Big Chungus</h1>
    <h2>The Character That Entertains the Web</h2>
</header>

<div class="container">
    <div id="main-content-block">
        <div class="content">
            <p><strong>Big Chungus</strong> is an internet meme that became very popular in recent years, but its story begins much earlier, in 1941.</p>
            <p>The original character of "Big Chungus" is based on the figure of *Bugs Bunny* from the Looney Tunes animated short. In a scene in the film "Wabbit Twouble" from 1941, Bugs Bunny changes his form to an exaggeratedly large and obese state. In this scene, Bugs Bunny makes his famous laugh, and a plump and comical figure appears, associated with a lot of classic humor.</p>
            <p>The character's popularity soared, especially in 2018, after many versions of it began appearing in video games and online forums. The "Big Chungus" meme serves as a parody of Bugs Bunny, and besides laughter, it is often used with humorous captions.</p>
            <p>Its popularity stems precisely from its exaggeration: the image of Bugs Bunny looking so fat and unrealistic created the comic effect and surprised many viewers. The name "Big Chungus" became associated with various amusing versions where the character appeared in different situations or with humorous captions.</p>
            <p>Moreover, the appearance of "Big Chungus" did not remain confined to the world of memes. Over the years, the character has also appeared in video games such as *PlayStation All-Stars Battle Royale*, where the character could be seen participating in a fight among other characters. Furthermore, images of the character can be found in many media, from memes to musical creations.</p>
            
            <p>One of the most popular expressions of the meme culture surrounding Big Chungus is the <a href="https://youtu.be/cB4dYfFgaME?si=mLQemf5n2kX2b9PR" target="_blank">song</a> created in its inspiration. The song, based on a simple and catchy tune, repeats the words "Big Chungus, Big Chungus" over and over, and became a viral hit on social networks and video sharing platforms. It is an excellent example of the power of internet culture to take a simple visual element and turn it into a humorous and entertaining musical phenomenon.</p>

            <p>The strength of this meme lies not only in its humor but also in the concept of creative freedom that allows anyone to take a familiar character and create funny and surprising versions of it. The character has the ability to provoke laughter and quickly become part of digital and internet culture.</p>
        </div>
    </div> <p class="quiz-intro" id="main-nav-intro">Ready to test your knowledge or skill?</p>
    <div class="button-container" id="main-buttons">
        <button class="game-button" onclick="showQuiz()">Enter Quiz</button>
        <button class="game-button" onclick="showLevelSelection()">Enter Game</button>
    </div>
    
    <div id="game-container-wrapper">
        
        <div id="level-selection">
            <h2 style="color: var(--primary-color);">Choose a Difficulty Level</h2>
            <button class="game-button" onclick="startGame('EASY')">Easy (30 Sec - Final Accel.)</button>
            <button class="game-button" onclick="startGame('MEDIUM')" style="background-color: #43A047;">Medium (1 Min - Final Accel.)</button>
            <button class="game-button" onclick="startGame('HARD')" style="background-color: #FF9800;">Hard (1 Min - Constant Speed)</button>
            <button class="game-button" onclick="startGame('WC')" style="background-color: #FBC02D;">World Champion (2 Min - High Speed)</button>
            <button class="game-button" onclick="startGame('GOD')" style="background-color: #F44336;">God Mode (3 Min - Peak Speed)</button>
        </div>
        
        <div id="game-area-main">
            <div style="text-align: center; margin-bottom: 15px;">
                <p style="font-size: 1.2rem; font-weight: bold; color: #555;">Time Left: <span id="game-timer-display">00:00</span> | Score: <span id="game-score-display">0</span></p>
            </div>
            <div id="game-container">
                <button class="game-button reset-button" id="reset-game-in-container" onclick="resetCurrentGame()">Reset Game</button> 
                <button id="exit-game-button" onclick="quitGame()">X</button>
                <h2 style="text-align:center; color: var(--primary-color);">Game: Catch Me If You Can!</h2>
                <p style="text-align: center; color: var(--text-color); font-weight: bold;">Move the carrot (cursor) to dodge Big Chungus! (Stay inside the rectangle)</p>
                <img id="chungus" src="https://purepng.com/public/uploads/large/big-chungus-jkg.png">
                <div id="game-messages"></div>
            </div>
            
            <div class="navigation-buttons">
                <button class="game-button" onclick="showLevelSelection()">Return to Level Selection</button>
                <button class="game-button" onclick="showQuiz()">Go to Quiz</button>
            </div>
        </div>
    </div>
    
    <div id="quiz-container">
        <h2 style="text-align:center; color: var(--primary-color);">Quiz on Big Chungus</h2>
        <form id="quiz-form"></form>
        
        <div class="navigation-buttons">
            <button class="game-button reset-button" onclick="resetQuiz()">Reset Quiz</button> 
            <button class="game-button" onclick="showLevelSelection()">Go to Game</button>
            <button class="game-button" onclick="returnToMainButtons()">Back to Main Buttons</button>
        </div>
    </div>
</div>

<div class="footer">
    <p>Content creation about Big Chungus - The Captivating World of Memes!</p>
</div>

<script>
    // Quiz Data (English) - Not changed, keeping for completeness
    const quizData = [
        {
            question: "From which year does the original Big Chungus character first appear?",
            options: ["1950", "1941", "1980", "2005"],
            answer: "1941"
        },
        {
            question: "Which character is 'Big Chungus' based on?",
            options: ["Mickey Mouse", "Daffy Duck", "Bugs Bunny", "Yosemite Sam"],
            answer: "Bugs Bunny"
        },
        {
            question: "In which animated short did the character first appear?",
            options: ["'What's Up, Doc?'", "'Rabbit Fire'", "'Wabbit Twouble'", "'Duck Amuck'"],
            answer: "'Wabbit Twouble'"
        },
        {
            question: "What characterizes Bugs Bunny's appearance in that short?",
            options: ["He looks unusually thick and large", "He wears a costume", "He changes voices", "He performs magic tricks"],
            answer: "He looks unusually thick and large"
        },
        {
            question: "In which year did the 'Big Chungus' meme become particularly popular?",
            options: ["2010", "1999", "2018", "2022"],
            answer: "2018"
        },
        {
            question: "What is the main purpose of the 'Big Chungus' meme?",
            options: ["To be a serious character", "To serve as parody and humor", "To convey political messages", "To represent pets"],
            answer: "To serve as parody and humor"
        },
        {
            question: "In addition to a meme, in which other media did the character appear?",
            options: ["In books", "In magazines", "In video games", "In documentaries"],
            answer: "In video games"
        },
        {
            question: "What is the meaning of the word 'Chungus'?",
            options: ["It is a Japanese name", "It is a fake name", "A word meaning 'big fat'", "It has no meaning"],
            answer: "A word meaning 'big fat'"
        },
        {
            question: "One of the meme's popular expressions is a viral song. What is the song based on?",
            options: ["On the melody of a famous folk song", "On a simple, catchy tune that repeats the words 'Big Chungus'", "On a complex melody that became very popular", "On a famous melody by a famous band"],
            answer: "On a simple, catchy tune that repeats the words 'Big Chungus'"
        },
        {
            question: "What is the main power of the 'Big Chungus' meme?",
            options: ["It is catchy", "It is easy to draw", "It is realistic", "It evokes laughter and allows creative freedom"],
            answer: "It evokes laughter and allows creative freedom"
        }
    ];

    const quizContainer = document.getElementById('quiz-container');
    const gameWrapper = document.getElementById('game-container-wrapper');
    const levelSelection = document.getElementById('level-selection');
    const gameAreaMain = document.getElementById('game-area-main');
    const mainContentBlock = document.getElementById('main-content-block');
    
    // New: Main Navigation Elements
    const mainNavIntro = document.getElementById('main-nav-intro');
    const mainButtonsContainer = document.getElementById('main-buttons');

    // New Game/Score Elements
    const timerDisplay = document.getElementById('game-timer-display');
    const scoreDisplay = document.getElementById('game-score-display');
    const resetGameButtonInContainer = document.getElementById('reset-game-in-container'); // New: Reset button inside game container
    
    // Utility for time formatting - Not changed
    function formatTime(ms) {
        const totalSeconds = Math.floor(ms / 1000);
        const minutes = Math.floor(totalSeconds / 60);
        const seconds = totalSeconds % 60;
        return `${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;
    }

    function shuffleArray(array) {
        for (let i = array.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [array[i], array[j]] = [array[j], array[i]];
        }
        return array;
    }
    
    function resetView() {
        quizContainer.style.display = 'none';
        gameWrapper.style.display = 'none';
        gameAreaMain.style.display = 'none';
        levelSelection.style.display = 'none';
        document.body.style.cursor = 'default';
        endGame(null); 
        
        mainContentBlock.style.display = 'block';
        
        // Show Main Navigation Elements
        mainNavIntro.classList.remove('hidden');
        mainButtonsContainer.classList.remove('hidden');
    }

    // --- Navigation Functions - UPDATED ---
    function showLevelSelection() {
        resetView();
        gameWrapper.style.display = 'block';
        levelSelection.style.display = 'flex';
        mainContentBlock.style.display = 'none'; 
        
        // Hide Main Navigation Elements
        mainNavIntro.classList.add('hidden');
        mainButtonsContainer.classList.add('hidden');
        
        window.location.href = "#game-container-wrapper";
    }

    function showQuiz() {
        resetView();
        quizContainer.style.display = 'block';
        mainContentBlock.style.display = 'none'; 
        
        // Hide Main Navigation Elements
        mainNavIntro.classList.add('hidden');
        mainButtonsContainer.classList.add('hidden');
        
        window.location.href = "#quiz-container";
        quizContainer.querySelector('form').innerHTML = ''; 
        buildQuiz();
    }
    
    function returnToMainButtons() {
        resetView();
        mainContentBlock.style.display = 'block'; 
        
        // Show Main Navigation Elements
        mainNavIntro.classList.remove('hidden');
        mainButtonsContainer.classList.remove('hidden');
        
        window.location.href = "#main-nav-intro";
    }

    // --- Reset Functions ---
    function resetQuiz() {
        showQuiz(); 
    }

    function resetCurrentGame() {
        if (!currentSettings) {
             showLevelSelection();
             return;
        }
        startGame(currentSettings.name.toUpperCase().replace(/\s/g, ''));
    }

    // --- Quiz Logic - Not changed
    function buildQuiz() {
        quizData.forEach((item, index) => {
            const questionGroup = document.createElement('div');
            questionGroup.classList.add('question-group');
            questionGroup.id = `question-group-${index}`;

            const questionElement = document.createElement('div');
            questionElement.classList.add('question');
            questionElement.innerHTML = `<p>${index + 1}. ${item.question}</p>`;

            const optionsElement = document.createElement('div');
            optionsElement.classList.add('options');
            
            const shuffledOptions = shuffleArray([...item.options]);

            shuffledOptions.forEach(option => {
                optionsElement.innerHTML += `
                    <label>
                        <input type="radio" name="question${index}" value="${option}">
                        ${option}
                    </label>
                `;
            });
            
            const checkButton = document.createElement('button');
            checkButton.classList.add('check-button');
            checkButton.textContent = 'Check Answer';
            checkButton.onclick = (e) => { e.preventDefault(); checkAnswer(index, item.answer); }; 

            const feedbackElement = document.createElement('div');
            feedbackElement.classList.add('feedback');
            feedbackElement.id = `feedback-${index}`;

            questionGroup.appendChild(questionElement);
            questionGroup.appendChild(optionsElement);
            questionGroup.appendChild(checkButton);
            questionGroup.appendChild(feedbackElement);

            quizContainer.querySelector('form').appendChild(questionGroup);
        });
    }

    function checkAnswer(questionIndex, correctAnswer) {
        const selectedOption = document.querySelector(`input[name="question${questionIndex}"]:checked`);
        const feedbackElement = document.getElementById(`feedback-${questionIndex}`);
        const questionGroup = document.getElementById(`question-group-${questionIndex}`);
        const checkButton = questionGroup.querySelector('.check-button');

        if (!selectedOption) {
            feedbackElement.textContent = 'Please select an answer first.';
            feedbackElement.classList.remove('correct-feedback', 'incorrect-feedback');
            return;
        }

        const selectedLabel = selectedOption.closest('label');

        if (selectedOption.value === correctAnswer) {
            feedbackElement.textContent = 'Correct! That is the right answer.';
            feedbackElement.classList.remove('incorrect-feedback');
            feedbackElement.classList.add('correct-feedback');
            selectedLabel.classList.add('correct');
        } else {
            feedbackElement.textContent = `Oops, that is not the right answer. The correct answer is: ${correctAnswer}`;
            feedbackElement.classList.remove('correct-feedback');
            feedbackElement.classList.add('incorrect-feedback');
            selectedLabel.classList.add('incorrect');
            
            const correctLabel = document.querySelector(`input[name="question${questionIndex}"][value="${correctAnswer}"]`).closest('label');
            correctLabel.classList.add('correct');
        }
        
        const radioButtons = questionGroup.querySelectorAll('input[type="radio"]');
        radioButtons.forEach(radio => radio.disabled = true);
        checkButton.disabled = true;
        checkButton.style.opacity = 0.6;
        checkButton.style.cursor = "not-allowed";
    }

    // --- Game Logic ---
    const gameContainer = document.getElementById('game-container'); 
    const chungusElement = document.getElementById('chungus');
    const messages = document.getElementById('game-messages');
    const exitButton = document.getElementById('exit-game-button');

    let chungus = { x: 0, y: 0, size: 120 };
    let carrot = { x: 0, y: 0, size: 25 };
    let gameLoop, gameTimerTimeout, gameDurationInterval, startTime;
    let gameActive = false;
    let currentSettings = null; 
    let score = 0; 
    
    // Difficulty Settings - Not changed
    const DIFFICULTY_SETTINGS = {
        EASY: { name: 'Easy', duration: 30000, baseSpeed: 3, rampUpDuration: 10000, peakSpeed: 7 }, 
        MEDIUM: { name: 'Medium', duration: 60000, baseSpeed: 3, rampUpDuration: 30000, peakSpeed: 7 }, 
        HARD: { name: 'Hard', duration: 60000, baseSpeed: 6, rampUpDuration: 0, peakSpeed: 6 }, 
        WC: { name: 'World Champion', duration: 120000, baseSpeed: 7, rampUpDuration: 0, peakSpeed: 7 }, 
        GOD: { name: 'God Mode', duration: 180000, baseSpeed: 9, rampUpDuration: 0, peakSpeed: 9 } 
    };

    const carrotCursorUrl = 'url("https://www.offidocs.com/images/carrotvegetablesfoodfreevectorgraphiconpixabay.jpg") 12.5 12.5, auto';

    function startGame(level) {
        resetView();
        
        currentSettings = DIFFICULTY_SETTINGS[level];
        gameWrapper.style.display = 'block';
        gameAreaMain.style.display = 'block';
        exitButton.style.display = 'block';
        resetGameButtonInContainer.style.display = 'block'; // Show Reset button
        
        document.body.style.cursor = 'none';
        gameContainer.style.cursor = carrotCursorUrl; 
        mainContentBlock.style.display = 'none'; 
        
        mainNavIntro.classList.add('hidden'); // Hide Main Navigation Elements
        mainButtonsContainer.classList.add('hidden'); // Hide Main Navigation Elements

        window.location.href = "#game-container-wrapper";
        resetGame();
    }
    
    function resetGame() {
        if (!currentSettings) return;

        if (gameLoop) clearInterval(gameLoop);
        if (gameTimerTimeout) clearTimeout(gameTimerTimeout);
        if (gameDurationInterval) clearInterval(gameDurationInterval);
        
        score = 0; 
        scoreDisplay.textContent = score;

        const areaWidth = gameContainer.clientWidth;
        const areaHeight = gameContainer.clientHeight;

        chungus.x = areaWidth / 2;
        chungus.y = areaHeight / 2;
        chungusElement.style.left = `${chungus.x - (chungus.size / 2)}px`; 
        chungusElement.style.top = `${chungus.y - (chungus.size / 2)}px`;
        
        messages.textContent = '';
        messages.classList.remove('win-message', 'lose-message');
        messages.style.display = 'none';
        gameActive = true;
        startTime = Date.now(); 
        
        gameDurationInterval = setInterval(updateTimeAndScore, 100); 

        gameLoop = setInterval(updateGame, 1000 / 60); 
        gameTimerTimeout = setTimeout(() => {
            if (gameActive) endGame(true); 
        }, currentSettings.duration); 
    }

    function updateTimeAndScore() {
        if (!gameActive) return;

        const timeElapsed = Date.now() - startTime;
        const timeLeft = currentSettings.duration - timeElapsed;

        if (timeLeft > 0) {
            timerDisplay.textContent = formatTime(timeLeft);
        } else {
            timerDisplay.textContent = formatTime(0);
        }

        score += 1; 
        scoreDisplay.textContent = score;
    }

    function updateGame() {
        if (!gameActive) return;

        let speed = currentSettings.baseSpeed;
        if (currentSettings.rampUpDuration > 0) {
            const timeElapsed = Date.now() - startTime;
            const timeLeft = currentSettings.duration - timeElapsed;
            
            if (timeLeft <= currentSettings.rampUpDuration) {
                const rampUpTimeLeft = timeLeft;
                const rampUpRatio = 1 - (rampUpTimeLeft / currentSettings.rampUpDuration);
                speed = currentSettings.baseSpeed + (rampUpRatio * (currentSettings.peakSpeed - currentSettings.baseSpeed));
            }
        } else {
            speed = currentSettings.baseSpeed;
        }
        
        const dx = carrot.x - chungus.x;
        const dy = carrot.y - chungus.y;
        const distance = Math.sqrt(dx * dx + dy * dy);
        
        if (distance > 1) {
            chungus.x += (dx / distance) * speed;
            chungus.y += (dy / distance) * speed;
        }

        const chungusHalfSize = chungus.size / 2;
        const minChungusX = chungusHalfSize;
        const maxChungusX = gameContainer.clientWidth - chungusHalfSize;
        const minChungusY = chungusHalfSize;
        const maxChungusY = gameContainer.clientHeight - chungusHalfSize;

        chungus.x = Math.max(minChungusX, Math.min(maxChungusX, chungus.x));
        chungus.y = Math.max(minChungusY, Math.min(maxChungusY, chungus.y));

        chungusElement.style.left = `${chungus.x - chungusHalfSize}px`;
        chungusElement.style.top = `${chungus.y - chungusHalfSize}px`;

        if (distance < (chungus.size / 2) + (carrot.size / 2)) {
            endGame(false); 
        }
    }

    function endGame(won) {
        if (!gameActive && won !== null) return; 
        gameActive = false;
        clearInterval(gameLoop);
        clearTimeout(gameTimerTimeout);
        clearInterval(gameDurationInterval); 
        
        messages.style.display = 'block';
        if (won === true) {
            messages.textContent = `You Won! ${currentSettings.name} (Score: ${score})`;
            messages.classList.add('win-message');
        } else if (won === false) {
            messages.textContent = `You Lose! (Score: ${score})`; 
            messages.classList.add('lose-message');
        } else {
            messages.textContent = "Game Stopped.";
            messages.classList.remove('win-message', 'lose-message');
        }
        
        document.body.style.cursor = 'default';
        gameContainer.style.cursor = 'default';
        exitButton.style.display = 'none';
        resetGameButtonInContainer.style.display = 'none'; // Hide Reset button on end/quit
    }
    
    function quitGame() {
        if (!gameActive) return;
        endGame(null); 
        messages.style.display = 'block';
        messages.textContent = "Game stopped by the user.";
        messages.classList.remove('win-message', 'lose-message');
    }
    
    // --- Mouse Movement and Boundary Check - Not changed
    document.addEventListener('mousemove', (e) => {
        if (!gameActive) return;
        
        const bounds = gameContainer.getBoundingClientRect();
        
        if (e.clientX < bounds.left || e.clientX > bounds.right || e.clientY < bounds.top || e.clientY > bounds.bottom) {
            endGame(false); 
            messages.textContent = "You Lose! Mouse left the playing area.";
            return; 
        }

        let newX = e.clientX - bounds.left;
        let newY = e.clientY - bounds.top;

        carrot.x = Math.max(0, Math.min(bounds.width, newX));
        carrot.y = Math.max(0, Math.min(bounds.height, newY));
    });
    
    // Set initial view to the main navigation buttons
    document.addEventListener('DOMContentLoaded', returnToMainButtons);

</script>

</body>
</html>
