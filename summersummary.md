# Summer Summary

## Computer Enviroment Setup

On my first day I was asked to run a simple hello world world program using just the terminal to understand how the complier functions. 

I then installed Visual Studio tools, CMake, Ninja, and Conan. Visual Studio provided a better user interface, creating a cleaner work environment. It allowed me to customize the visual appearance of my workspace, access GitHub easily, and navigate between my code more efficiently.

CMake is a tool that manages the build process of software projects. It generates build files for various platforms and compilers, simplifying the process of compiling and linking code. In my case, CMake helped me link my classes to different main programs. Additionally, I used Ninja as the build system, which takes source code and produces executables.

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
In C++, when you define a class, you use access specifiers to control the visibility of its members. Access specifiers determine whether certain data or functions within the class can be accessed from outside the class. This is important for maintaining data security and ensuring that the software is less prone to errors, as it helps to enforce encapsulation and restrict unauthorized access to sensitive information, which could lead to bugs and crashes.
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
With the class "Car" now defined in our example, objects are the individual instances of that class. For example, we defined our class as "Car" with members like "make" and "year." To create an object, you can write Car car1;. This line of code creates an instance of the "Car" class named car1. You can then access and modify its member variables like this: car1.make = "BMW";. This assigns the value "BMW" to the make member of car1.

Objects are like houses built from a blueprint. The class is the blueprint, and each object is a distinct house with its own characteristics. You can create as many objects as you need, each with its own unique set of values.

## Member Functions
Now that we have defined that we can create as many objects from our class as we want, we can simplify this and create something called member functions. For example, instead of typing out `cout << "This is a" << car1.year << car1.year << endl;`, you can make a function like `void print () { << "This is a" << year << year << endl;} };` these eliminate repetition and help clean out code, you can create any type of function that you may need it does not need to be a print function. Another way to refer to functions in OOP is methods.

## Constructors
In object-oriented programming (OOP), constructors are a special type of member function that are automatically called when an object of a class is created. Constructors serve a crucial role in setting up an object by initializing its member variables with default or specified values. This ensures that the object is in a valid state from the moment it is instantiated.

Constructors can be overloaded, meaning you can define multiple constructors within a class, each with different parameters. This allows for flexibility in how objects are initialized. For instance, one constructor might initialize all member variables with default values, while another might allow you to pass specific values to customize the object's state right from the start.

Constructors don't have a return type, not even void, and they share the same name as the class they belong to. This makes them easily identifiable and essential to the object creation process. Without a constructor, an object would not have its member variables properly initialized, which could lead to unexpected behavior or errors in the program.
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
In object-oriented programming (OOP), inheritance is a concept that allows one class to inherit variables and member functions from another class. This means that a derived class can access and use the properties and methods of its base class, which helps to avoid code duplication and leads to more maintainable software.

C++ also supports multi-level inheritance, where a derived class can act as a base class for another class. This allows for a hierarchy of classes, each building on the functionality of the previous one.

Furthermore, C++ introduces the concept of virtual functions. By making a function virtual in the base class, you allow it to be overridden in a derived class. This is crucial for polymorphism, where the most derived version of the function is called, even if you're working with a pointer or reference to the base class. Essentially, a virtual function adds a pointer to the class that holds a reference to the implementing class (the child class).

This setup allows for flexible and modular code, where derived classes can provide specific implementations while still benefiting from the common functionality of their base classes.
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
With inheritance comes a powerful concept called polymorphism. Polymorphism allows objects of derived classes to be treated as objects of their base class. This means you can use a derived class wherever a base class is expected, enabling you to write more flexible and reusable code.

For example, if you have a base class Animal and derived classes like Dog and Cat, polymorphism allows you to create a list of Animal pointers or references that can hold Dog or Cat objects. Even though each object might be of a different derived class, you can call methods defined in the base class, and the appropriate derived class method will be executed. This is especially useful in scenarios where you want to write functions or algorithms that can operate on objects of different types but share a common interface.

Polymorphism in C++ is typically achieved through the use of virtual functions. When you declare a function as virtual in a base class, and override it in a derived class, the function call is resolved at runtime based on the actual type of the object, not the type of the reference or pointer. This allows for dynamic behavior in your programs, where the exact function that gets called depends on the specific object being used, even when accessed through a base class pointer or reference.

For instance, if you have a virtual function speak() in the Animal class and override it in Dog and Cat, a function expecting an Animal can call speak(), and the appropriate version will run depending on whether the object is a Dog or a Cat. This leads to highly extensible and modular code, where new derived classes can be added without modifying existing code.
```cpp
class Animal {
public:
    virtual void speak() {
        std::cout << "Animal speaks" << std::endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        std::cout << "Dog barks" << std::endl;
    }
};

class Cat : public Animal {
public:
    void speak() override {
        std::cout << "Cat meows" << std::endl;
    }
};

void makeAnimalSpeak(Animal* animal) {
    animal->speak();
}

int main() {
    Dog dog;
    Cat cat;

    makeAnimalSpeak(&dog);  
    makeAnimalSpeak(&cat);  
}
```
In this example, even though makeAnimalSpeak takes a pointer to the base class Animal, it correctly calls the speak() method of the derived classes Dog and Cat, thanks to polymorphism. This ability to interchange derived classes seamlessly wherever a base class is expected makes your code more flexible, easier to maintain, and more adaptable to change.

## Pointers:

Pointers are as simple as they sound: they are variables that point to a memory address. Pointers are extremely useful and powerful because they allow you to access a variable or function without actually calling it. You can access the value stored at the memory address a pointer is pointing to by a process called dereferencing. This allows you to access the actual value stored at the pointed-to memory address.

## Linked Lists:

Linked lists are closely tied to pointers and utilize their benefits. This is evident in the structure of linked lists. A linked list is made up of nodes, where each node contains a value and a pointer to the next node in the list. The last node points to a null value, indicating the end of the list. From this, you might wonder what the difference is between this and an array. The difference is that linked lists are dynamic in size, meaning that if you want to add or remove a node, you simply change the order of the pointers and ensure that the last value points to null. This makes linked lists extremely useful for structuring your data. One thing to note is that you have to traverse the entire list to reach your desired node, which means moving through each node until you reach the spot you want.

## Doubly Linked List

A doubly linked list is an extension of the linked list that enhances its functionality by adding an additional pointer. In a singly linked list, each node contains a pointer to the next node, but in a doubly linked list, each node contains two pointers: one pointing to the next node and another pointing to the previous node. This dual-link structure allows for more flexible traversal of the list, as you can move both forwards and backwards. Additionally, I was able to implement a "delete from back" function that removes nodes from the end of the list, made possible by a tail pointer.

## Jaged Arrays
During the term, I also learned about jagged arrays and how to handle them in C++. A jagged array is an array of arrays where the inner arrays can have different lengths. This structure is useful when dealing with data that naturally varies in size, such as rows of data with varying numbers of elements.

I worked on changing C code to C++ to manage jagged arrays using linked lists. This involved creating custom classes to represent rows and the overall array, allowing for dynamic memory allocation. By processing input data into a 2D array format, I gained experience in managing data structures, enhancing my understanding of dynamic memory and data organization in C++.

## Multithreading

## Threads
Multithreading lets you tap into the power of multiple CPU threads, which can really boost your program’s performance. While most CPUs start with just one thread, you can create additional threads to handle different tasks at the same time. This not only speeds up your program but also makes it easier to switch between tasks quickly.

By breaking a program into smaller, concurrent threads, you can make better use of modern multi-core processors, where each core can handle its own thread. This can lead to faster performance, especially for tasks that are heavy on computation or need to handle multiple operations at once, like processing real-time data or performing complex calculations.

Additionally, multithreading can make your applications more responsive by keeping the user interface interactive while background tasks are running. However, it does come with its own set of challenges, like managing thread synchronization to avoid issues such as race conditions and deadlocks. So while multithreading can be incredibly powerful, it requires careful handling to get the best results.

## Mutexes
When threads access and modify shared variables, you encounter what's known as a critical section. A critical section is a moment when a shared variable is being modified by multiple threads, which can lead to conflicts and potential crashes if not managed properly. This is where mutexes (short for “mutual exclusions”) come into play. Mutexes are tools used to ensure that only one thread can access a critical section at a time, maintaining atomicity—meaning an action either happens completely or not at all.

Mutexes help you modify critical sections without interference from other threads, which is essential for preventing issues like race conditions and ensuring data consistency. While they add complexity to your code, they are crucial for applications where atomic processes and thread safety are essential for reliable and stable performance.


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
#ifndef NETWORKSERVER_HPP
#define NETWORKSERVER_HPP

#include <windows.h>
#include <string>

#define DEFAULT_PORT 27015
#define DEFAULT_BUFLEN 512

namespace MyServer {

class NetworkServer {
public:
    NetworkServer(uint16_t port = DEFAULT_PORT);
    ~NetworkServer();

    bool startServer();
    void run();

private:
    uint16_t port;
    SOCKET ListenSocket;
    WSADATA wsaData;

    void handleClient(SOCKET ClientSocket);
    void closeServer();
};
}
#endif // NETWORKSERVER_HPP

#include "server.hpp"
#include <Windows.h>
#include <iostream>

MyServer::NetworkServer::NetworkServer( uint16_t port ) : port( port ), ListenSocket( INVALID_SOCKET )
{
    WSAStartup( MAKEWORD( 2, 2 ), &wsaData );
}

MyServer::NetworkServer::~NetworkServer()
{
    closeServer();
    WSACleanup();
}

bool MyServer::NetworkServer::startServer()
{
    ListenSocket = socket( AF_INET, SOCK_STREAM, IPPROTO_TCP );
    if ( ListenSocket == INVALID_SOCKET ) {
        std::cerr << "Socket creation failed.\n";
        return false;
    }

    sockaddr_in serverAddr;
    serverAddr.sin_family      = AF_INET;
    serverAddr.sin_addr.s_addr = INADDR_ANY;
    serverAddr.sin_port        = htons( port );

    if ( bind( ListenSocket, (sockaddr *)&serverAddr, sizeof( serverAddr ) ) == SOCKET_ERROR ) {
        std::cerr << "Bind failed.\n";
        closeServer();
        return false;
    }

    if ( listen( ListenSocket, SOMAXCONN ) == SOCKET_ERROR ) {
        std::cerr << "Listen failed.\n";
        closeServer();
        return false;
    }

    return true;
}

void MyServer::NetworkServer::run()
{
    while ( true ) {
        SOCKET ClientSocket = accept( ListenSocket, nullptr, nullptr );
        if ( ClientSocket == INVALID_SOCKET ) {
            std::cerr << "Accept failed.\n";
            break;
        }

        handleClient( ClientSocket );
        closesocket( ClientSocket );
    }
}

void MyServer::NetworkServer::handleClient( SOCKET ClientSocket )
{
    const size_t bufferSize = DEFAULT_BUFLEN;       // Use size_t for buffer size
    std::string  receivedData( bufferSize, '\0' );  // Initialize string with buffer size

    int recvResult = recv( ClientSocket, &receivedData[0], static_cast< int >( bufferSize ), 0 );
    if ( recvResult > 0 ) {
        receivedData.resize( recvResult );  // Resize to actual length of received data
        std::cout << "Received message: " << receivedData << std::endl;

        std::string sendbuf = "World";
        if ( send( ClientSocket, sendbuf.c_str(), sendbuf.length() + 1, 0 ) == SOCKET_ERROR ) {
            std::cerr << "Send failed.\n";
        }
    }
    else if ( recvResult == 0 ) {
        std::cout << "Connection closed gracefully" << std::endl;
    }
    else {
        std::cerr << "Recv failed: " << WSAGetLastError() << std::endl;
    }
}

void MyServer::NetworkServer::closeServer()
{
    if ( ListenSocket != INVALID_SOCKET ) {
        closesocket( ListenSocket );
        ListenSocket = INVALID_SOCKET;
    }
}

```

## Summary 
In conclusion, I gained a deeper understanding of computer science concepts and hands-on experience with various programming tools and techniques. I began by setting up my development environment, which laid the foundation for all subsequent learning. Through Object-Oriented Programming (OOP), I learned how to design and organize code efficiently, which was essential for the more complex projects I undertook, such as implementing linked lists and TCP server-client communication.

Next, I explored pointers, another fundamental concept, and applied them in creating linked lists and doubly linked lists. I then moved on to multithreading, where I learned how to optimize the use of CPU cores to speed up my programs. This included understanding mutexes, which are crucial for ensuring that critical points in the code are modified without interruption from other threads.

Finally, I learned how servers operate over the internet and successfully created my own server to send messages back and forth. Overall, I gained a lot of important and useful knowledge this term and look forward to continuing my learning with these new skills I've acquired.






