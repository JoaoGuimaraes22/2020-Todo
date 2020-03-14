## File

**Overview:**

- C# provides different classes to alter files and directories;
- Can be used to access directories, access files, open files for reading or writing, create a new file or move existing files from one location to another, etc.;

**Classes:**

- File:
  - It's static class that provides different functionalities like copy, create, move, delete, open for reading or /writing, encrypt or decrypt, check if a file exists, append lines or text to a file’s content, get last access time, etc;
- FileInfo:
  - It provides the same functionality as a static File class;
  - You have more control on how you do read/write operations on a file by writing code manually for reading or writing bytes from a file;
- Directory:
  - It's a static class that provides functionality for creating, moving, deleting and accessing subdirectories;

**File:**

- C# includes static File class to perform I/O operation on physical file system;
- It is not recommended to use File class for multiple operations on multiple files at the same time due to performance reasons;
- Use FileInfo class in that scenario;

**Important Methods of Static File Class:**

- AppendAllLines:
  - Appends lines to a file, and then closes the file;
  - If the specified file does not exist, this method creates a file, writes the specified lines to the file, and then closes the file;
- AppendAllText:
  - Opens a file, appends the specified string to the file, and then closes the file;
  - If the file does not exist, this method creates a file, writes the specified string to the file, then closes the file;
- AppendText:
  - Creates a StreamWriter that appends UTF-8 encoded text to an existing file, or to a new file if the specified file does not exist;
- Copy:
  - Copies an existing file to a new file;
  - Overwriting a file of the same name is not allowed;
- Create:
  - Creates or overwrites a file in the specified path;
- CreateText:
  - Creates or opens a file for writing UTF-8 encoded text;
- Decrypt:
  - Decrypts a file that was encrypted by the current account using the Encrypt method;
- Delete:
  - Deletes the specified file;
- Encrypt:
  - Encrypts a file so that only the account used to encrypt the file can decrypt it;
- Exists:
  - Determines whether the specified file exists;
- GetAccessControl:
  - Gets a FileSecurity object that encapsulates the access control list (ACL) entries for a specified file;
- Move:
  - Moves a specified file to a new location, providing the option to specify a new file name;
- Open:
  - Opens a FileStream on the specified path with read/write access;
- ReadAllBytes:
  - Opens a binary file, reads the contents of the file into a byte array, and then closes the file;
- ReadAllLines:
  - Opens a text file, reads all lines of the file, and then closes the file;
- ReadAllText:
  - Opens a text file, reads all lines of the file, and then closes the file;
- Replace:
  - Replaces the contents of a specified file with the contents of another file, deleting the original file, and creating a backup of the replaced file;
- WriteAllBytes:
  - Creates a new file, writes the specified byte array to the file, and then closes the file;
  - If the target file already exists, it is overwritten;
- WriteAllLines:
  - Creates a new file, writes a collection of strings to the file, and then closes the file;
- WriteAllText:
  - Creates a new file, writes the specified string to the file, and then closes the file;
  - If the target file already exists, it is overwritten;

**Example:**

```
//Check whether file is exists or not at particular location
bool isFileExists = File.Exists(@"C:\ DummyFile.txt"); // returns false

//Copy DummyFile.txt as new file DummyFileNew.txt
File.Copy(@"C:\DummyFile.txt", @"D:\NewDummyFile.txt");

//Get when the file was accessed last time
DateTime lastAccessTime = File.GetLastAccessTime(@"C:\DummyFile.txt");

//get when the file was written last time
DateTime lastWriteTime = File.GetLastWriteTime(@"C:\DummyFile.txt");

// Move file to new location
File.Move(@"C:\DummyFile.txt", @"D:\DummyFile.txt");

//Open file and returns FileStream for reading bytes from the file
FileStream fs = File.Open(@"D:\DummyFile.txt", FileMode.OpenOrCreate);

//Open file and return StreamReader for reading string from the file
StreamReader sr = File.OpenText(@"D:\DummyFile.txt");

//Delete file
File.Delete(@"C:\DummyFile.txt");
```

**Points to Remeber:**

- File is a static class to read\write from physical file with less coding;
- Static File class provides functionalities such as create, read\write, copy, move, delete and others for physical files;
- Static Directory class provides functionalities such as create, copy, move, delete etc for physical directories with less coding;
- FileInfo and DirectoryInfo class provides same functionality as static File and Directory class;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-file ;
