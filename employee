#include <iostream>
#include <string>
using namespace std;

class Employee
{
private:
	string firstName, lastName;
protected:
	double salary;
public:

	Employee();
	Employee(const string&, const string&, const double&);
	Employee(const Employee&);
	~Employee();
	Employee& operator=(const Employee&);
	string getFirstName() const;
	string getLastName() const;
	double getSalary() const;
	void setFirstName(const string&);
	void setLastName(const string&);
	void setSalary(const double&);
	void readInfo(istream&);
	void printInfo(ostream&) const;
	friend istream& operator>>(istream&, Employee&);
	friend ostream& operator<<(ostream&, const Employee&);
};

Employee::Employee() : firstName("N/A"), lastName("N/A"), salary(0.00)
{
	cout << "Inside employee default constructor"<< endl;
}
Employee::Employee(const string& f, const string& l, const double& s) : firstName(f), lastName(l), salary(s)
{
	cout << "Inside employee non-default constructor"<< endl;
}
Employee::Employee(const Employee& e) : firstName(e.firstName), lastName(e.lastName), salary(e.salary)
{	
	cout << "Inside employee copy constructor"<< endl;
}
Employee::~Employee()
{
	cout << "Employee object destructed" << endl;
}
Employee& Employee::operator=(const Employee& e)
{
	firstName = e.firstName;
	lastName = e.lastName;
	salary = e.salary;
	return *this;
}
string Employee::getFirstName() const
{
	return firstName;
}
string Employee::getLastName() const
{
	return lastName;
}
double Employee::getSalary() const
{
	return salary;
}
void Employee::setFirstName(const string& f)
{
	firstName = f;
}
void Employee::setLastName(const string& l)
{
	lastName = l;
}
void Employee::setSalary(const double& s)
{
	salary = s;
}
void Employee::readInfo(istream& in)
{
	cout << endl;
	cout << "\tEnter first name: ";
	in >> firstName;
	cout << "\tEnter last name: ";
	in >> lastName;
	cout << "\tEnter salary: ";
	in >> salary;
}
void Employee::printInfo(ostream& out) const
{
	out << endl;
	out << "\tFull Name = " << firstName << " " << lastName << endl;
	out << "\tSalary = " << salary << endl;
}
istream& operator>>(istream& in, Employee& e)
{
	e.readInfo(in);
	return in;
}
ostream& operator<<(ostream& out, const Employee& e)
{
	e.printInfo(out);
	return out;
}

int main()
{
	Employee e1, e2("Jack", "Malcom", 1500.00);
	Employee e3(e2), e4;
	e4 = e2;
	cout << "Enter an employee ";
	cin >> e1;
	cout << "Employee 1 " << e1 << endl;
	cout << "Employee 2 " << e2 << endl;
	cout << "Employee 3 " << e3 << endl;
	cout << "Employee 4 " << e4 << endl;

	e1.~Employee();
	e2.~Employee();
	e3.~Employee();
	e4.~Employee();

	system("Pause");
	return 0;
}
