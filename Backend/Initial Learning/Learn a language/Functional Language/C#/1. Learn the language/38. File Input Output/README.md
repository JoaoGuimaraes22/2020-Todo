# File I/O

## Here you will learn about

1. File Input Output:
   1. Stream I/O
   2. File;
   3. File Info;

## Overview

- A file is a collection of data stored in a disk with a specific name and a directory path;
- When a file is opened for reading or writing, it becomes a stream;
- There are two main streams:
  - The input stream:
    - For reading data from files (read operations);
  - The output stream:
    - For writing into the file (write operations);

## I/O Classes

- Classes from the System.IO namespace;
- Binary Reader:
  - Reads primitive data from a binary stream;
- BinaryWriter:
  - Writes primitive data in binary format;
- BufferedStream:
  - A temporary storage for a stream of bytes;
- Directory:
  - Helps in manipulating a directory structure;
- DirectoryInfo:
  - Used for performing operations on directories;
- DriveInfo:
  - Provides information for the drives;
- File:
  - Helps in manipulating files;
- FileInfo:
  - Used for performing operations on files;
- FileStream:
  - Used to read from and write to any location in a file;
- MemoryStream:
  - Used for random access to streamed data stored in memory;
- Path:
  - Performs operations on path information;
- StreamReader:
  - Used for reading characters from a byte stream;
- StreamWriter:
  - Used for writing characters to a stream;
- StringReader:
  - Used for reading from a string buffer;
- StringWriter:
  - Used for writing into a string buffer;

## The FileStream Class

- Helps in reading from, writing to and closing files;
- Syntax:

```c#
FileStream <object_name> = new FileStream( <file_name>, <FileMode Enumerator>,
   <FileAccess Enumerator>, <FileShare Enumerator>);
```

- For example, e create a FileStream object F for reading a file named sample.txt as shown:

```c#
FileStream F = new FileStream("sample.txt", FileMode.Open, FileAccess.Read,
   FileShare.Read);
```

### Parameters and descriptions

- FileMode:

  - The FileMode enumerator defines various methods for opening files:
    - Append:
      - Opens an existing file and puts cursor at the end of file, or creates the file, if the file does not exist;
    - Create:
      - Creates a new file;
    - CreateNew:
      - Specifies to the operating system, that it should create a file;
    - Open:
      - Open an existing file;
    - OpenOrCreate:
      - Specifies to the operating system that it should open a file if it exists, otherwise it should create a new file;
    - Truncate:
      - Opens an existing file and truncates its size to zero bytes;
  - FileAccess:
    - Has members:
      - Read;
      - ReadWrite;
      - Write;
  - FileShare:
    - Has members:
      - Inheritable:
        - Allows a file handle to pass inheritance to the child processes;
      - None:
        - Declines sharing of the current file;
      - Read:
        - Allows opening the file for reading;
      - ReadWrite:
        - Allows opening the file for reading and writing;
      - Write:
        - Allows opening the file for writing;

- Example:

```c#
using System;
using System.IO;

namespace FileIOApplication {
   class Program {
      static void Main(string[] args) {
         FileStream F = new FileStream("test.dat", FileMode.OpenOrCreate,
            FileAccess.ReadWrite);

         for (int i = 1; i <= 20; i++) {
            F.WriteByte((byte)i);
         }
         F.Position = 0;
         for (int i = 0; i <= 20; i++) {
            Console.Write(F.ReadByte() + " ");
         }
         F.Close();
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 -1
```

## Advanced File Operations

- Reading and writing into text files:
  - Involves reading from and writing into text files;
  - The StreamReader and StreamWriter class helps to accomplish it;
  - **See in** -> <https://www.tutorialspoint.com/csharp/csharp_text_files.htm> ;
- Reading from and Writing into Binary files:
  - Involves reading from and writing into binary files;
  - The BinaryReader and BinaryWriter class helps to accomplish this;
  - **See in** -> <https://www.tutorialspoint.com/csharp/csharp_binary_files.htm> ;
- Manipulating the Windows file system:
  - It gives a C# programamer the ability to browse and locate Windows files and directories;
  - **See in** -> <https://www.tutorialspoint.com/csharp/csharp_windows_file_system.htm> ;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_file_io.htm>
