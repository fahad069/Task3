class Name{
private:
	int nlength;
	char* firstname;
	char* lastname;
	char* anothername;
	char *fulln;
public:
	Name();
	Name(char*, char*);// parameterized constructor with default values
	Name(const Name&); //copy constructor
	~Name();//destructor
	void setfirstname(char *);
	char * getfirstname();
	void setlastname(char *);
	char * getlastname();
	//	void copyname(Name&); //this is not a copy constructor, I want this function to copy the contents of one name(firstName and lastName both) to another name.
	void camelcase(); // make first letter capital of both attributes
	void tlower(); //convert name to lower case alphabets
	void tupper(); //convert name into upper case alphabets
	int namelength(); // both first and last (excluding space)
	void swapnames(); // firstName becomes lastName and vice versa
	void display(); //prints name(firstName and lastName with space in between)
	char* fullName(); //concatenate both attributes and return full name with a space in between both
	bool isValidName();// name should contain only alphabets - no special characters or digits
	void callall();


	////provide setters/getters for Name class. Remember: Setters with no memory leakage.
	// provide other relevant methods you want like your own strLength and strCopy function  in a separate file known as helperFunctions.h and helperFunctions.cpp etc; 
};
