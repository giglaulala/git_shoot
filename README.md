# git_shoot
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script>
    function getComputerChoice() {
      let Choices = ["Rock", "Paper", "Scissors"];
      let computer_choice = Choices[Math.floor(Math.random() * Choices.length)];
      return computer_choice;
    }

    function comparingChoices(playerSelection, computerSelection) {
      
      playerSelection = playerSelection.toUpperCase();
      computerSelection = computerSelection.toUpperCase();

      if (playerSelection === computerSelection) {
        return "Draw!";
      } else if (
        (playerSelection === "ROCK" && computerSelection === "SCISSORS") ||
        (playerSelection === "PAPER" && computerSelection === "ROCK") ||
        (playerSelection === "SCISSORS" && computerSelection === "PAPER")
      ) {
        return "You win!";
      } else {
        return "You Lose!";
      }
    }
    
    let yourScore = 0;
    let computerScore = 0;

    function playGame() {
      let playerChoice, result;

      while (yourScore !== 5 && computerScore !== 5) {
        playerChoice = prompt("Enter your Choice: ").toUpperCase();
        let computerChoice = getComputerChoice();
        result = comparingChoices(playerChoice, computerChoice);
        console.log(result);

        if (result.slice(0, 8) === "You Lose") {
          computerScore++;
        } else if (result === "Draw!") {
          console.log("It's a draw");
        } else {
          yourScore++;
        }

        if (yourScore === 5 || computerScore === 5) {
          break;
        }
      }

      return { yourScore, computerScore };
    }

    console.log(playGame());

  </script>
</head>
<body>

</body>
</html>
