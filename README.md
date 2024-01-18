#include <iostream>
#include <cstdlib>
#include <iomanip>

using namespace std;

int main()
{
    int addVal = 0, MDAS;
    int stored = 1000; // stored value
    bool wantToCont = true;
    char continueChoice;
    
    while (wantToCont) {
        system("cls");
        cout << setfill('=') << setw(40) << "=";
        cout << "\n\t\t  Menu\n";
        cout << setfill('=') << setw(40) << "=";
        cout << "\n[0]Exit \n[1]Add \n[2]Subtract \n[3]Multiply \n[4]Divide \n[5]Modulus\n\n\nEnter your choice: "; // main menu
        cin >> MDAS;

        if (MDAS == 0) {
            wantToCont = false; //exit the loop
            cout << "\nGoodbye!";
            exit(0); // terminate the program
        } else if (MDAS == 1 || MDAS == 2 || MDAS == 3 || MDAS == 4 || MDAS == 5) {
            cout << "Enter a value: ";
            cin >> addVal;

            switch (MDAS) {
            case 1:
                stored += addVal;
                break;
            case 2:
                stored -= addVal;
                break;
            case 3:
                stored *= addVal;
                break;
            case 4:
                stored /= addVal;
            case 5:
                stored %= addVal;
                break;
            default:
                "\n\nInvalid input\n\n";
            }

            cout << "\nResult: " << stored << endl;

            cout << "\nDo you want to continue? (y/n): ";
            cin >> continueChoice;

            if (continueChoice != 'y') {
                wantToCont = false;
                cout << "\nGoodbye!";
                exit(0);
            }
        } else {
            cout << "Invalid input\n\n";
        }
    }

    return 0;
}
