# Summer Summary

## Computer Enviroment Setup

On my first day I was asked to run a simple hello world world program using just the terminal to understand how the complier functions.

I then installed Visual studio tools, CMake, Ninja, and conan. Visual studio gave me a better user interface to code for a cleaner work enviroment by giving me the tools to edit the visual appearance of my workspace, giving me easy access to github and giving me tools to read and go between my code, CMake is a cross-platform tool that helps manage the build process of software projects. It is primarily used to generate build files for different platforms and compilers, making it easier to compile and link code across various environments. For my situation CMake helped me link my classes to diffrent main programs and utilize the build system ninja which takes source code and outputs executables.

After initializing my enviroment I was introduced to github, at the beginning I was using gitbash to upload my code and learned the proper commands to upload, push, pull and other nessarcy commands. GitHub is a very useful tool to work on projects with, as you can organize your code, share your code, and organize it in a manner such that your team can edit and show where to make changes and organize a project 

## OOP(Object Oriented Programming)

One of the first concepts that I learned was Object Oriented Programming or OOP for short. This is a very important concept and the core of the projects that I have created during this semester.

In OOP, you are focused on creating an object and basing things around it. For example, if you have a car, a car is an object but it has certain specifications like year and make. In C++, you can define this by using a class and then you name your class. For example, `class car` and then inside this class, you can create member variables that are part of this class, for example, `make`, and `year`.
```cpp
// Class and Objects
class Car {
    public:
        string make;
        int year;
};

int main(){

Car car1;
car1.make = "BMW";
car1.year = 2020;

return 0;

}
```
## Access Specifiers
In C++, when you create a class, you have something called access specifiers. These are basically telling C++ if you can access that certain type of information outside of that specified class. This is important to keep certain information secure, access modifiers make software less error prone.
```cpp
// Member Functions
class Car {
    public:
        string make;
        int year;
        void print() {
            cout << "This is a " << make << " from " << year << endl;
        }
};
```

## Objects
Now that a class is defined in our example "car", objects are individual instances of classes. For example, we defined our class as "car" and members as "make" and "year". Now we can create an object like so `car car1;` now we can access the members by doing so `car1.make= "BMW";` now we accessed a member variable and assigned the value of BMW to it. We can create as many objects as we want, you can picture it as a house being built from a blueprint.

## Member Functions
Now that we have defined that we can create as many objects from our class as we want, we can simplify this and create something called member functions. For example, instead of typing out `cout << "This is a" << car1.year << car1.year << endl;`, you can make a function like `void print () { << "This is a" << year << year << endl;} };` these eliminate repetition and help clean out code, you can create any type of function that you may need it does not need to be a print function. Another way to refer to functions in OOP is methods.

## Constructors
There is a special type of member function in OOP and they are called constructors. These are called when an object is created. These will do the setup work of an object and will initialize the member variables.
```cpp
// Constructors
class Car {
    public:
        string make;
        int year;
        Car(string x, int y) {
            make = x;
            year = y;
        }
};
```

## Encapsulation
In OOP, there is something called encapsulation. This is basically where you manipulate private and public access specifiers to have better control of your data. Let's say you run a company and you create a class called employee. You can set the salary to private and create specific public functions to get and display the salary. This better controls your data, because you (or others) can change one part of the code without affecting other parts.

// Encapsulation
```cpp
class Employee {
    private:
        double salary;
    public:
        Employee(double s) {
            salary = s;
        }
        double getSalary() const {
            return salary;
        }
};

int main() {
    Employee emp1(50000);
    std::cout << emp1.getSalary() << std::endl;

    return 0;
}
```

## Inheritance
In OOP, there is a concept called inheritance. Inheritance allows one class to inherit the variables and member functions from another class. Inheritance prevents code duplication. This leads to more maintainable software. C++ also allows multi-level inheritance. This means a derived class can be a base class. Furthermore you can add a concept called virtual what this does is adds a pointer to the class that holds a refreence to the implementing class(child). Down below is the syntax to properly write a virtual class, which creates a parent class(gym).
```cpp
// Inheritance
class Vehicle {
    public:
        string make;
        int year;
};

class Car : public Vehicle {
    public:
        int doors;
};

int main(){

Car car1;
car1.make = "BMW";
car1.year = 2020;
car1.doors = 4;

return 0;

}

// Virtual Classes
#ifndef __INHERITANCE__GYM__HPP__
#define __INHERITANCE__GYM__HPP__

class Gym { //creates the base class gym 

public:
    virtual double cardio() const = 0;  // returns the percentage by which the weight will increase
    virtual double lift() const   = 0;  // returns the percentage by which the weight will increase
};

#endif
```

## Polymorphism
With inheritance comes a concept called polymorphism. This allows you to use your derived class anywhere in your code that we can use your base class.
```cpp
// Polymorphism
class Vehicle {
    public:
        virtual void honk() {
            cout << "Beep!" << endl;
        }
};

class Car : public Vehicle {
    public:
        void honk() override {
            cout << "Honk!" << endl;
        }
};

int main(){

Vehicle* vehicle1 = new Car();
vehicle1->honk();

return 0;

}
```
## Pointers:

Pointers are as simple as they sound: they are variables pointing at a memory address. Pointers are extremely useful and powerful because they allow you to access a variable or function without actually having to call it. You can call the value stored in the memory address a pointer is pointing at by something called dereferencing. This allows you to access the actual value stored at the pointed memory address.

## Linked Lists:

Linked lists are closely tied with pointers and utilize their benefits. This is displayed by the structure of linked lists. A linked list is made up of nodes, where each node contains a value and a pointer to the next node in the list. The last node points to a null value, indicating the end of the list. From this, you could wonder what is the difference between this and an array. The difference between the two is that linked lists are dynamic in size, meaning that if you wanted to add or remove a node, you simply just change the order of the pointers and make sure your last value points to null. This makes it extremely useful when it comes to structuring your data. One thing to note is tat you have to traverse to your desired node meaning traversing through the entire list until you reach your desired spot.

## Doubly Linked List

A doubly linked list is an extension of the linked list that enhances its functionality by giving an additional pointer. In a singly linked list, each node contains a pointer to the next node, but in a doubly linked list, each node contains two pointers one pointing to the next node and another pointing to the previous node. This link allows for more flexible traverse of the list, as you can move both forwards and backwards through the list. Additionaly, I was able to implement a "delete" from back function that deletes nodes from the back being made possible by a tail pointer. 

## Jaged Arrays
During the term, I also learned about jagged arrays and how to handle them in C++. A jagged array is an array of arrays where the inner arrays can have different lengths. This structure is useful when dealing with data that naturally varies in size, such as rows of data with varying numbers of elements.

I worked on changing C code to C++ to manage jagged arrays using linked lists. This involved creating custom classes to represent rows and the overall array, allowing for dynamic memory allocation. By processing input data into a 2D array format, I gained experience in managing data structures, enhancing my understanding of dynamic memory and data organization in C++.

## Multithreading

## Threads
Multithreading allows you to use the power of multiple CPU threads. While CPUs typically start from a single thread, you can split tasks effectively by creating additional threads. This approach speeds up programs and allows quicker task switching between threads.

## Mutexes
When threads access a shared variable and make changes to it, that moment is called a critical point. Shared variables are important, but improper use can lead to program crashes. This is where Mutexes (short for “mutual exclusions”) come in. They are hardcoded into the software to ensure atomicity—an action that either happens completely or not at all. In other words, mutexes allow you to modify critical points without interruption from other threads. This is very useful in applications where atomic processes are essential.


## TCP Client and Server

## TCP Client
The TCP client, implemented in the NetworkClient class, performs the following steps:

Initialization:

The client initializes Winsock using WSAStartup, which prepares the underlying network system for communication.
It sets up the server address and port to which it will connect.
Connection:

The client creates a socket using socket(), specifying the AF_INET address family (IPv4), SOCK_STREAM socket type (TCP), and IPPROTO_TCP protocol.
It then attempts to connect to the server using the connect() function, specifying the server's IP address and port.
Data Transmission:

The client can send data to the server using the sendData() method, which uses the send() function to transmit data over the established connection.
The client can receive data from the server using the recvData() method, which uses the recv() function to read data from the socket into a buffer.
Disconnection:

The client can close the connection using the closeConnection() method, which closes the socket and cleans up resources.
```cpp
#ifndef NETWORKCLIENT_HPP
#define NETWORKCLIENT_HPP

#include <string>
#include <windows.h>

namespace MyNetwork {

    constexpr int DEFAULT_BUFLEN = 512;

    class NetworkClient {

    public:
        NetworkClient( const std::string & serverAddress, uint16_t port );
        ~NetworkClient();

        bool        openConnection();
        bool        sendData( std::string & data );
        std::string recvData( int bufferSize );

        std::string serverAddress;
        uint16_t    port;
        SOCKET      connectSocket;
        WSADATA     wsaData;

        void closeConnection();
    };

}  // namespace MyNetwork

#endif
```

## TCP Server
The TCP server, implemented in the NetworkServer class, performs the following steps:

Initialization:

The server initializes Winsock using WSAStartup, preparing the network environment for communication.
It sets the port number on which the server will listen for incoming client connections.
Starting the Server:

The server creates a listening socket using socket(), specifying the AF_INET address family (IPv4), SOCK_STREAM socket type (TCP), and IPPROTO_TCP protocol.
It binds the socket to an IP address and port using bind(), associating the socket with the server's address and port.
The server starts listening for incoming connections using the listen() function.
Handling Client Connections:

The server enters a loop, accepting incoming client connections using the accept() function.
For each accepted connection, the server handles the communication with the client in the handleClient() method, where it can receive data from the client using recv() and send data back using send().
Stopping the Server:

The server can be stopped by closing the listening socket using the closeServer() method, which cleans up resources and ensures that the socket is properly closed.
```cpp
#include <Windows.h>
#include <client.hpp>
#include <iostream>

MyNetwork::NetworkClient::NetworkClient( const std::string & serverAddress, uint16_t port ) :
    serverAddress( serverAddress ), port( port ), connectSocket( INVALID_SOCKET )
{
    // Initialize Winsock
    int result = WSAStartup( MAKEWORD( 2, 2 ), &wsaData );
    if ( result != NO_ERROR ) {
        std::cerr << "WSAStartup failed with error: " << result << std::endl;
        throw std::runtime_error( "WSAStartup failed" );
    }
}

MyNetwork::NetworkClient::~NetworkClient() { closeConnection(); }

bool MyNetwork::NetworkClient::openConnection()
{

    connectSocket = socket( AF_INET, SOCK_STREAM, IPPROTO_TCP );
    if ( connectSocket == INVALID_SOCKET ) {
        std::cout << "socket function failed with error: " << WSAGetLastError() << std::endl;
        return false;
    }

    sockaddr_in clientService;
    clientService.sin_family = AF_INET;
    clientService.sin_addr.s_addr = inet_addr("192.168.55.49");
    clientService.sin_port = htons( port );

    int result = connect( connectSocket, (SOCKADDR *)&clientService, sizeof( clientService ) );
    if ( result == SOCKET_ERROR ) {
        std::cerr << "Connect function failed with error: " << WSAGetLastError() << std::endl;
        closeConnection();
        return false;
    }

    return true;
}

bool MyNetwork::NetworkClient::sendData( std::string & data )
{
    int result = send( connectSocket, data.c_str(), (int)data.length() + 1, 0 );
    if ( result == SOCKET_ERROR ) {
        std::cerr << "Send failed with error: " << WSAGetLastError() << std::endl;
        return false;
    }
    return true;
}

std::string MyNetwork::NetworkClient::recvData( int bufferSize )
{
    std::string recvStr( bufferSize, '\0' );
    int         result = recv( connectSocket, &recvStr[0], bufferSize, 0 );

    if ( result > 0 ) {
        recvStr.resize( result );
        return recvStr;
    }
    else if ( result == 0 ) {
        std::cout << "Connection closed" << std::endl;
    }
    else {
        std::cerr << "Recv failed with error: " << WSAGetLastError() << std::endl;
    }

    return "";
}

void MyNetwork::NetworkClient::closeConnection()
{
    if ( connectSocket != INVALID_SOCKET ) {
        closesocket( connectSocket );
        connectSocket = INVALID_SOCKET;
    }
}
```
## Summary 
In conclusion, I gained a deeper understanding of computer science concepts and hands-on experience with various programming tools and techniques. I began by setting up my development environment, which laid the foundation for all subsequent learning. Through Object-Oriented Programming (OOP), I learned how to design and organize code efficiently, which was essential for the more complex projects I undertook, such as implementing linked lists and TCP server-client communication.

Next, I explored pointers, another fundamental concept, and applied them in creating linked lists and doubly linked lists. I then moved on to multithreading, where I learned how to optimize the use of CPU cores to speed up my programs. This included understanding mutexes, which are crucial for ensuring that critical points in the code are modified without interruption from other threads.

Finally, I learned how servers operate over the internet and successfully created my own server to send messages back and forth. Overall, I gained a lot of important and useful knowledge this term and look forward to continuing my learning with these new skills I've acquired.






