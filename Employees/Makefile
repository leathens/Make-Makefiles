# @file Makefile
# @author Anna Hensley 
# @date 2024-09-18
# @brief This is a Makefile that was specifically made for the Make & Makefiles assignment.
# @description Specifically, this Makefile is targeted for the files downloaded labeled "Employees" in the Make & Makefiles assignment description.

# compiler used
CC = g++

# name of final executable (what is tested) 
TARGET = employee

# Compile with all errors and warnings
# -g ... adds debugging info
# -Wall ... all compiler warnings
# -Wextra ... any other warnings
CFLAGS = -g -Wall -Wextra

# the default that allows the 'make' command without naming the target
# compiles and links everything together 
all: $(TARGET)

# Links by combining all .o files (object files) into the target
$(TARGET): main.o Employee.o Officer.o Supervisor.o
	$(CC) $(CFLAGS) -o $(TARGET) main.o Employee.o Officer.o Supervisor.o


# combines all .o files from the .cpp files (main, Employee, Officer, and Supervisor)
# .h files are the dependencies 
main.o: main.cpp Employee.h Officer.h Supervisor.h
	$(CC) $(CFLAGS) -c main.cpp

Employee.o: Employee.cpp Employee.h
	$(CC) $(CFLAGS) -c Employee.cpp

Officer.o: Officer.cpp Officer.h Employee.h
	$(CC) $(CFLAGS) -c Officer.cpp

Supervisor.o: Supervisor.cpp Supervisor.h Employee.h
	$(CC) $(CFLAGS) -c Supervisor.cpp


# cleaning removes the target, all .o files, and other backup files
# 'rm -f' helps errors from happening if the specified files do not exist
clean:
	rm -f $(TARGET) *.o *~
