# Week 3 - Lab C
## Q1. Passing command Arguments
### Question
Set input and output filenames as arguments
### Solution
![q1 2](https://github.com/jasminejolly123/c-/assets/114992186/70a12207-3674-4ef0-a1f8-8158e5806dbe)
### Sample output
Copy error
### Reflection
Once fileanmes are added to the command arguments the program can use the text files and not display an error message.

## Q2.Copying a textfile
### Question
Copy the contents of one text file into another
### Solution
```cpp
bool Copy(char filenamein[], char filenameout[])
{
	string contents;
  string contents2;
  ifstream file;
  fstream outfile ("output.txt", ios::out);
  file.open("input.txt", ios::in);
  file >> contents;
  outfile << contents;
  outfile >> contents2;

  if (contents == contents2)
	  return true;
  else
	  return false;
}

int main(int argn, char* argv[])
{
	if (argn != 3) {
		cerr << "Usage: " << argv[0] << " <input filename> <output filename>" << endl;
		int keypress; cin >> keypress;
		return -1;
	}

	if (Copy(argv[1], argv[2]))
	{
		cout << "Copy successful" << endl;
	}
	else
	{
		cout << "Copy error" << endl;
	}

	system("PAUSE");
}
```
### Sample output
Copy error
### Reflection
I tried reading the input file and writing the contents to the output file, this resulted in an error message. When adding a breakpoint I can see the contents of the input file are not correctly copied into the outfile file but I'm not sure why.

## Q3. Function call mechanism
### Questions
Explore assembly language within functions
### Solution
![Q3 1](https://github.com/jasminejolly123/c-/assets/114992186/729c37ce-053e-45b5-a86e-4872bfe0aa0a)
This is the code given in assembly language
![q3 2](https://github.com/jasminejolly123/c-/assets/114992186/e6229de4-5b6a-413d-8006-bf90a5c53a17)
This is the registers with the register values
![q3 3](https://github.com/jasminejolly123/c-/assets/114992186/4170e41b-4558-4220-bdf1-4883dd4d3fd1)
This shows the different memory locations of all the data, this is after putting the location of the stack pointer so this shows the stack
![q3 4](https://github.com/jasminejolly123/c-/assets/114992186/ef176080-cd83-4d65-95ad-49c08cc4db28)
This is the assembly language after adding another parameter and changing all the parameters to different data types. When moving to different memory locations you can see the double takes up more space than the other data types, the integer and float using 4 bytes and the doubles using 8 bytes, this is because doubles are a much larger data type than bth integers and floats.
### Sample output
a = 10, b = 20, c = 30
max = 30
### Reflection
Assembly language gives a lot more information than c++, showing mempry locations, contents of the stack and data sizes.




![image](https://github.com/jasminejolly123/c-/assets/114992186/7c328fcd-1963-4ecf-b615-2d20600993da)
