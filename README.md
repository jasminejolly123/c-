# c++
## Q1
```cpp
int main (int argc, char **argv) {
   cout << "Hello World" << endl;
   return 0;
}
```

## Q2
``` cpp
int main(int argc, char** argv) 
{
	float tempf = 0;
	float tempc = 0;
	cout << "Enter temp" << endl;
	cin >> tempf;
	tempc = 5.0 / 9.0 * (tempf - 32);
	cout << tempc;
	return 0;
}
```

## Q3
``` cpp
int main(int argc, char** argv) 
{
	int intsize = 0;
	int charsize = 0;
	int floatsize = 0;
	int shortsize = 0;
	int longsize = 0;
	
	intsize = sizeof(int);
	charsize = sizeof(char);
	floatsize = sizeof(float);
	shortsize = sizeof(short);
	longsize = sizeof(long);

	cout << intsize << charsize << floatsize << shortsize << longsize << endl;
	return 0;
}
```

## Q4
``` cpp
int main(int argc, char** argv) 
{
	const double x = 100000.123456789;
	const double a = 200000.123456789;
	double y = (x + a) / x;
	double z = 1.0 + (a / x);
	if (y == z)
		cout << "y and z are identical" << endl;
	return 0;
}
```
## Q5
```cpp
int main(int argc, char** argv)
{
    int factorialNumber = 5;
    int factorialTotal = 1;

    for (int n = 2; n <= factorialNumber; ++n)
    {
        factorialTotal *= n;
    }

    cout << factorialTotal;
}
```

## Q6
```cpp
int main(int argc, char** argv) 
{
	float n = 0;
	float m = 0;
	int i = 1;

	while (n >= 0)
	{
		cout << "Please enter an int value, then press Enter" << endl;
		cin >> n;
		if (n >= 0) 
		{
			m = m + n;
			m = m / i;
			i++;
		}
	}

	cout << m;
	return 0;
}
```
