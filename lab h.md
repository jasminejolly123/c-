# lab H
## Q1 Person Node
``` cpp
	void setName(string name)
	{
		m_name = name;
	}

	void setAge(int age)
	{
		m_age = age;
	}

	string getName()
	{
		return m_name;
	}

	int getAge()
	{
		return m_age;
	}
```
Here I wrote get and set functions for the name and age

``` cpp
friend AddressBookSLL;
```
Here I made the address book friends with the person node class this is so the address book class has access to private members of person node

## Q2 Address Book
``` cpp
void AddressBookSLL::AddPerson(const string& name, int age)
{
	if (m_head == nullptr)
	{
		m_head = new PersonNode(name, age);
	}
	else if (m_next != nullptr)
	{
		m_next = new PersonNode(name, age);
	}
}
```
Here I added functionality to the add person method.
I had a problem understanding the instructions so I made it so if the list was empty the new person would be added to the top of the list and otherwise added to the next item in the list.
This code did not run as the code could not find the m_next variable, I think this is due to a problem with my friend declaration.

## Q3 Find, Delete and Output
``` cpp
const int AddressBookSLL::FindPerson(const string& name)
{
	bool find = false;
	for (string : book)
	{
		if (PersonNode::m_name == name)
		{
			return PersonNode;
			find = true;
		}
	}
	if (find == false)
	{
		return nullptr;
	}
}
```
This is the code for the "find person" method, because of the problen with my friend declaration I couldn't run this code I also had multiple errors cone up similar to the ones from the previous question.
I did a for loop to run through each member of the list and checked each item against the input from the parameters. I used a boolean variable to check whether a match was found.

``` cpp
bool AddressBookSLL::DeletePerson(const string& name)
{
	bool del = false;
	PersonNode* current = m_head;
	for (string : book)
	{
		if (PersonNode::m_name == name)
		{
			delete current;
			return true;
		}
	}
	if (del == false)
	{
		return false;
	}
}
```
This is the code for the "delete person" method, I also could not run this code and struggled with how to code this anyway. I wrote what I thought might work.
I again did a for loop to go through each item in the list and when finding a match instaed of outputting that person node I outputted true, and if none was found false was outputted.

``` cpp
void AddressBookSLL::Save(const char filename[])
{
	ofstream file;
	for (string : book)
	{
		file << PersonNode[0, 1];
	}
}
```
This is the code to save all items in the list into a readable file.
I made an output file then went through each item in the list outputting it into the file.
