#include <iostream>
#include <random>

using namespace std;

int main() {
    // Better random number generation using <random>
    random_device rd;
    mt19937 gen(rd()); // Mersenne Twister engine
    uniform_int_distribution<> distr(1, 100);

    int secretNumber = distr(gen);
    int guess;

    cout << "Welcome to the Number Guessing Game!" << endl;
    cout << "Guess the number between 1 and 100." << endl;

    while (true) {
        cout << "Enter your guess: ";
        cin >> guess;

        if (guess < secretNumber) {
            cout << "Too low! Try again." << endl;
        } else if (guess > secretNumber) {
            cout << "Too high! Try again." << endl;
        } else {
            cout << "Correct! You guessed the number!" << endl;
            break;
        }
    }

    return 0;
}
