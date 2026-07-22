Question 3: File Processing Using Linux System Calls
Objective

The objective is to create a file, write employee records, update a specific record without rewriting the complete file, efficiently retrieve records, and close the file using Linux system calls.

open()

The open() system call creates or opens the employee data file.

The O_CREAT flag creates the file if it does not already exist, while O_RDWR allows both reading and writing.

The system call returns a file descriptor that is used by the other system calls.

write()

The write() system call writes employee records to the file.

Since each employee record has a fixed-size structure, the location of each record can be calculated using its position and the size of the structure.

lseek()

The lseek() system call moves the file offset to a specific location.

For example, to update the second employee record, the program moves the file pointer to:

1 × sizeof(struct Employee)

The record can then be updated directly without reading or rewriting the entire file.

Updating a Specific Record

The program uses lseek() to move to the exact location of the required employee record.

It then uses write() to overwrite only that record.

This is more efficient than reading all records, modifying one record in memory, and rewriting the entire file.

read()

The read() system call retrieves employee records from the file.

After resetting the file offset using lseek(), the program reads the records sequentially.

close()

The close() system call closes the file descriptor after all file operations are complete.

This releases the operating system resource associated with the file.

Result

The program successfully created a file, wrote employee records, updated a specific employee record directly, retrieved records from the file, and closed the file using Linux system calls.
