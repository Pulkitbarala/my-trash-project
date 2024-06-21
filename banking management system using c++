#include <iostream>
#include <vector>
#include <string>

using namespace std;

class BankAccount {
public:
    string name;
    string address;
    int accountNumber;
    double balance;

    BankAccount(string n, string add, int accNum, double bal) {
        name = n;
        address = add;
        accountNumber = accNum;
        balance = bal;
    }

    void display() {
        cout << "Account Number: " << accountNumber << endl;
        cout << "Name: " << name << endl;
        cout << "Address: " << address << endl;
        cout << "Balance: " << balance << endl;
    }
};

vector<BankAccount> accounts;
int nextAccountNumber = 1;

BankAccount* findAccount(int accountNumber) {
    for (auto &account : accounts) {
        if (account.accountNumber == accountNumber) {
            return &account;
        }
    }
    return nullptr;
}

void createAccount() {
    string name, address;
    double initialAmount;

    cout << "Enter Name: ";
    cin.ignore();
    getline(cin, name);
    cout << "Enter Address: ";
    getline(cin, address);
    cout << "Enter Initial Amount: ";
    cin >> initialAmount;

    BankAccount newAccount(name, address, nextAccountNumber++, initialAmount);
    accounts.push_back(newAccount);
    cout << "Account created successfully with Account Number: " << newAccount.accountNumber << endl;
}

void withdrawAmount() {
    int accountNumber;
    double amount;

    cout << "Enter Account Number: ";
    cin >> accountNumber;
    BankAccount* account = findAccount(accountNumber);

    if (account) {
        cout << "Enter Amount to Withdraw: ";
        cin >> amount;
        if (account->balance >= amount) {
            account->balance -= amount;
            cout << "Amount withdrawn successfully!" << endl;
        } else {
            cout << "Insufficient funds! Withdrawal amount exceeds balance." << endl;
        }
    } else {
        cout << "Account not found!" << endl;
    }
}

void insertAmount() {
    int accountNumber;
    double amount;

    cout << "Enter Account Number: ";
    cin >> accountNumber;
    BankAccount* account = findAccount(accountNumber);

    if (account) {
        cout << "Enter Amount to Insert: ";
        cin >> amount;
        account->balance += amount;
        cout << "Amount inserted successfully!" << endl;
    } else {
        cout << "Account not found!" << endl;
    }
}

void viewAccountStatement() {
    int accountNumber;

    cout << "Enter Account Number: ";
    cin >> accountNumber;
    BankAccount* account = findAccount(accountNumber);

    if (account) {
        account->display();
    } else {
        cout << "Account not found!" << endl;
    }
}

void deleteAccount() {
    int accountNumber;

    cout << "Enter Account Number: ";
    cin >> accountNumber;
    for (auto it = accounts.begin(); it != accounts.end(); ++it) {
        if (it->accountNumber == accountNumber) {
            accounts.erase(it);
            cout << "Account deleted successfully!" << endl;
            return;
        }
    }
    cout << "Account not found!" << endl;
}

int main() {
    int choice;

    while (true) {
        cout << "Select an option:" << endl;
        cout << "1. Create New Account" << endl;
        cout << "2. Withdraw Amount" << endl;
        cout << "3. Insert Amount" << endl;
        cout << "4. View Account Statement" << endl;
        cout << "5. Delete Account" << endl;
        cout << "6. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                createAccount();
                break;
            case 2:
                withdrawAmount();
                break;
            case 3:
                insertAmount();
                break;
            case 4:
                viewAccountStatement();
                break;
            case 5:
                deleteAccount();
                break;
            case 6:
                return 0;
            default:
                cout << "Invalid choice, please try again." << endl;
        }
    }

    return 0;
}
