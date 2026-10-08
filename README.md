# TheoryOfProbability
# Coin & Dice

A small probability project that runs in the browser. It starts with one question: what happens to the share of heads if you flip a coin 100,000 times? You can't predict a single flip, but a very long series of flips ends up close to one half. The site shows why, using a coin and a die.

## Pages

1. **Sample space.** What an experiment, an outcome and an event are, how to get a probability by counting, and a calculator that shows every step.
2. **Coin.** Flip a coin yourself, then let the computer flip it up to 100,000 times and watch the share of heads settle near 0.5.
3. **Die.** The same experiment with a die. The running average should end up near 3.5 and each face near 1/6.
4. **Results.** Numbers from a Python simulation with 100,000 trials and seed 42.
5. **Findings.** What the experiments showed and where they fall short.

There is also a home page with a short overview.

## Running it

Everything is in one HTML file. Download `Sample_Space.html` and open it in a browser. There is nothing to install and no server to start. The page loads two fonts (Outfit and Work Sans) from Google Fonts, so it needs internet for those. Without it the page falls back to system fonts and still works.

To put it on GitHub Pages, rename the file to `index.html` and turn Pages on in the repository settings.

The layout follows the system light or dark setting.

## The calculator

On the sample space page you choose 0 to 3 coins and 0 to 2 dice, then describe an event, for example "exactly 1 head" or "the sum of the dice is at least 9". The calculator then:

1. counts the ways each coin and die can land,
2. multiplies them to get the size of the sample space S,
3. writes out every outcome and highlights the ones in your event,
4. counts those outcomes,
5. divides to get P(A), and also shows P(not A).

It assumes every outcome is equally likely, which holds for a fair coin and a fair die. A "Run 10,000 trials" button simulates the same event with random numbers and puts the observed frequency next to the exact value.

I checked the exact values against a brute-force count for all 1,797 combinations of settings. They matched every time.

## Results

From the Python run with 100,000 trials:

- heads came up 50,089 times, a share of 0.50089
- the die average was 3.4948
- the distance from the target shrinks roughly like 1/√n, so ten times more accuracy takes about a hundred times more flips

The odd detail is that the die average at 10,000 rolls was closer to 3.5 than the one at 100,000 rolls. That is chance. The law of large numbers says the error gets smaller on average, not on every run.

## Limits

- Computer random numbers are pseudo-random, so this only imitates a real coin and die.
- One run proves little. The experiments are worth repeating.
- The fairness test needs enough data. With 100 flips it missed a coin that lands heads 55% of the time. With 1,000 flips it caught it.
- The Python script behind the Results page is not part of this repository, only its output.

## Author

Moldassanov Dias
Narxoz University
