    const words = ["apple", "banana", "cherry", "grape", "orange", "watermelon"];

    function generatedRandomWord() {
      return words[Math.floor(Math.random() * words.length)];
    }

    function guessWord() {
      const targetWord = generatedRandomWord().toLowerCase();
      const maxAttempts = 5;
      let attempts = 0;

      while (attempts < maxAttempts) {
        const guess = prompt(`Guess a word from: apple, banana, cherry, grape, orange, watermelon. You have ${maxAttempts} attempts!`);

        if (guess === null) {
          alert("Thanks for playing!");
          break;
        }

        const userGuess = guess.toLowerCase();
        attempts++;

        if (userGuess === targetWord) {
            
          alert(`Congratulations! You guessed the word "${targetWord}" correctly in ${attempts} attempts.`);
          const playAgain = confirm("Do you want to play again?");
          if (playAgain) {
            guessWord();
          } else {
            alert("Thanks for playing!");
          }
          break;
        } else {
          alert(`Incorrect guess! You have ${maxAttempts - attempts} attempts remaining.`);
        }
      }

      if (attempts === maxAttempts) {
        alert(`Game over! You failed to guess the word in "${maxAttempts}" attempts. The word was "${targetWord}".`);
        const playAgain = confirm("Do you want to play again?");
        if (playAgain) {
            guessWord();
        } else {
          alert("Thanks for playing!");
        }
      }
    }

    guessWord();

