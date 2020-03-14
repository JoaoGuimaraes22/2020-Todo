## FileInfo

**Overview:**

- The FileInfo class provides the same functionality as the static File class but you have more control on read/write operations on files by writing code manually for reading or writing bytes from a file;

**Important Properties of FileInfo:**

- Directory:
  - Gets an instance of the parent directory;
- DirectoryName:
  - Gets a string representing the directory's full path;
- Exists:
  - Gets a value indicating whether a file exists;
- Extension:
  - Gets the string representing the extension part of the file;
- FullName:
  - Gets the full path of the directory or file;
- IsReadOnly:
  - Gets or sets a value that determines if the current file is read only;
- LastAccessTime:
  - Gets or sets the time the current file or directory was last accessed;
- LastWriteTime:
  - Gets or sets the time when the current file or directory was last written to;
- Length:
  - Gets the size, in bytes, of the current file;
- Name:
  - Gets the name of the file;

**Important Methods of FileInfo::**

- AppendText:
  - Creates a StreamWriter that appends text to the file represented by this instance of the FileInfo;
- CopyTo:
  - Copies an existing file to a new file, disallowing the overwriting of an existing file;
- Create:
  - Creates a file;
- CreateText:
  - Creates a StreamWriter that writes a new text file;
- Decrypt:
  - Decrypts a file that was encrypted by the current account using the Encrypt method;
- Delete:
  - Deletes the specified file;
- Encrypt:
  - Encrypts a file so that only the account used to encrypt the file can decrypt it;
- GetAccessControl:
  - Gets a FileSecurity object that encapsulates the access control list (ACL) entries for a specified file;
- MoveTo:
  - Moves a specified file to a new location, providing the option to specify a new file name;
- Open:
  - Opens a in the specified FileMode;
- OpenRead:
  - Creates a read-only FileStream;
- OpenText:
  - Creates a StreamReader with UTF8 encoding that reads from an existing text file;
- OpenWrite:
  - Creates a write-only FileStream;
- Replace:
  - Replaces the contents of a specified file with the file described by the current FileInfo object, deleting the original file, and creating a backup of the replaced file;
- ToString:
  - Returns a path as string;

**Example:**

```
//Create FileInfo object for DummyFile.txt
FileInfo fi = new FileInfo(@"D:\DummyFile.txt");

//open DummyFile.txt for read operation
FileStream fsToRead = fi.Open(FileMode.OpenOrCreate, FileAccess.ReadWrite , FileShare.ReadWrite);

//open DummyFile.txt for write operation
FileStream fsToWrite = fi.Open(FileMode.OpenOrCreate, FileAccess.ReadWrite, FileShare.ReadWrite);

//get the StreamReader

StreamReader sr = new StreamReader(fsToRead);
//read all texts using StreamReader object
string fileContent = sr.ReadToEnd();
sr.Close();

//get the StreamWriter
StreamWriter sw = new StreamWriter(fsToWrite);
//write some text using StreamWriter
sw.WriteLine("Another line from streamwriter");
sw.Close();

//close all Stream objects
fsToRead.Close();
fsToWrite.Close();
```

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-fileinfo ;
