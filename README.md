# STL
- [vector](#vector)
- [list](#list)
- [map](#map)
- [set](#set)

# set
A set is part of the Standard Template Library (STL) and represents a collection of unique elements that are sorted automatically. 
It allows for efficient insertion, deletion, and search operations.

## syntax
```cpp
std::set<int> mySet;               // declare a  set of integers
std::set<std::string> myStringSet; // declare a set of strings

std::set<int> mySet = {1, 2, 3, 4, 5};  //initialize a set

mySet.insert(6); // Adds 6 to the set
mySet.insert(3); // This will not add 3, since it already exists

mySet.erase(2); // Removes the element 2 from the set
```
checking for existence
```cpp
if (mySet.find(3) != mySet.end()) {
    std::cout << "3 is in the set." << std::endl;
} else {
    std::cout << "3 is not in the set." << std::endl;
}
```
### Example
```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> mySet;

    // Adding elements
    mySet.insert(3);
    mySet.insert(1);
    mySet.insert(4);
    mySet.insert(1); // Duplicate, will not be added

    // Iterating over the set
    std::cout << "Elements in the set: ";
    for (const auto& element : mySet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    // Removing an element
    mySet.erase(1);
    std::cout << "After removing 1: ";
    for (const auto& element : mySet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    // Checking for existence
    if (mySet.find(3) != mySet.end()) {
        std::cout << "3 is in the set." << std::endl;
    } else {
        std::cout << "3 is not in the set." << std::endl;
    }

    return 0;
}
```





________________________________________________________________________________________________________________________________________________
# map
A map is part of the Standard Template Library (STL) and provides a sorted associative container that stores elements in key-value pairs. 
Each key must be unique, and the map automatically sorts the keys.

### syntax
```cpp

std::map<int, std::string> myMap; // declaring a map with integer keys and string values
std::map<std::string, int> ageMap; // declaring a map with string keys and integer values

std::map<std::string, int> ageMap = {   //Initializing a Map
    {"Alice", 30},
    {"Bob", 25},
    {"Charlie", 35}
};

myMap[1] = "One";          // assing an element using []
myMap.insert({2, "Two"});  // Using insert()

myMap.erase(1); // Removes the element with key 1
```

### Example
```cpp

#include <iostream>
#include <map>

int main() {
    std::map<std::string, int> ageMap;

    // Adding elements
    ageMap["Alice"] = 30;
    ageMap["Bob"] = 25;
    ageMap["Charlie"] = 35;

    // Accessing elements
    std::cout << "Alice's age: " << ageMap["Alice"] << std::endl;

    // Iterating over the map
    std::cout << "All ages:\n";
    for (const auto& pair : ageMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    // Removing an element
    ageMap.erase("Bob");

    std::cout << "After removing Bob:\n";
    for (const auto& pair : ageMap) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    return 0;
}
````

_________________________________________________________________________________________________________________________________________________________________________________________________________
# list
 list is part of the Standard Template Library (STL) and represents a doubly linked list. 
 It allows for efficient insertion and removal of elements from any position, but accessing elements by index is less 
 efficient compared to vectors.

 ```cpp
#include <list>

std::list<int> numbers; // A list of integers
std::list<std::string> names; // A list of strings
std::list<int> numbers(5, 0); // A list of 5 integers, all initialized to 0
numbers.push_back(10); // Add to the end
numbers.push_front(5); // Add to the front

numbers.pop_back(); // Removes the last element
numbers.pop_front(); // Removes the first element
numbers.remove(10); // Removes all occurrences of 10
```
### example 
```cpp
#include <iostream>
#include <list>

int main() {
    std::list<int> numbers;

    // Adding elements
    numbers.push_back(10);
    numbers.push_back(20);
    numbers.push_front(5);

    // Iterating over the list
    std::cout << "Numbers: ";
    for (int number : numbers) {
        std::cout << number << " ";
    }
    std::cout << std::endl;

    // Removing an element
    numbers.remove(10);

    std::cout << "After removing 10, numbers: ";
    for (int number : numbers) {
        std::cout << number << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
### Note
Lists are useful when you need frequent insertions and deletions from anywhere in the container.
However, if you need to access elements by index frequently, consider using vectors instead, as they provide better performance for random access.
______________________________________________________________________________________________________________________________________________________________________________________________________________
# vector
 vector is part of the Standard Template Library (STL) and provides a dynamic array that can grow and shrink in size. 
 It allows you to store elements and provides many useful member functions to manipulate the data.

```cpp
#include <vector>
std::vector<int> numbers; // A vector of integers
std::vector<double> prices; // A vector of doubles
std::vector<std::string> names; // A vector of strings

std::vector<int> numbers(10, 0); // A vector of 10 integers, all initialized to 0
```
### Adding elements
```cpp
numbers.push_back(1);
numbers.push_back(2);
int first = numbers[0];      // accessing elements using []
int second = numbers.at(1);  // Using at()
```
### Example Code
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers;

    // Adding elements
    numbers.push_back(10);
    numbers.push_back(20);
    numbers.push_back(30);

    // Accessing elements
    std::cout << "First number: " << numbers[0] << std::endl;

    // Iterating over the vector
    std::cout << "All numbers: ";
    for (int number : numbers) {
        std::cout << number << " ";
    }
    std::cout << std::endl;

    // Removing the last element
    numbers.pop_back();

    std::cout << "After popping back, numbers: ";
    for (int number : numbers) {
        std::cout << number << " ";
    }
    std::cout << std::endl;
    return 0;
}
```
______________________________________________________________________________________________________________________________________________________________________________________________________________

