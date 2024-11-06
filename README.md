<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" >
    <meta name="viewport" content="width=device-width, initial-scale=1.0" >
    <title>Rock Paper Scissor Game</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            text-align: center;
            background-color:grey;

        }
        h1{
            background-color:#081b31;
            color: #fff;
            height:5rem;
            line-height: 5rem;
        }
        .choice{
            height: 165px;
            width:165px;
            border-radius:50%;
            display:flex;
            justify-content:center;
            align-items:center;
        }
        .choice:hover {
            cursor: pointer;
            background-color: #081b31;
        }
        img{
            height: 150px;
            width: 150px;
            object-fit:cover;
            border-radius:80%;
        }
        .choices{
            display:flex;
            justify-content: center;
            align-items:center;
            gap:3rem;
            margin-top: 5rem;

        }
        .score-board{
            display: flex;
            justify-content:center;
            align-items: center;
            font-size: 2rem;
            margin-top: 3rem;
            gap:5rem;
            
        }
        #user-score,#comp-score{
            font-size: 4rem;

        }
        .msg-content{
            margin-top: 5rem;
        }
        #msg{
            background-color: #081b31;
            color:#fff;
            font-size: 2rem;
            display: inline;
            padding: 1rem;
            border-radius: 1rem;
            
        }
    </style>
    
</head>
<body>
    <h1>Rock Paper Scissor Game</h1>
    <div class="choices">
        <div class="choice" id="rock">
            <img src="./image/rock.png" />
        </div>
        <div class="choice" id="paper">
            <img src="./image/paper.png"/>
        </div>
        <div class="choice" id="scissors">
            <img src="./image/scissors.png"/>
        </div>
    </div>
    <div class="score-board">
        <div class="score">
            <p id="user-score">0</p>
            <p>YOU</p>
        </div>
        <div class="Score">
            <p id="comp-score">0</p>
            <p>COMP</p>
        </div>
    </div>
    <div class="msg-content">
        <p id="msg">Play your move</p>
    </div>
    <script>
        let prompt ="do you wnat to play game"
         console.log(prompt)
        let userScore = 0;
         let compScore = 0; 

const choices = document.querySelectorAll(".choice");
const msg = document.querySelector("#msg");

const userScorePara = document.querySelector("#user-score");
const compScorePara = document.querySelector("#comp-score");


const genCompChoice = () =>{
    const options =["rock","paper","scissors"];
    const randIdx = Math.floor(Math.random() *3);
     return options[randIdx];
};

const drawGame =() => {
    msg.innerText= "Game was draw.Play again.";
    msg.style.backgroundcolor = "#081b31";
}
const showWinner = (userWin,userChoice,compChoice)=> {
    if(userWin) {
        userScore++;
        userScorePara.innerText = userScore;
        msg.innerText = `you win! your ${userChoice} beats ${compChoice}`;
        msg.style.backgroundcolor ="green";
    }else{
        compScore++;
        compScorePara.innerText = compScore;
        msg.innerText = `you lost. ${compChoice} beats your ${userChoice}`;
        msg.style.backgroundcolor ="red";

    }
}
 const playGame = (userChoice) => {
    // generate computer choice
    const compChoice = genCompChoice();


    if(userChoice === compChoice) {
        //draw game
        drawGame();
    }else{
        let userWin = true;
        if(userChoice ==="rock") {
            //scissors,paper
            userWin = compChoice ==="paper" ? false :true;
        }else if(userChoice ==="paper") {
            //rock,scissors
            userWin = compChoice ==="scissors" ? false : true;
        } else{
            //rock ,paper
            userWin = compChoice === "rock" ? false : true;
        }
        showWinner(userWin, userChoice,compChoice);

    }
    
 };
choices.forEach((choice) => {
    choice.addEventListener("click",() =>{
        const userChoice = choice.getAttribute("id");
        playGame(userChoice);
    });

});
    </script>
    
</body>
</html>- 👋 Hi, I’m @varshith245
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
varshith245/varshith245 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
