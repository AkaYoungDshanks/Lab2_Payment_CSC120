// Payment programing by chaunguyen 
#include <iostream>
#include<iomanip>
#include <cmath>
using namespace std;

int main()
{

    
    double loanAmount, annualRate, monthlyRate, monthlyPayment, totalAmount, interestPaid;
    int numPayments;

    // Taking the values 
    cout << "Loan amount: "; cin >> loanAmount;
    cout << "Annual interest rate (%): "; cin >> annualRate;
    cout << "Number of payments: "; cin >> numPayments;

    //  The monthly interest rate
    monthlyRate = annualRate / 1200;
    //  The monthly payment
    monthlyPayment = loanAmount * (monthlyRate * pow(1 + monthlyRate, numPayments)) /
        (pow(1 + monthlyRate, numPayments) - 1);

    //  The total amount paid for the loan
    totalAmount = monthlyPayment * numPayments;
    //  The total interest paid 
    interestPaid = totalAmount - loanAmount;

    //  Outputs
    cout << endl;
    cout << "loan Amount:           $" << setprecision(2) << fixed << setw(10) << loanAmount << endl;
    cout << "monthly Interest Rate:  " << setprecision(2) << fixed << setw(9) << monthlyRate * 100 << "%" << endl;
    cout << "number of Payments:     " << setw(10) << numPayments << endl;
    cout << "monthly Payment:       $" << setprecision(2) << fixed << setw(10) << monthlyPayment << endl;
    cout << "amount Paid Back:      $" << setprecision(2) << fixed << setw(10) << totalAmount << endl;
    cout << "interest Paid:         $" << setprecision(2) << fixed << setw(10) << interestPaid << endl;


    return 0;
}
