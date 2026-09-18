# Basic-Calculator.-
#include <iostream>
#include <iomanip>
#include <limits>
using namespace std;

int main()
{
    double num1, num2;
    int choice;
    char again;

    do
    {
        cout << "\n=====================================\n";
        cout << "        BASIC CALCULATOR\n";
        cout << "=====================================\n";
        cout << "1. Addition (+)\n";
        cout << "2. Subtraction (-)\n";
        cout << "3. Multiplication (*)\n";
        cout << "4. Division (/)\n";
        cout << "5. Modulus (%)\n";
        cout << "6. Exit\n";
        cout << "=====================================\n";

        // Input validation for menu choice
        cout << "Enter your choice (1-6): ";

        while (!(cin >> choice))
        {
            cout << "Invalid input! Please enter a number from 1 to 6: ";
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
        }

        // Exit option
        if (choice == 6)
        {
            cout << "\nThank you for using the Basic Calculator!\n";
            break;
        }

        // Validate menu range
        if (choice < 1 || choice > 6)
        {
            cout << "\nInvalid choice! Please select between 1 and 6.\n";
            continue;
        }

        // Input numbers
        cout << "Enter first number: ";

        while (!(cin >> num1))
        {
            cout << "Invalid input! Please enter a valid number: ";
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
        }

        cout << "Enter second number: ";

        while (!(cin >> num2))
        {
            cout << "Invalid input! Please enter a valid number: ";
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
        }

        // Perform operation
        cout << fixed << setprecision(2);

        switch (choice)
        {
            case 1:
                cout << "\nResult: " << num1 << " + "
                     << num2 << " = " << num1 + num2 << endl;
                break;

            case 2:
                cout << "\nResult: " << num1 << " - "
                     << num2 << " = " << num1 - num2 << endl;
                break;

            case 3:
                cout << "\nResult: " << num1 << " * "
                     << num2 << " = " << num1 * num2 << endl;
                break;

            case 4:
                if (num2 == 0)
                {
                    cout << "\nError: Division by zero is not allowed!\n";
                }
                else
                {
                    cout << "\nResult: " << num1 << " / "
                         << num2 << " = " << num1 / num2 << endl;
                }
                break;

            case 5:
                // Modulus requires integer values
                if (num2 == 0)
                {
                    cout << "\nError: Modulus by zero is not allowed!\n";
                }
                else
                {
                    int a = static_cast<int>(num1);
                    int b = static_cast<int>(num2);

                    cout << "\nResult: " << a << " % "
                         << b << " = " << a % b << endl;
                }
                break;

            default:
                cout << "\nInvalid choice!\n";
        }

        cout << "\nDo you want to perform another calculation? (y/n): ";
        cin >> again;

        while (again != 'y' && again != 'Y' &&
               again != 'n' && again != 'N')
        {
            cout << "Invalid input! Please enter y or n: ";
            cin >> again;
        }

    } while (again == 'y' || again == 'Y');

    cout << "\n=====================================\n";
    cout << "        PROGRAM ENDED\n";
    cout << "=====================================\n";

    return 0;
}