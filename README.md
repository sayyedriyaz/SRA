!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Love Proposal</title>
    <style>
        body {
            background-color: pink;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            position: relative;
        }
        .heart {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('heart_background.png') no-repeat center center fixed;
            background-size: cover;
            z-index: -1;
        }
        .message-box {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            text-align: center;
            width: 300px;
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background-color: pink;
            cursor: pointer;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <div class="heart"></div>
    <div class="message-box" id="messageBox">
        <div id="message">IT'S A SPECIAL MESSAGE FOR YOU</div>
        <button id="nextBtn">CLICK TO SEE</button>
    </div>
    <script>
        const messages = [
            "I was thinking of talking to you for a long time but I was not getting the courage to talk to you, that is why today I am talking to you by creating this website.",
            "I don't know how many people there are in this world, but you are the only one whom I fell in love with for the first time after seeing you.",
            "I was going to tell you this at the time of the unit test paper, but then I thought that maybe you would get angry with me and stop talking to me, that's why I did not tell you, but today I am saying, SORRY TO SAY 🤞",
            "I LIKE YOU SAMREEN 🤞🤞"
        ];
        
        const finalMessages = {
            yes: "Shayad Ramzaan ki dua kabool ho gayi",
            no: "Sorry to say Samreen shayad mujhe ye aapko bolna hi nahi chahiye tha 😔😔😔"
        };
        
        let currentMessageIndex = 0;
        
        document.getElementById('nextBtn').addEventListener('click', function() {
            if (currentMessageIndex < messages.length) {
                document.getElementById('message').innerText = messages[currentMessageIndex];
                currentMessageIndex++;
                
                if (currentMessageIndex === messages.length) {
                    this.innerText = "YES or NO";
                    this.setAttribute('id', 'finalBtn');
                    
                    document.getElementById('finalBtn').addEventListener('click', function() {
                        const userResponse = confirm("Do you like me?");
                        if (userResponse) {
                            alert(finalMessages.yes);
                        } else {
                            alert(finalMessages.no);
                        }
                    });
                }
            }
        });
    </script>
</body>
</html>
