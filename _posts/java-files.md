---
layout: default
title: java-files
date: 2024-07-02
status: ongoing
tags: java, programming-languages, file-handling
---

> Resource used:
>
> <https://java-programming.mooc.fi/>

## Files

**Files** are collections of data stored in the hard drive of a computer. Their format determines what data can be stored in it as well as the program required to read it.

- Information is made of bits [0s and 1s].
- Modern hard drives hold about 8 trillion bits.

> [!example]
> `.psd` files are read using Adobe Photoshop, ``.txt`` can be read using any text editor

**Filesystem** of a computer is responsible for keeping track of file location and performing operations [such as creating new files and such]. It abstracts the structure of a hard drive [i.e. you don't need to worry about how a file is actually stored].

### Reading from a file

#### File class

We import the input/output utility ``File`` in our program. Then we create an object and assign it our file's parameters.

- ``File`` class tends to be more object-oriented.

```java
import java.io.File;
public class reading
{
    public static void main(String[] args)
    {
        File file = new File("C:\\Users\\Ambha\\Python\\Java\\Nothing\\one.txt");
        //program
    }
```

Although it looks simple to use, there are a few drawbacks:

- Can't throw exceptions if error occurs
- Doesn't produce desired output at times
- Doesn't support symbolic links

It is better to use ``Path`` class instead. Here's how you convert a ``File`` class object to ``Path`` class :

```java
Path varName = fileName.toPath();
```

#### Path class

We import the ``Path`` utility to our program and then create an object.

```java
import java.nio.file.Path;
public class reading
{
    public static void main(String[] args)
    {
        Path file = Paths.get("fileName");
        //program
    }
```

Now, we've some technical terms to review here. Let's check them out one-by-one...

- **Absolute path** : Complete location of a file; starts from root directory till the file name.
- **Relative path** : Location of a file described from the current directory.
- **Canonical path** : Shortest absolute path to a file.
- **URI [Uniform Resource Identifier]** : Sequence of characters that allows complete identification of a resource. Similar to URL.

> [!example]
> Path : file.txt
> Absolute path : /home/User/test/file.txt

To read the file, we create a ``Scanner`` object and assign it the ``Path`` object. While doing this, we surround the code with ``try and catch`` blocks to handle errors.

- After that, we read each line using a while loop that will break when the scanner reaches the end of the file.

```java
while (fileScan.hasNextLine())
{
    String line = fileScan.nextLine();
}
```

> [!note]
> Path class often throws an IOException and returns a Boolean value when any operation is done.

#### Empty lines in file

Sometimes we may encounter an empty line while reading a file. To skip it, we use ``continue`` and ``isEmpty()`` method.

```java
//some program
while (fileScan.hasNextLine())
{
    String line = fileScan.nextLine();
    if (line.isEmpty())
    {
        continue;
    }
}
```

### Comma-separated values [CSV]

Note that if we're reading from a CSV file, we've to split the string according to commas.

```java
//some program before
while (true)
{

	System.out.print("Enter name and age separated by a comma: ");
	String line = scanner.nextLine();

	if (line.equals(""))
	{
		break;
	}

	String[] parts = line.split(",");
	String name = parts[0];
	int age = Integer.valueOf(parts[1]);

	//printing name and age
}
```

#### Reading objects from a file

We should create a method for creating objects from file data. 

In that method, we create an ``ArrayList`` object and then read the file using a while loop [like we do with a CSV file] and assigning the variables created for each part of a line as object attributes. Then we'd use a for-each loop to print every item of the ``ArrayList`` object.
