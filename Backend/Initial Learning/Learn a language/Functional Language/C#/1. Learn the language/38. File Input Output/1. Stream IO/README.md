# Stream I/O

## Overview

- C# includes following standard IO (Input/Output) classes to read/write from different sources like a file, memory, network, isolated storage, etc;

## Stream

- System.IO.Stream is an abstract class that provides standard methods to transfer bytes (read, write, etc.) to the source;
- It's like a wrapper class to transfer bytes;
- Classes that need to read/write bytes from a particular source must implement the Stream class;
- The following classes inherits Stream class to provide functionality to Read/Write bytes from a particular source;

- FileStream:
  - Reads or writes bytes from/to a physical file whether it is a .txt, .exe, .jpg or any other file;
  - Derived from the Stream class;
- MemoryStream:
  - Reads or writes bytes that are stored in memory;
- BufferedStream:
  - Reads or writes bytes from other Streams to improve the performance of certain I/O operations;
- NetworkStream:
  - Reads or writes bytes from a network socket;
- PipeStream:
  - Reads or writes bytes from different processes;
- CryptoStream:
  - For linking data streams to cryptographic transformations;

## Stream Readers and Writers

- StreamReader:
  - It's a helper class for reading characters from a Stream by converting bytes into characters using an encoded value;
  - Can be used to read strings (characters) from different Streams like FileStream, MemoryStream, etc;
- StreamWriter:
  - It's a helper class for writing a string to a Stream by converting characters into bytes;
  - Can be used to write strings to different Streams such as FileStream, MemoryStream, etc;
- BinaryReader:
  - It's a helper class for reading primitive datatype from bytes;
- BinaryWriter:
  - Writes primitive types in binary;

## Points to Remember

- Stream is an abstract class for transfering bytes from different sources. It is base class for all other class that reads\writes bytes to different sources;
- FileStream class provides reading and writing functionality of bytes to physical file;
- Reader & writer classes provides functionality to read bytes from Stream classes (FileStream, MemoryStream etc) and converts bytes into appropriate encoding;
- StreamReader provides a helper method to read string from FileStream by converting bytes into strings. StreamWriter provides a helper method to write string to FileStream by converting strings into bytes;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-stream-io> ;
