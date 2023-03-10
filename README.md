BACKEND PROVA
==============

Intro
=====
Using any programming language (taking performance into consideration), write a server
("Application") that opens a socket and restricts input to at most 5 concurrent clients. Clients
will connect to the Application and write any number of 9 digit numbers, and then close the
connection. The Application must write a de-duplicated list of these numbers to a log file in no
particular order.

Primary Consideration
=====================

- The Application should work correctly as defined below in Requirements.
  
- The overall structure of the Application should be simple.
  
- The code of the Application should be descriptive and easy to read, and the build method and runtime parameters must be well-described and work.

- The design should be resilient with regard to data loss.
  
- The Application should be optimized for maximum throughput, weighed along with the other Primary Considerations and the Requirements below.

- The solution should be able to build and run from the command line. Include specific instructions on dependencies, build, test, and run instructions.

Requirements
============

1. The Application must accept input from at most 5 concurrent clients on TCP/IP port
4000.

2. Input lines presented to the Application via its socket must either be composed of
exactly nine decimal digits (e.g.: 314159265 or 007007009) immediately followed by a
server-native newline sequence; or a termination sequence as detailed below.

3. Numbers presented to the Application must include leading zeros as necessary to
ensure they are each 9 decimal digits.

4. The log file, to be named "numbers.log", must be created anew and/or cleared when the
Application starts.

5. Only numbers may be written to the log file. Each number must be followed by a
server-native newline sequence.

6. No duplicate numbers may be written to the log file.
   
7. Any data that does not conform to a valid line of input should be discarded and the client
connection terminated immediately and without comment.

8. Every 10 seconds, the Application must print a report to standard output:
   - The difference since the last report of the count of new unique numbers that have been received.
   - The difference since the last report of the count of new duplicate numbers that have been received.
   - The total number of unique numbers received for this run ofthe Application. o Example text: Received 50 unique numbers, 2 duplicates. Unique total: 567231

9. If any connected client writes a single line with only the word "terminate" followed by a
server-native newline sequence, the Application must disconnect all clients and perform
a clean shutdown as quickly as possible.

10. Clearly, state all of the assumptions you made in completing the Application.

NOTES
=====

- Ensure your application is executable from the command line.
  
- Distribute your code with all the necessary instructions to build it and run it.
  
- You may write tests at your own discretion. Tests are useful to ensure your Application passes Primary Consideration A.

- You are not restricted to Python language and libraries and frameworks that are considered part of the language. You may use common libraries and frameworks if their use helps improve Application simplicity and readability.

- Your Application may not for any part of its operational use or require the use of external systems, for example, Apache Kafka or Redis.

- At your discretion, leading zeroes present in the input may be stripped???or not used???when writing output to the log or console.

- Robust implementations of the Application typically handle more than 2M numbers per 10-second reporting period on a modern MacBook Pro laptop (e.g.: 16 GiB of RAM and a 2.5 GHz Intel i7 processor)




SOLUTION
========
Almost 4 Milion new numbers every 10 seconds

- Ryzen 7 3700x
- 32GB Ram


Unique: 3766906, duplicated: 16448, total: 6235754

Unique: 3819799, duplicated: 31484, total: 10055553

Unique: 3783042, duplicated: 45938, total: 13838595

Unique: 3777032, duplicated: 60260, total: 17615627

Unique: 3737175, duplicated: 74496, total: 21352802

Unique: 3740728, duplicated: 89037, total: 25093530
