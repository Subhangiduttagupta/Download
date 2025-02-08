<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will you be my Valentine?</title>
    <style>
        body {
            text-align: center;
            background-color: #ffe6e6;
            font-family: 'Arial', sans-serif;
        }
        .container {
            margin-top: 50px;
        }
        h1 {
            color: #ff4d4d;
            font-size: 36px;
        }
        .gif {
            width: 250px;
            height: auto;
            margin-bottom: 20px;
        }
        .btn {
            font-size: 20px;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            margin: 10px;
            transition: 0.3s;
            border-radius: 10px;
        }
        .yes-btn {
            background-color: #ff4d4d;
            color: white;
        }
        .no-btn {
            background-color: #fff;
            color: #ff4d4d;
            border: 2px solid #ff4d4d;
        }
        .hidden {
            display: none;
            font-size: 28px;
            color: #ff4d4d;
            font-weight: bold;
            margin-top: 20px;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Will you be my Valentine? ❤️</h1>
    <!-- Updated GIF Path -->
    <img src="bunnies.gif" class="gif" alt="Two Bunnies GIF">
    <br>
    
    <!-- Buttons -->
    <button class="btn yes-btn" id="yes" onclick="showCongrats()">Yes</button>
    <button class="btn no-btn" id="no" onclick="changeText()">No</button>

    <!-- Hidden Congratulations Message -->
    <p id="congrats" class="hidden">🎉 Yay! You made my day! Happy Valentine's Day. I LOVE YOU! 💖</p>
</div>

<script>
    let noTexts = ["Are you sure? 🥺", "Really? 💔", "Think again! 😢", "Please? 🥰", "Don't break my heart 💞"];
    let index = 0;

    function changeText() {
        let noBtn = document.getElementById("no");
        let yesBtn = document.getElementById("yes");

        if (index < noTexts.length) {
            noBtn.textContent = noTexts[index];
            index++;
        } else {
            noBtn.style.display = "none"; // Hide the button after enough attempts
        }
        
        yesBtn.style.fontSize = (120 + index * 50) + "px"; // Increase size of Yes button
    }

    function showCongrats() {
        document.getElementById("yes").style.display = "none";  // Hide "Yes" button
        document.getElementById("no").style.display = "none";   // Hide "No" button
        let congratsMessage = document.getElementById("congrats");
        congratsMessage.style.display = "block";  // Show the message
        setTimeout(() => {
            congratsMessage.style.opacity = "1";  // Fade in effect
        }, 100);
    }
</script>

</body>
</html>
