# Sqlite template for c++

#### Back Story
When i was looking for database for my project. i was thinking to implement Mysql and i found out it was quite hard to setup and use in c++.\
Then i found sqlite for c++ article i read about it and i came up with this template.
> I Will try to create step by step tutorial about it. 

### This template design for small projects only but you can modify a your need
I try to make things simple as possible.
- <b> db</b> : On this folder we will store all our databases 
- <b>sqlite </b> : this folder contains sqlite header file. 
> NOTE : You can move into header file folder if it is large projects and have lots of library
- <b> src</b> : It consists of all cpp files 
- <b> main.cpp</b> : here you write your codes.

#### Example Code
```c++
#include <iostream> 
#include "sqlite/sqlite3.h"

using namespace std;
  
int main() 
{ 
    // Pointer to SQLite connection
    sqlite3* db; 
    
    // Save the connection result
    int exit = 0;
    exit = sqlite3_open("db/example.db", &db); 
  
    // Test if there was an error
    if (exit) { 
        
        cout << "DB Open Error: " << sqlite3_errmsg(db) << endl; 
        
    } else {

        cout << "Opened Database Successfully!" << endl; 
    }
    
    // Close the connection
    sqlite3_close(db); 
    
    return (0); 
}
```
#### Then we have MakeFile
```MakeFile
compile:
		g++ main.cpp -o main -l sqlite3

		./main
```
### How to Run ?
 Open up your terminal and type following
 ```sh
 mingw32-make -f MakeFile
 ```

### Or we can use second option 
type following on terminal
```sh
g++ main.cpp -o main -l sqlite3
```
#### MakeFile make things lot easier  ** I recommend MakeFile ** 

Happy Coding 🙂 \
Keep Learning 📖 \

