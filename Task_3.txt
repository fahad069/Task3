#include <iostream>
#include "Header.h"
using namespace std;

int main()
{

	Name one;


	char * fna = new char[10];
	char * lna = new char[10];
	cout << "Enter first name :";
	cin >> fna;
	cout << "Enter last name :";
	cin >> lna;
	Name three(fna, lna);
	one.setfirstname(fna);
	one.setlastname(lna);
	Name two = one;
	cout << "The First name is :" << one.getfirstname() << endl;
	cout << "The Last name is :" << one.getlastname() << endl;
	cout << endl;
	one.callall();
	cout << endl;
	cout << "The length of first and last name is : " << one.namelength() << endl;
	cout << "The full name is :" << one.fullName() << endl;
	cout << endl;
	if (one.isValidName() == 0)
	{
		cout << "***** The name is not valid ***** " << endl;
	}
	if (one.isValidName() != 0)
	{
		cout << "***** The name is valid ***** " << endl;
	}
	cout << endl;
	cout << "****** PRESS ENTER TO SEE THE OTHER SIDE OF PROGRAM ******";
	cout << endl;

	system("pause");

	system("cls");

	cout << "To see the copy constructor values :" << endl;
	cout << "The first name of copy constructor is :" << two.getfirstname() << endl;
	cout << "The Last name of copy constructor is :" << two.getlastname() << endl;
	system("pause");
	return 0;
}