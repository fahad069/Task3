#include <iostream>
#include "Header.h"
using namespace std;

Name::Name()
{
	nlength = 0;
	firstname = nullptr;
	lastname = nullptr;
	anothername = nullptr;
	fulln = nullptr;
}

Name::Name(char*a, char*b)
{
	nlength = 0;
	firstname = nullptr;
	lastname = nullptr;
	anothername = nullptr;
	fulln = nullptr;
}

Name::Name(const Name& obj)
{
	nlength = obj.nlength;

	int length = 0;
	for (int i = 0; obj.firstname[i] != '\0'; i++)
	{
		length++;
	}
	firstname = new char[length + 1];
	for (int i = 0; i < length; i++)
	{
		firstname[i] = obj.firstname[i];
	}
	firstname[length] = '\0';


	length = 0;
	for (int i = 0; obj.lastname[i] != '\0'; i++)
	{
		length++;
	}
	lastname = new char[length + 1];
	for (int i = 0; i < length; i++)
	{
		lastname[i] = obj.lastname[i];
	}
	lastname[length] = '\0';







}

Name::~Name()
{
	cout << "Destructor" << endl;
	delete[]firstname;
	firstname = nullptr;
	delete[]lastname;
	lastname = nullptr;
	delete[] anothername;
	anothername = nullptr;
	delete[]fulln;
	fulln = nullptr;

}
void Name::setfirstname(char *fn)
{
	int length = 0;
	for (int i = 0; fn[i] != '\0'; i++)
	{
		length++;
	}
	firstname = new char[length + 1];
	for (int i = 0; i < length; i++)
	{
		firstname[i] = fn[i];
	}
	firstname[length] = '\0';
}

char*  Name::getfirstname()
{
	int length = 0;
	for (int i = 0; firstname[i] != '\0'; i++)
	{
		length++;
	}
	char *temp = new char[length + 1];
	for (int i = 0; i < length; i++)
	{
		temp[i] = firstname[i];
	}
	temp[length] = '\0';
	return temp;
}


void Name::setlastname(char *ln)
{
	int length = 0;
	for (int i = 0; ln[i] != '\0'; i++)
	{
		length++;
	}
	lastname = new char[length + 1];
	for (int i = 0; i < length; i++)
	{
		lastname[i] = ln[i];
	}
	lastname[length] = '\0';
}

char*  Name::getlastname()
{
	int length = 0;
	for (int i = 0; lastname[i] != '\0'; i++)
	{
		length++;
	}
	char *temp = new char[length + 1];
	for (int i = 0; i < length; i++)
	{
		temp[i] = lastname[i];
	}
	temp[length] = '\0';
	return temp;
}

/*void Name :: copyname(Name&)
{
Sir, you haven't teach this kind of function yet.

}*/


void Name::camelcase()
{
	if (firstname[0] >= 97 && firstname[0] <= 122)
	{
		firstname[0] = firstname[0] - 32;
	}

	if (lastname[0] >= 97 && lastname[0] <= 122)
	{
		lastname[0] = lastname[0] - 32;
	}
	cout << "After camel case First name is : " << firstname << endl;
	cout << "After camel case Last name is : " << lastname << endl;
}

void Name::tlower()
{

	for (int i = 0; firstname[i] != '\0'; i++)
	{
		if (firstname[i] >= 65 && firstname[i] <= 90)
		{
			firstname[i] = firstname[i] + 32;
		}
	}

	for (int i = 0; lastname[i] != '\0'; i++)
	{
		if (lastname[i] >= 65 && lastname[i] <= 90)
		{
			lastname[i] = lastname[i] + 32;
		}
	}
	cout << "After Lower First name is : " << firstname << endl;
	cout << "After Lower Last name is : " << lastname << endl;
}


void Name::tupper()
{

	for (int i = 0; firstname[i] != '\0'; i++)
	{
		if (firstname[i] >= 97 && firstname[i] <= 122)
		{
			firstname[i] = firstname[i] - 32;
		}
	}

	for (int i = 0; lastname[i] != '\0'; i++)
	{
		if (lastname[i] >= 97 && lastname[i] <= 122)
		{
			lastname[i] = lastname[i] - 32;
		}
	}
	cout << "After Upper First name is : " << firstname << endl;
	cout << "After Upper Last name is : " << lastname << endl;
}

int Name::namelength()
{
	int Flength = 0;
	int Llength = 0;
	for (int i = 0; firstname[i] != '\0'; i++)
	{
		Flength++;
	}

	for (int i = 0; lastname[i] != '\0'; i++)
	{
		Llength++;
	}

	nlength = Flength + Llength;

	return nlength;
}

void Name::swapnames()
{
	int FNlength = 0;
	int LNlength = 0;
	for (int i = 0; firstname[i] != '\0'; i++)
	{
		FNlength++;
	}
	char *tempf = new char[FNlength + 1];
	for (int i = 0; i < FNlength; i++)
	{
		tempf[i] = firstname[i];
	}
	tempf[FNlength] = '\0';


	for (int i = 0; lastname[i] != '\0'; i++)
	{
		LNlength++;
	}
	char *templ = new char[LNlength + 1];
	for (int i = 0; i < LNlength; i++)
	{
		templ[i] = lastname[i];
	}
	templ[LNlength] = '\0';

	firstname = new char[LNlength + 1];
	lastname = new char[FNlength + 1];

	for (int i = 0; i < LNlength; i++)
	{
		firstname[i] = templ[i];
	}
	firstname[LNlength] = '\0';


	for (int i = 0; i < FNlength; i++)
	{
		lastname[i] = tempf[i];
	}
	lastname[FNlength] = '\0';
	cout << "After swaping The first name is :" << firstname << endl;
	cout << "After swaping The last name is :" << lastname << endl;
}

void Name::display()
{

	cout << "Reverse Name is :" << firstname << '\t' << lastname << endl;
}

char * Name::fullName()
{
	int fulllength = 0;
	int Flength = 0;
	int Llength = 0;
	for (int i = 0; firstname[i] != '\0'; i++)
	{
		Flength++;
	}

	for (int i = 0; lastname[i] != '\0'; i++)
	{
		Llength++;
	}

	nlength = Flength + Llength;

	fulln = new char[nlength + 1];
	for (int i = 0; lastname[i] != '\0'; i++)
	{
		fulln[i] = lastname[i];
		fulllength++;
	}

	fulln[fulllength] = 32;
	fulllength++;

	for (int i = 0; firstname[i] != '\0'; i++)
	{
		fulln[fulllength] = firstname[i];
		fulllength++;
	}

	fulln[fulllength] = '\0';

	return fulln;
}

bool Name::isValidName()
{

	int fulllength = 0;
	int Flength = 0;
	int Llength = 0;
	for (int i = 0; firstname[i] != '\0'; i++)
	{
		Flength++;
	}

	for (int i = 0; lastname[i] != '\0'; i++)
	{
		Llength++;
	}

	nlength = Flength + Llength;

	fulln = new char[nlength + 1];
	for (int i = 0; firstname[i] != '\0'; i++)
	{
		fulln[i] = firstname[i];
		fulllength++;
	}

	for (int i = 0; lastname[i] != '\0'; i++)
	{
		fulln[fulllength] = lastname[i];
		fulllength++;
	}

	fulln[fulllength] = '\0';

	int l = 0;
	for (int i = 0; fulln[i] != '\0'; i++)
	{
		l++;
	}

	int j = 0;

	for (int i = 0; fulln[i] != '\0'; i++)
	{
		if ((fulln[i] >= 65 && fulln[i] <= 90))
		{
			j++;
		}
		if (fulln[i] >= 97 && fulln[i] <= 122)
		{
			j++;
		}
	}
	if (j == l)
	{
		return true;
	}
	else
	{
		return false;
	}
}


void Name::callall()
{
	camelcase();
	cout << "**************************" << endl;
	cout << endl;
	tlower();
	cout << "**************************" << endl;
	cout << endl;
	tupper();
	cout << "**************************" << endl;
	cout << endl;
	swapnames();
	cout << "**************************" << endl;
	cout << endl;
	display();
}