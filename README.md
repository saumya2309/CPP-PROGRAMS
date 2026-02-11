# CPP-PROGRAMS
### QUESTION 1. Write a C++ program that: Declares one global variable
###  Declares one local variable inside main()
### Dynamically allocates one integer using new
### Print the addresses of all three and identify which memory region each belongs to.

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


### 2.

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

### 3.
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

 ### 4.

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

### 5. 
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

### 6.
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


### 7. 
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

### 8 . 
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

### 9. 
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
## OUTPUT:

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

### Ques
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
## output. 
<img width="524" height="292" alt="image" src="https://github.com/user-attachments/assets/8608083a-401e-4b78-8407-0bfbc4fb4809" />

### QUES. Write a c++ program to find the sum of all elements in an array
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
## output
<img width="465" height="273" alt="image" src="https://github.com/user-attachments/assets/7263adf8-d508-4912-bf75-cbfa677d8b98" />

### Ques. write a c++ program  to copy one array into another
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

### Ques. write a c++ program to print array elements at even index
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
## Output
<img width="610" height="380" alt="image" src="https://github.com/user-attachments/assets/7912c861-bf1a-43db-a95a-0435793b01b6" />

### Ques write a c++ program to read and display a 2D array (matrix)

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

# # Output
<img width="393" height="285" alt="image" src="https://github.com/user-attachments/assets/70047ec4-cb94-4466-97aa-f25711ac5b67" />

---
### ques. 
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

### ques :create a structure STUDENT  with:

### input details of 5 students and display students who scored more than  75 marks.

```c
#include <stdio.h>

struct STUDENT {
    int roll;
    char name[50];
    float marks;
};

int main() {
    struct STUDENT s[5];
    int i;

    for(i = 0; i < 5; i++) {
        printf("Enter roll, name, marks: ");
        scanf("%d %s %f", &s[i].roll, s[i].name, &s[i].marks);
    }

    printf("\nStudents scoring more than 74:\n");
    for(i = 0; i < 5; i++) {
        if(s[i].marks > 74)
            printf("%d %s %.2f\n", s[i].roll, s[i].name, s[i].marks);
    }

    return 0;
}
```

<img width="505" height="482" alt="image" src="https://github.com/user-attachments/assets/7a343c78-0e5d-46ad-85db-7af27044a677" />

### ques: Define a structure Employee containing:
### employee ID ,name , basic salary

```c
#include <stdio.h>

struct Employee {
    int id;
    char name[50];
    float basic;
};

// Function to calculate gross salary
float grossSalary(float basic) {
    return basic + 0.2*basic + 0.1*basic; // basic + 20% HRA + 10% DA
}

int main() {
    int n;
    printf("Enter number of employees: ");
    scanf("%d", &n);

    struct Employee emp[n];

    // Input employee details
    for (int i = 0; i < n; i++) {
        printf("\nEmployee %d ID: ", i+1);
        scanf("%d", &emp[i].id);

        printf("Employee %d Name: ", i+1);
        scanf(" %[^\n]s", emp[i].name); // read full name with spaces

        printf("Employee %d Basic Salary: ", i+1);
        scanf("%f", &emp[i].basic);
    }

    // Display details and gross salary
    printf("\n--- Employee Details ---\n");
    for (int i = 0; i < n; i++) {
        printf("\nID: %d\nName: %s\nBasic: %.2f\nGross Salary: %.2f\n", 
                emp[i].id, emp[i].name, emp[i].basic, grossSalary(emp[i].basic));
    }

    return 0;
}
```
<img width="538" height="408" alt="image" src="https://github.com/user-attachments/assets/c4077a2a-aa51-4872-a80d-cf62c0372953" />


#### ques: int arr[] = {10, 20, 30, 40};
#### int *p = arr;
#### cout << *p << endl;
#### cout << *(p + 1) << endl;
#### cout << *(p + 3) << endl;
```c
#include <iostream>
using namespace std;

int main() {
    // Initialize an array
    int arr[] = {10, 20, 30, 40};
    
    // Pointer to the first element of the array
    int *p = arr;

    // Print values using the pointer
    cout << "*p = " << *p << endl;        // Points to arr[0]
    cout << "*(p+1) = " << *(p+1) << endl; // Points to arr[1]
    cout << "*(p+3) = " << *(p+3) << endl; // Points to arr[3]

    return 0;
}
```
<img width="469" height="475" alt="image" src="https://github.com/user-attachments/assets/433f9797-4a53-4e73-acb0-49ee8f9f1931" />

#### ques: int arr[] = {5, 10, 15, 20};
#### int *p = arr + 2;
#### cout << *p << endl;
#### cout << *(p - 1) << endl;
```c
#include <iostream>
using namespace std;

int main() {
    // Initialize array
    int arr[] = {5, 10, 15, 20};
    
    // Pointer to the 3rd element of the array (arr[2])
    int *p = arr + 2;

    // Print values using the pointer
    cout << "*p = " << *p << endl;        // Points to arr[2]
    cout << "*(p-1) = " << *(p-1) << endl; // Points to arr[1]

    return 0;
}
```

<img width="411" height="233" alt="image" src="https://github.com/user-attachments/assets/d1c8718b-fa5d-4dfe-8fef-fd0bef341a11" />

```

```
#### Ques:int arr[5] = {1, 2, 3, 4, 5};

#### for(int i = 0; i < 5; i++)
 ####   cout << *(arr + i) << " "; , 
 ```c
int arr[5] = {1, 2, 3, 4, 5};

for(int i = 0; i < 5; i++)
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {1, 2, 3, 4, 5};

    for(int i = 0; i < 5; i++)
        cout << *(arr + i) << " ";

    return 0;
}
```
<img width="529" height="272" alt="Screenshot 2026-02-05 185735" src="https://github.com/user-attachments/assets/cc9e0842-5576-495a-9590-346ce92cf7b2" />

```
```
#### Ques: int arr[] = {2, 4, 6, 8};
#### int *p = arr;
#### p++;
#### cout << *p << endl;

```c
#include <iostream>
using namespace std;

int main() {
    int arr[] = {2, 4, 6, 8};
    int *p = arr;

    p++;              // move pointer to next element
    cout << *p << endl;

    return 0;
}
```

<img width="718" height="278" alt="image" src="https://github.com/user-attachments/assets/d46af6f2-318c-4d7f-9819-8ad2ba6f966c" />


#### Ques:int arr[] = {7, 14, 21};
#### cout << arr[1] << endl;
#### cout << 1[arr] << endl;

```c
#include <iostream>
using namespace std;

int main() {
    int arr[] = {7, 14, 21};

    cout << arr[1] << endl;
    cout << 1[arr] << endl;

    return 0;
}


```

<img width="680" height="339" alt="image" src="https://github.com/user-attachments/assets/dc18c358-3333-4b91-b474-77e007f8e59c" />


```
```
#### Ques: int arr[] = {10, 20, 30};
#### int *p = arr;
#### cout << *p + 1 << endl;
#### cout << *(p + 1) << endl;

```c
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30};
    int *p = arr;

    cout << *p + 1 << endl;
    cout << *(p + 1) << endl;

    return 0;
}

```

<img width="812" height="327" alt="Screenshot 2026-02-05 190715" src="https://github.com/user-attachments/assets/7095af0d-0702-44c9-ab2a-f8f588b883ca" />

```
```
#### Ques: int arr[] = {3, 6, 9, 12};
#### int *p = arr;
#### while(p <= &arr[3]) {
####    cout << *p << " ";
####    p++;
#### }
```c
#include <iostream>
using namespace std;

int main() {
    int arr[] = {3, 6, 9, 12};
    int *p = arr;

    while(p <= &arr[3]) {
        cout << *p << " ";
        p++;
    }

    return 0;
}
```

<img width="489" height="212" alt="image" src="https://github.com/user-attachments/assets/7eaccf9b-b794-431a-9a43-bb0dcae8e92d" />
```
```
#### Ques:int arr[] = {1, 2, 3};
#### int *p = arr;

#### for(int i = 0; i < 3; i++)
####    cout << *(p++) << " ";

```c
#include <iostream>
using namespace std;

int main() {
    int arr[] = {1, 2, 3};
    int *p = arr;

    for(int i = 0; i < 3; i++)
        cout << *(p++) << " ";

    return 0;
}
```

<img width="450" height="149" alt="image" src="https://github.com/user-attachments/assets/4888835b-e009-4e2b-b5b7-f430cf3ee4cc" />

```
```
#### Ques:int arr[] = {10, 20, 30};
#### int *p = arr;
#### cout << p << endl;
#### cout << p + 1 << endl;

```c
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30};
    int *p = arr;

    cout << p << endl;
    cout << p + 1 << endl;

    return 0;
}
```

<img width="453" height="144" alt="image" src="https://github.com/user-attachments/assets/d1e54910-9bef-4219-a27c-cc59dd393101" />
```
```
#### Ques: char arr[] = {'A', 'B', 'C'};
#### char *p = arr;
#### cout << p << endl;
#### cout << p + 1 << endl;

```c
#include <iostream>
using namespace std;

int main() {
    char arr[] = {'A', 'B', 'C'};
    char *p = arr;

    cout << p << endl;
    cout << p + 1 << endl;

    return 0;
}
```


<img width="455" height="140" alt="image" src="https://github.com/user-attachments/assets/c120d185-9d33-4f4c-ad21-0cf9d1fdbe1b" />

```
```
#### Ques:struct Data {
####    int x;
####    int y;
#### };
#### Data arr[] = {{1,2}, {3,4}, {5,6}};
#### Data *p = arr;
#### cout << p->x << endl;
#### cout << (p + 1)->y << endl;
```c
#include <iostream>
using namespace std;

struct Data {
    int x;
    int y;
};

int main() {
    Data arr[] = {{1,2}, {3,4}, {5,6}};
    Data *p = arr;

    cout << p->x << endl;
    cout << (p + 1)->y << endl;

    return 0;
}
```

<img width="471" height="203" alt="image" src="https://github.com/user-attachments/assets/c3ecaf3c-28e7-4fde-9ec4-06eeda3ad317" />
```
```



#### Ques: struct Item {
####    int price;
##### };

#### Item arr[] = {100, 200, 300};
#### Item *p = arr;

#### cout << p[2].price << endl;
#### cout << (*(p + 1)).price << endl;
```c
#include <iostream>
using namespace std;

struct Item {
    int price;
};

int main() {
    Item arr[] = {100, 200, 300};
    Item *p = arr;

    cout << p[2].price << endl;
    cout << (*(p + 1)).price << endl;

    return 0;
}
```

<img width="617" height="215" alt="image" src="https://github.com/user-attachments/assets/3683d98f-c2db-4188-aa29-8ea1955dacca" />
```
```






















