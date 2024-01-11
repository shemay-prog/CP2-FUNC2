#include <iostream>
#include <cstdlib>

using namespace std;

int main()
{
    int addVal = 0, MDAS;
    int stored = 1000; // stored value
    bool wantToCont = true;
    char continueChoice;

    while (wantToCont) {
        system("cls");
        cout << "\nexit [0] | add [1] | subtract [2]: "; // main menu
        cin >> MDAS;

        if (MDAS == 0) {
            wantToCont = false; // exit the loop
            cout << "\nGoodbye!";
            exit(0); // terminate the program
        }
        else if (MDAS == 1 || MDAS == 2) {
            cout << "\nEnter a value: ";
            cin >> addVal;

            switch (MDAS) {
            case 1:
                stored += addVal;
                break;
            case 2:
                stored -= addVal;
                break;
            }

            cout << "\n" << stored << endl;

            cout << "\nDo you want to continue? (y/n): ";
            cin >> continueChoice;

            if (continueChoice != 'y') {
                wantToCont = false;
                cout << "\nGoodbye!";
                exit(0);
            }
        }
        else {
            cout << "Invalid input\n\n";
        }
    }

    return 0;
}
