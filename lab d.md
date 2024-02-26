Q1. Good streaming operator
Question:

Solution:

Test data:

Sample output:

Reflection:

Metadata:

Further information:

# Week 4 - Lab D
## Q1. Linker errors
### Question

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
