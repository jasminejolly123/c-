# Week 4 - Lab D
## Q1. Linker errors
### Question
Add source code for constructor and destructor
### Solution
```cpp
class Grid
{
public:
	Grid();
	~Grid();

	void LoadGrid(const char filename[]);
	void SaveGrid(const char filename[]);

private:
	int m_grid[9][9];
};
```
Here is the code in the Grid.h file. It holds the 2D array for the grid and the functions for loading and saving the grid.

![lab d q1 errors ](https://github.com/jasminejolly123/c-/assets/114992186/716c9879-7270-4f35-b887-8a12fa9f0ac1)
This is where errors are displayed because there's no source code for the constructor or destructor

```cpp
Grid::Grid()
{
}

Grid::~Grid()
{
}
```
This is all thats needed to be added to the Grid.cpp file for the code to run as the load and save functions are currently commented out in main.cpp.

![lab d q1 no errors](https://github.com/jasminejolly123/c-/assets/114992186/352f4f1d-074f-4fbe-8836-975c7c44ecd9)
Here there are no errors acter adding the previous code

### Reflection
source code needs to be added for all constructors, destructors and functions to run.

## Q2. Reading into Grid class
### Question
Turn the puesdocode into working c++

### Solution
```cpp
int main(int argn, char* argv[])
{
	Grid grid;
	grid.LoadGrid("Grid1.txt");
	grid.SaveGrid("OutGrid.txt");

	system("pause");
}
```
After adding the load and save grid an error appears
![lab d q2 errors](https://github.com/jasminejolly123/c-/assets/114992186/8c1bd471-82b8-43ea-81b0-591af921827a)
This is because there is no code to load or save the grid.

```cpp
void Grid::LoadGrid(const char filename[])
{
	ifstream file;
	for (int i = 0; i < 9; i++)
	{
		for (int j = 0; j < 9; i++)
		{
			file >> m_grid[i][j];
		}
	}
	file.close();
}
```
This is the code I wrote to load values from the input file into the grid
![lab d q2 unexpected errors](https://github.com/jasminejolly123/c-/assets/114992186/986a413a-3654-4978-a437-50b7807821d9)
I got an error after adding this code, I couldn't figure out what the cause of this was

### Reflection
The Grid.cpp holds all definitions and source code. Using >> code an be transfered from file to variable.

## Q3. Saving the grid
### Question
Write code to save the grid into a text file

### Solution
```cpp
void Grid::SaveGrid(const char filename[])
{
	ofstream Grid2;
	for (int i = 0; i < 9; i++)
	{
		for (int j = 0; j < 9; i++)
		{
			Grid2 << m_grid[i][j];
		}
		Grid2 << endl;
	}
	Grid2.close();
}
```
This is my code to save the grid, I added an end line between the nested loops to maintain the grid structure.

### Reflection
Because of the error after adding the load grid code i could not see whether this code worked. I wrote code similar to the load grid code but used an output file instead of an input file and used << instead of >> as the data was being taken from the grid rather than being put into the grid.

## Q4. Pointers - Basics
### Question
Use the pointer to change the value of a

### Solution
```cpp
void functionA() {
	int a = 10;
	int b = 20;
	int *p = &a;

	cout << "a= " << a << endl;
	cout << "b= " << b << endl;

	*p = 100;

	cout << "a= " << a << endl;
	cout << "b= " << b << endl;
}
```

### Sample output
![lab d q4 assigning a result](https://github.com/jasminejolly123/c-/assets/114992186/81219f6c-dd2f-4cdb-b0fb-02d19d54c87e)

### Reflection
By using the pointer with the asterisk you can change the value of a varible without using the varible

## Q5. Pointers - False assumptions
### Question 
Try advancing the pointer

### Solution
```cpp
void functionB() {
	int a = 10;
	int b = 20;
	int c = 30;
	int *p = &b;

	cout << "a= " << a << endl;
	cout << "b= " << b << endl;
	cout << "c= " << c << endl;

	*p = 100;
	p++;
	*p = 200;

	cout << "a= " << a << endl;
	cout << "b= " << b << endl;
	cout << "c= " << c << endl;
}
```

### Sample output
![lab d q5 exception](https://github.com/jasminejolly123/c-/assets/114992186/9ef04b1b-1b58-437d-a69f-d96a6becb9e8)
An exception is thrown

### Reflection
The assumption would be that after incrementing p the pointer would now be pointing at c, but instead an exception is thrown. The memory location the pointer is now pointing to is invalid this is because although c is defined directly b that doesn't mean the memory location will be directly after b.

## Q6. Pointers - The crash
### Question
Why does the program crash

### Solution
```cpp
void functionC() {
	unsigned int a = 0x00ff00ff;
	unsigned int *p = (unsigned int *)a;

	*p = 999;
}
```
### Sample output
![lab d q6 exception](https://github.com/jasminejolly123/c-/assets/114992186/06ab36be-258d-4102-9b9e-f75827c1b9c2)

### Reflection
999 isn't a valid memory location so the program crashes.

## Q7.Pointers - Pointers to pointers
### Question
Change a value using a chain of pointers

### Solution
```cpp
void functionD() {
	double x = 3.14;
	double *q = &x;
	double **p = &q;

	cout << "x= " << x << endl;

	**p = 50.0;

	cout << "x= " << x << endl;
}
```

### Sample output
x= 3.14
x= 50.0

### Reflection
With each pointer added on a chain another asterisk needs to be added and any value can be changed from the end of the chain.
