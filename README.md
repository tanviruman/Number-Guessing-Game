# Number Guessing Game 

This C program implements a number guessing game where Player-1 sets a number and Player-2 tries to guess it within a limited number of attempts.

## Table of Contents

1. [Introduction](#introduction)
2. [Functionality](#functionality)
3. [Variables](#variables)
4. [Program Flow](#program-flow)
5. [Usage](#usage)
6. [Example](#example)

## Introduction

This program allows two players to play a simple guessing game. Player-1 chooses a number, and Player-2 has a certain number of attempts to guess the number. If Player-2 guesses correctly, they win. If they exhaust all attempts without guessing correctly, Player-1 wins.

## Functionality

- Player-1 inputs a secret number.
- Player-2 is given a number of attempts to guess the secret number.
- Player-2 makes guesses and is informed whether the guess is correct or how many attempts remain.
- The game ends when Player-2 guesses the number correctly or runs out of attempts.

## Variables

- `X`: The secret number chosen by Player-1.
- `N`: The number of attempts allowed for Player-2.
- `Guess`: The current guess made by Player-2.
- `Tries_left`: The number of remaining attempts for Player-2.

## Program Flow

1. The program prompts Player-1 to enter a secret number (`X`).
2. The program prompts Player-1 to enter the number of attempts allowed for Player-2 (`N`).
3. `Tries_left` is initialized with the value of `N`.
4. A `while` loop runs as long as `Tries_left` is greater than 0:
    - Player-2 is prompted to enter a guess (`Guess`).
    - If `Guess` equals `X`, Player-2 wins, and the program prints a success message and breaks out of the loop.
    - If `Guess` does not equal `X`, `Tries_left` is decremented by 1, and the program prints the number of remaining attempts.
5. If `Tries_left` reaches 0, Player-1 wins, and the program prints a failure message.

## Usage

1. **Compile the Program**

   ```sh
   gcc guessing_game.c -o guessing_game
   ```

2. **Run the Program**

   ```sh
   ./guessing_game
   ```

3. **Game Flow**

   - Player-1 enters the secret number and the number of allowed attempts.
   - Player-2 makes guesses until they either guess correctly or run out of attempts.

## Example

### Player-1 Input

```
Enter the number given by Player-1: 50
Enter the number of tries given for Player-2: 5
```

### Player-2 Guesses

```
Enter your Guess: 30
Wrong, 4 Choice(s) Left!
Enter your Guess: 40
Wrong, 3 Choice(s) Left!
Enter your Guess: 50
Right, Player-2 wins!
```

If Player-2 does not guess correctly within the allowed attempts:

```
Enter your Guess: 30
Wrong, 4 Choice(s) Left!
Enter your Guess: 40
Wrong, 3 Choice(s) Left!
Enter your Guess:

```

### Code Explanation

 let's break down the code step by step to explain its functionality.

```c
#include <stdio.h>

int main() {
    int X, N, Guess, Tries_left;

    // Prompt Player-1 to enter the secret number
    printf("Enter the number given by Player-1: ");
    scanf("%d", &X);

    // Prompt Player-1 to enter the number of attempts allowed for Player-2
    printf("Enter the number of tries given for Player-2: ");
    scanf("%d", &N);

    // Initialize the number of tries left for Player-2
    Tries_left = N;

    // Loop to allow Player-2 to make guesses until they run out of attempts
    while (Tries_left > 0) {
        // Prompt Player-2 to enter their guess
        printf("Enter your Guess: ");
        scanf("%d", &Guess);

        // Check if the guess is correct
        if (Guess == X) {
            // If the guess is correct, Player-2 wins and the game ends
            printf("Right, Player-2 wins!\n");
            break;
        } else {
            // If the guess is incorrect, decrement the number of tries left
            Tries_left--;
            printf("Wrong, %d Choice(s) Left!\n", Tries_left);
        }
    }

    // If Player-2 runs out of attempts, Player-1 wins
    if (Tries_left == 0) {
        printf("Player-1 wins!\n");
    }

    return 0;
}

#### 1. Include Standard I/O Library
```c
#include <stdio.h>
```
This line includes the standard input-output library, which allows us to use functions like `printf` and `scanf`.

#### 2. Main Function
```c
int main() {
```
This is the main function where the execution of the program begins.

#### 3. Declare Variables
```c
int X, N, Guess, Tries_left;
```
Here, four integer variables are declared:
- `X`: The secret number that Player-1 will input.
- `N`: The number of attempts that Player-2 will have to guess the secret number.
- `Guess`: The current guess made by Player-2.
- `Tries_left`: The number of attempts remaining for Player-2.

#### 4. Input Secret Number and Number of Tries
```c
printf("Enter the number given by Player-1: ");
scanf("%d", &X);
printf("Enter the number of tries given for Player-2: ");
scanf("%d", &N);
```
The program prompts Player-1 to enter the secret number (`X`) and the number of tries (`N`) allowed for Player-2. These values are read using `scanf`.

#### 5. Initialize Tries Left
```c
Tries_left = N;
```
The variable `Tries_left` is initialized with the value of `N`, representing the total number of attempts Player-2 has.

#### 6. While Loop for Player-2 Guesses
```c
while (Tries_left > 0) {
```
This loop continues as long as `Tries_left` is greater than 0.

##### 6.1. Prompt for a Guess
```c
printf("Enter your Guess: ");
scanf("%d", &Guess);
```
Player-2 is prompted to enter their guess, which is read into the variable `Guess`.

##### 6.2. Check the Guess
```c
if (Guess == X) {
    printf("Right, Player-2 wins!\n");
    break;
} else {
    Tries_left--;
    printf("Wrong, %d Choice(s) Left!\n", Tries_left);
}
```
- If `Guess` equals `X`, Player-2 has guessed correctly. The program prints a success message and breaks out of the loop.
- If `Guess` does not equal `X`, `Tries_left` is decremented by 1, and the program prints the number of remaining attempts.

#### 7. Check for Out of Tries
```c
if (Tries_left == 0) {
    printf("Player-1 wins!\n");
}
```
If `Tries_left` reaches 0 (i.e., Player-2 has used up all attempts without guessing correctly), the program prints a message indicating that Player-1 wins.

#### 8. End of Main Function
```c
return 0;
}
```
The main function returns 0, indicating that the program has executed successfully.

### Summary
- Player-1 inputs a secret number and the number of allowed attempts for Player-2.
- Player-2 attempts to guess the number within the given attempts.
- The program informs Player-2 whether their guess is correct and how many attempts are left.
- The game ends either when Player-2 guesses correctly or runs out of attempts, determining the winner.
