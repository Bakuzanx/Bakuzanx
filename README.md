#include <iostream>
#include <conio.h>
#include <cstdlib>

using namespace std;

// Global variables for employee data
char ename[50];
char eadd[25];
char pos[15];
int eid;
int hrw;  // hours worked
float phic, pagibig, late, ca, gross, net;
float totded = 0;  // total deduction
int choice;

// Function prototypes
void getEmployee();
void getWorkhr();
float getDeduction();
void payrollSummary();

void getEmployee() {
    system("color 1F");
    cout << "\n\n======= Employee Info =======\n";
    cout << "Enter Employee Id: ";
    cin >> eid;
    cout << "Enter Employee Name: ";
    cin.ignore();
    cin.getline(ename, 50);
    cout << "Enter Address: ";
    cin.getline(eadd, 25);
    cout << "Enter Position: ";
    cin.getline(pos, 15);
}

void getWorkhr() {
    cout << "\n\n======= Working Hours Information =======\n";
    cout << "Employee ID: " << eid << "\n";
    cout << "Enter Hours Worked: ";
    cin >> hrw;
    cout << "Enter Hourly Rate: ";
    float hrRate;
    cin >> hrRate;
    gross = hrw * hrRate;  // calculate gross pay
    cout << "Gross Pay: " << gross << "\n";
}

float getDeduction() {
    system("color 30");
    cout << "\n\n======= Deduction Information =======\n";
    cout << "Enter Philhealth Deduction: ";
    cin >> phic;
    cout << "Enter Pagibig Deduction: ";
    cin >> pagibig;
    cout << "Enter Late Deduction: ";
    cin >> late;
    cout << "Enter Cash Advance Deduction: ";
    cin >> ca;
    totded = phic + pagibig + late + ca;
    cout << "Total Deductions: " << totded << "\n";
    return totded;
}

void payrollSummary() {
    system("cls");
    cout << "\n\n======= Payroll Summary =======\n";
    cout << "Employee ID: " << eid << "\n";
    cout << "Employee Name: " << ename << "\n";
    cout << "Employee Address: " << eadd << "\n";
    cout << "Employee Position: " << pos << "\n";
    cout << "Gross Pay: " << gross << "\n";
    cout << "Total Deductions: " << totded << "\n";
    net = gross - totded;
    cout << "Net Pay: " << net << "\n";
}

int main() {
    system("cls");
    cout << "\n\n======= Payroll System =======\n";
    cout << "1) Employee record\n";
    cout << "2) Working hours\n";
    cout << "3) Calculate deduction\n";
    cout << "4) Payroll Summary\n";
    cout << "Select a choice [1-4]: ";
    cin >> choice;

    switch (choice) {
        case 1:
            getEmployee();
            break;
        case 2:
            getEmployee();
            getWorkhr();
            break;
        case 3:
            getEmployee();
            getWorkhr();
            getDeduction();
            break;
        case 4:
            getEmployee();
            getWorkhr();
            getDeduction();
            payrollSummary();
            break;
        default:
            cout << "Invalid choice.\n";
            break;
    }

    return 0;
}
