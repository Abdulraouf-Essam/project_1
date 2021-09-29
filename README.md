#include<iostream>
using namespace std;
struct info
{
	string name;

	int ID;
	int Age;
	double marks[5];
};
void input(info student[], int N);
void output(info student[], int N);
void _14(info student[], int N, int number);
void even_ID(info student[], int N);
void info_student(info student[], int N, int numberID);
void first(info student[], int N);

int main()
{
	info student[2];
	int numberID;


	input(student, 2);

	output(student, 2);

	_14(student, 2, 14);

	even_ID(student, 2);

	cout << "Enter the ID you want to search for ...";
	cin >> numberID;
	info_student(student, 2, numberID);

	first(student, 2);


	return 0;
}

void input(info student[], int N)
{
	for (int i = 0; i < N; i++)
	{
		cout << "Enter name of student " << i + 1 << " ... ";
		cin >> student[i].name;

		cout << "\nEnter ID of student " << i + 1 << " ... ";
		cin >> student[i].ID;

		cout << "\nEnter Age of student " << i + 1 << " ... ";
		cin >> student[i].Age;

		cout << "\nEnter Marks of student" << i + 1 << " ... ";
		for (int j = 0; j < 5; j++)
		{
			cout << "\nThe Mark " << j + 1 << " ... ";
			cin >> student[i].marks[j];
		}

		cout << "\n\n";
	}

	cout << "--------------------------------\n";
}
void output(info student[], int N)
{
	for (int i = 0; i < N; i++)
	{
		cout << "the name student " << i + 1 << ": " << student[i].name << "\nthe ID : " << student[i].ID << "\nthe age : " << student[i].Age << "\n";

		for (int j = 0; j < 5; j++)
			cout << "mark " << j + 1 << " : " << student[i].marks[j] << "\n";

		cout << "\n";
	}

	cout << "--------------------------------\n";
}
void _14(info student[], int N, int number)
{
	bool T = false;
	for (int i = 0; i < N; i++)
	{
		if (student[i].Age == 14)
		{
			cout << "student" << i + 1 << ":" << student[i].name << " have 14 yeas\n";
			T = true;
		}
	}

	if (!T)
		cout << "No student is 14 years old.";

	cout << "\n--------------------------------\n";
}
void even_ID(info student[], int N)
{
	bool T = false;

	for (int i = 0; i < N; i++)
	{
		if (student[i].ID % 2 == 0)
		{
			cout << "student " << i + 1 << " : " << student[i].name << " has ID even\n";
			T = true;
		}
	}

	if (!T)
		cout << "There is no student with even ID.";

	cout << "\n--------------------------------\n";
}
void info_student(info student[], int N, int numberID)
{
	bool T = false;
	for (int i = 0; i < N; i++)
	{
		if (student[i].ID == numberID)
		{
			T = true;
			cout << "\nthe name student :" << student[i].name <<
				"\nthe ID student :" << student[i].ID << "\nthe age student :" << student[i].Age << "\n";

			for (int j = 0; j < 5; j++)
				cout << "mark " << j + 1 << " : " << student[i].marks[j] << "\n";

			break;
		}
	}

	if (!T)
		cout << "There is no student with this ID.\n";

	cout << "\n--------------------------------\n";

}
void first(info student[], int N)
{

	for (int i = 0; i < 5; i++)
	{
		string name;
		int MAX = INT_MIN;

		for (int j = 0; j < N; j++)
		{
			if (student[j].marks[i] > MAX)
			{
				name = student[j].name;
				MAX = student[j].marks[i];
			}
		}

		cout << "The highest student in the Mark " << i + 1 << " is " << name << "\n";
	}
}
