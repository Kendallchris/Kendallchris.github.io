+++
title = 'My First Post'
date = 2023-12-04T13:25:35-08:00
draft = false
+++

# A guessing game to start coding in C++

In this post, I want to share a fun and interactive way to start coding in C++. The project is a simple guessing game that demonstrates basic programming concepts in C++, such as loops, conditional statements, and standard input/output.

## The Guessing Game

The game allows a player to guess a randomly generated number within a specified range. After each guess, the game provides feedback on how close the guess is to the target number. The player has three attempts to guess the correct number.

Here's the code for the guessing game:

```C++
#include <iostream>
#include <cstdlib>
#include <ctime>

using std::cout;
using std::cin;
using std::endl;

int main() {
    srand(time(0));
    int magic, guess, cont = 1, maxNum;
    double close;

    while (cont == 1) {
        cout << "What is the maximum number you want?" << endl;
        cin >> maxNum;
        magic = rand() % maxNum + 1;
        cout << "Please guess a number" << endl;
        for (int curTry = 0; curTry < 3; ++curTry) {
            cout << "Attempt #" << curTry + 1 << ": ";
            cin >> guess;
            close = abs(magic - guess) / static_cast<double>(maxNum);
            if (guess == magic) {
                cout << "You win!" << endl;
                break;
            } else if (curTry < 2){
                cout << "Try again!" << endl;
                if (close < 0.25) {
                    cout << "Hot!" << endl;
                } else if (close > 0.25 && close < 0.50) {
                    cout << "Warm!" << endl;
                } else if (close > 0.50 && close < 0.75) {
                    cout << "Cold!" << endl;
                } else {
                    cout << "Freezing!" << endl;
                }
            }
        }
        if (guess != magic) {
            cout << "Loser" << endl;
        }
        cout << "Wanna go again? [0 for no]";
        cin >> cont;
    }
    return 0;
}
```

This simple game is great for beginners to understand the fundamentals of C++. The code involves using random number generation, loops for repeated attempts, and basic input/output to interact with the user.

For more details and to see the complete project, check out the GitHub repository [here](https://github.com/Kendallchris/guess-game-f2022)
