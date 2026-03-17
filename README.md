Library Information Management System
Project Overview
This project is a Command-Line Interface (CLI) library information management system developed in the C programming language. The application features a comprehensive, menu-driven interactive interface designed to handle everything from book entry and retrieval to tracking borrowing status and persisting data locally. The system employs a dual-mode permission model, dividing users into Visitor and Manager roles to accommodate different operational needs and security levels.

Core Features
Dual-Mode Access Control
The system uses a hierarchical menu structure, starting with a primary menu to select the user identity, followed by 15 secondary service menus. The Visitor mode provides basic services such as querying, browsing, and borrowing or returning books. The Manager mode grants top-level permissions, enabling bulk book entry, deletion, information modification, and full inventory sorting.

Book Lifecycle Management
Administrators can input detailed attributes for each book, including login number, title, author, classification number, publisher, publication time, and price. Functions like bookzhengjia (add) and bookshanchu (delete) utilize pointers and the gets function to dynamically manipulate the array of structures. Users can accurately retrieve specific books using keyword searches or browse the entire catalog.

Borrow and Return Tracking
The software independently records and modifies the current borrow or return status of every single book, making it easy to track the circulation of the library's inventory.

Inventory Sorting
A built-in data organization feature allows the inventory to be sorted. The bookpaixu function implements the Selection Sort algorithm, utilizing the strcmp function to compare specific book attributes (such as the login number) across the entire database and rearrange them accordingly.

System Architecture and Implementation
Core Data Structure
At its core, the system abstracts individual books using a C structure (struct book). The entire library inventory is managed in memory through an array of these structures or structure pointers (struct book *p), ensuring high-speed reading and modification during runtime.

Local Data Persistence
To prevent data loss when the program is closed, a robust file I/O module is integrated. All book records are formatted and written to a local text file named book.txt. The data serialization and deserialization are handled using fopen("book.txt","r") and fscanf functions within the bookzairu (load) and bookbaocun (save) modules. The system automatically loads this data upon startup and saves all modifications upon exit.

Environment and Setup
This system is built using the standard C language (C89/C99 standards) and relies on standard libraries such as <stdio.h>, <string.h>, and <stdlib.h>. It is fully compatible with standard C compilers including GCC (Linux/MinGW) and MSVC (Visual Studio).

Usage Guide
Compilation
You can compile the source code using a standard C compiler. For example, if you are using GCC, run the following command in your terminal:

Bash
gcc -o library_system main.c
Execution
Once compiled, you can start the application by running the generated executable:

Bash
./library_system
First Run Configuration
When running the program for the first time, please ensure that the directory containing the executable has read and write permissions. This is necessary so the system can successfully generate the book.txt file required for data storage.
