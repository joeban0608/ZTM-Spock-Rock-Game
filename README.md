# ZTM-Spock-Rock-Game

This is pratice from ZTM classes: [javascript-web-projects-to-build-your-portfolio-resume-第十五章](https://www.udemy.com/course/javascript-web-projects-to-build-your-portfolio-resume/?couponCode=ACCAGE0923)

> [click to watch the demo](https://joeban0608.github.io/ZTM-Spock-Rock-Game/)

---

resource:

- confetti JS: https://www.cssscript.com/confetti-falling-animation/
  ```jsx
  import { startConfetti, stopConfetti, removeConfetti } from "./confetti.js";

  // Check result, increase scores, update resultText
  function updateScore(playerChoice) {
    if (playerChoice === computerChoice) {
      resultText.textContent = "It's a tie.";
    } else {
      const choice = choices[playerChoice];
      if (choice.defeats.indexOf(computerChoice) > -1) {
        startConfetti();
        resultText.textContent = "You Won!";
        playerScoreNumber++;
        playerScoreEl.textContent = playerScoreNumber;
      } else {
        resultText.textContent = "You Lost!";
        computerScoreNumber++;
        computerScoreEl.textContent = computerScoreNumber;
      }
    }
  }

  // Reset all 'selected' icons, remove confetti
  function resetSelected() {
    allGameIcons.forEach((icon) => {
      icon.classList.remove("selected");
    });
    stopConfetti();
    removeConfetti();
  }
  ```
