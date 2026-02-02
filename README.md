# CPP-PROGRAMS
## QUESTION 1. Write a C++ program that: Declares one global variable
##  Declares one local variable inside main()
## Dynamically allocates one integer using new
## Print the addresses of all three and identify which memory region each belongs to.

###
``` c
#include <iostream>
using namespace std;

 // Global variable (stored in the global/static data segment)
int globalVar = 10;

int main() {
      Local variable inside main() (stored on the stack)
    int localVar = 20;

    //  Dynamically allocated integer (stored on the heap)
    int* heapVar = new int(30);

    // Printing addresses
    cout << "Address of global variable: " << &globalVar << endl;
    cout << "Memory region: Global / Data Segment" << endl << endl;

    cout << "Address of local variable:  " << &localVar << endl;
    cout << "Memory region: Stack" << endl << endl;

    cout << "Address of dynamically allocated variable: " << heapVar << endl;
    cout << "Memory region: Heap" << endl;

    // Free dynamically allocated memory
    delete heapVar;

    return 0;
}
```
###
output:
<img width="522" height="336" alt="Screenshot 2026-01-21 095814" src="https://github.com/user-attachments/assets/a3324f60-46a6-46d6-9bec-0103fc1274e9" />


# 2.

```c
#include <iostream>
using namespace std;

// Function that squares the value using a pointer
void square(int* p) {
    *p = (*p) * (*p);
}

int main() {
    int num = 5;        // normal integer variable
    int* ptr = &num;   // pointer storing address of num

    cout << "Before calling square():" << endl;
    cout << "Value of num: " << num << endl;
    cout << "Address of num: " << &num << endl;
    cout << "Value stored in pointer ptr: " << ptr << endl << endl;

    // Call function
    square(ptr);

    cout << "After calling square():" << endl;
    cout << "Value of num: " << num << endl;
    cout << "Address of num: " << &num << endl;
    cout << "Value stored in pointer ptr: " << ptr << endl;

    return 0;
}
```
OUTPUT:
<img width="438" height="457" alt="Screenshot 2026-01-21 100247" src="https://github.com/user-attachments/assets/c36d1d2f-ea70-4659-b026-ee4a7be2cba6" />

# 3.
```c
#include <iostream>
using namespace std;

int main() {
    int a = 10;        // First variable
    int* ptr = &a;    // Pointer stores address of a
    int b;             // Third variable (will store copied value)

    // Copy value using dereferencing
    b = *ptr;

    cout << "Value of a: " << a << endl;
    cout << "Address of a: " << &a << endl;
    cout << "Value stored in pointer ptr: " << ptr << endl;
    cout << "Value obtained by dereferencing ptr (*ptr): " << *ptr << endl;
    cout << "Value of b (copied value): " << b << endl;

    return 0;
}
```

OUTPUT:

<img width="472" height="283" alt="Screenshot 2026-01-21 100345" src="https://github.com/user-attachments/assets/2097c5f0-a05e-42a7-afb5-e24305426202" />

 # 4.

 ```c
 #include <iostream>
using namespace std;

int main() {
    int x = 5;
    int *p = &x;
    *p = 10;
    cout << x;
    return 0;
}
```

<img width="393" height="242" alt="Screenshot 2026-01-21 100858" src="https://github.com/user-attachments/assets/2e3606c2-25c8-4f27-8c10-6ac958509867" />

# 5. 
```c
#include <iostream>
using namespace std;

int main() {
    int a = 1, b = 2;
    int *p = &a;

    p = &b;    // pointer now points to b
    *p = 5;    // changes value of b

    cout << a << " " << b;

    return 0;
}
```

output:

<img width="425" height="245" alt="Screenshot 2026-01-21 101132" src="https://github.com/user-attachments/assets/5599c4e2-45c8-4343-8a5b-8163c692d282" />

# 6.
``` c
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    int *p = &x;
    int **pp = &p;

    **pp = 20;
    cout << x;

    return 0;
}
```
OUTPUT:


<img width="427" height="171" alt="Screenshot 2026-01-21 101632" src="https://github.com/user-attachments/assets/0a4d6806-d00e-4567-8b03-67934bf371ec" />


# 7. 
```c
#include <iostream>
using namespace std;

int main() {
    int a[5] = {2, 4, 6, 8, 10};
    int *p = a;

    cout << *p++ << " ";
    cout << *p;

    return 0;
}
```

OUTPUT:

<img width="407" height="281" alt="Screenshot 2026-01-21 101947" src="https://github.com/user-attachments/assets/a3f54fc3-4a69-4c1e-8292-4491b8629b4f" />

# 8 . 
```c
#include <iostream>
using namespace std;

// Function to swap values using pointers
void swap(int *a, int *b) {
    int temp;
    temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x, y;

    cout << "Enter two numbers: ";
    cin >> x >> y;

    cout << "Before swapping: " << endl;
    cout << "x = " << x << ", y = " << y << endl;

    // Call swap function
    swap(&x, &y);

    cout << "After swapping: " << endl;
    cout << "x = " << x << ", y = " << y << endl;

    return 0;
}
```
OUTPUT:



<img width="401" height="349" alt="Screenshot 2026-01-21 102115" src="https://github.com/user-attachments/assets/9d67a401-4182-4be3-90da-5cc217267764" />

# 9. 
```c
#include <iostream>
using namespace std;

int main() {
    // Create dynamic integer
    int *p = new int;

    // Assign value through pointer
    *p = 10;

    cout << "Value of dynamic integer: " << *p << endl;
    cout << "Address of dynamic integer: " << p << endl;

    // Modify value through pointer
    *p = 25;
    cout << "Modified value: " << *p << endl;

    // Free allocated memory
    delete p;

    return 0;
}
```
OUTPUT:

<img width="608" height="401" alt="Screenshot 2026-01-21 102401" src="https://github.com/user-attachments/assets/2feb8866-d001-4d2c-a681-56aba2e64593" />

# 10. 
```c
#include <iostream>
using namespace std;

int main() {
    int a[] = {1, 2, 3, 4, 5};
    int *p = a;

    cout << *p++ << " ";
    cout << (*p)++ << " ";
    cout << ++(*p) << " ";
    cout << *p << "\n";

    for (int i = 0; i < 5; i++)
        cout << a[i] << " ";

    return 0;
}
```



OUTPUT:

<img width="708" height="483" alt="Screenshot 2026-01-21 102805" src="https://github.com/user-attachments/assets/648cc390-f785-436d-84ce-488608bb8d24" />

# Ques
```
#include <iostream>
using namespace std;

int main() {
    int n;
    int arr[100];

    cout << "Enter the number of elements: ";
    cin >> n;

    cout << "Enter " << n << " elements:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    cout << "Array elements are:\n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```
# output. 
<img width="524" height="292" alt="image" src="https://github.com/user-attachments/assets/8608083a-401e-4b78-8407-0bfbc4fb4809" />

# QUES. Write a c++ program to find the sum of all elements in an array
```c
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    int arr[100];

    cout << "Enter the number of elements: ";
    cin >> n;

    cout << "Enter " << n << " elements:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
        sum += arr[i];   // add each element to sum
    }

    cout << "Sum of array elements = " << sum << endl;

    return 0;
}
```
# output
<img width="465" height="273" alt="image" src="https://github.com/user-attachments/assets/7263adf8-d508-4912-bf75-cbfa677d8b98" />

# Ques. write a c++ program  to copy one array into another
```c
#include <iostream>
using namespace std;

int main() {
    int n, a[50], b[50];

    cout << "Enter number of elements: ";
    cin >> n;

    cout << "Enter elements:\n";
    for (int i = 0; i < n; i++)
        cin >> a[i];

    // Copy array
    for (int i = 0; i < n; i++)
        b[i] = a[i];

    cout << "Copied array:\n";
    for (int i = 0; i < n; i++)
        cout << b[i] << " ";

    return 0;
}
```
# output
<img width="441" height="338" alt="image" src="https://github.com/user-attachments/assets/4b5b5114-8055-4699-9b2e-ad4a3cd91dd5" />

# Ques. write a c++ program to print array elements at even index
```c
#include <iostream>
using namespace std;

int main() {
    int n, a[50];

    cout << "Enter number of elements: ";
    cin >> n;

    cout << "Enter elements:\n";
    for (int i = 0; i < n; i++)
        cin >> a[i];

    cout << "Elements at even index:\n";
    for (int i = 0; i < n; i += 2)
        cout << a[i] << " ";

    return 0;
}
```
# Output
<img width="610" height="380" alt="image" src="https://github.com/user-attachments/assets/7912c861-bf1a-43db-a95a-0435793b01b6" />

# Ques write a c++ program to read and display a 2D array (matrix)

```c
#include <iostream>
using namespace std;

int main() {
    int r, c;
    int a[10][10];

    cout << "Enter number of rows and columns: ";
    cin >> r >> c;

    cout << "Enter matrix elements:\n";
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            cin >> a[i][j];
        }
    }

    cout << "Matrix is:\n";
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            cout << a[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

#  Output
<img width="393" height="285" alt="image" src="https://github.com/user-attachments/assets/70047ec4-cb94-4466-97aa-f25711ac5b67" />

---
# ques. 
```c
#include <iostream>
using namespace std;

int main() {
    int r, c;
    int matrix[10][10];

    cout << "Enter number of rows and columns: ";
    cin >> r >> c;

    cout << "Enter matrix elements:\n";
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            cin >> matrix[i][j];

    cout << "Matrix elements in row-wise order:\n";
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++)
            cout << matrix[i][j] << " ";
        cout << endl;
    }

    return 0;
}
```
<img width="514" height="434" alt="image" src="https://github.com/user-attachments/assets/59fab06b-5190-4d4e-9ba4-cbb262fa7073" />













