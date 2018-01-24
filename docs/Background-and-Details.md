## What is DotNetZip All About?
The System.IO.Compression namespace added in the Microsoft .NET Framework {v2.0 v3.0 v3.5} includes base class libraries supporting compression within streams - both the Deflate (ietf rfc-1951) and Gzip (ietf rfc-1952) compression formats are supported, in the DeflateStream and GZipStream classes, respectively. 

But the System.IO.Compression namespace provides streaming compression only - useful for compressing a single stream or block of bytes, but not directly useful for creating compressed archives, like .zip files or .gzip files. The compressed archives, in addition to containing the compressed stream (or file) data, also include header information, what might be called "metadata". For .zip files, the format is defined by PKWare Inc; For gzip, the format is described in RFC-1952. But the System.IO.Compression.DeflateStream class does not parse the metadata for such files. The classes in the System.IO.Compression namespace do not directly support formatting zip or gzip archive headers and so on. 

As a result, if you build an application with the .NET Framework, and you want to manipulate .ZIP files, you will need an external library to do so. 

This class library provides the handling for Zip files that the .NET Framework base class library lacks. Using this library, you can build .NET applications that read and write zip-format files. The library relies on the System.IO.Compression.DeflateStream class, to perform compression. Around that capability, the library adds logic for formatting zip headers, doing encryption and decryption, verifying zip contents, managing zip entries in an archive, and so on.

## Why Another Library?
There are various Zip class libraries available for .NET applications. For example,

- *The J# runtime.* it is possible to read and write zip files within .NET via the J# runtime. But some people don't like to install the extra J# DLL, which is very large, just for the zip capability. Also , the end-of-life of J# has been announced by Microsoft.

- *SharpZipLib* - a 3rd party LGPL-based (or is it GPL?) library. It works, in both .NET 1.1 and .NET 2.0. But some people don't like the GPL, and some people say the library is complicated and slow.

- *Commercial Tools* - There are commercial tools (from ComponentOne, XCeed, etc). But some people don't want to incur the cost.

- The *System.Packaging* namespace added in .NET 3.0

DotNetZip is an alternative to all of these options. It is open source, though not GPL licensed. It is free of cost, though donations are encouraged. It is small and simple, but it does what you need. It does not require J#. Unlike the System.Packaging classes, DotNetZip is designed specifically for .ZIP files and is easier to use because of that. (It does require .NET 2.0 for the DeflateStream class).

This code is released under the Microsoft Public License. See the License.txt for details.

### Features:
read, write, and update .zip files.
read zips from streams or files, write zips to streams or files.
extract zip entries to stream. Add entries from a stream.
comments on zip entries as well as the entire zip archive
progress events for Save and Extract operations.
support for double-byte chars (UTF-8, or any code page) in filenames
can generate self-extracting archives.
ZIP64 for large (>4.2g) archives

### Bugs:
does not do 0..9 compression levels (not supported by the DeflateStream class)
does only PKZIP encryption, which is weak. No Strong Encryption. Yet?
does not do "full archive" password protection - where the central directory itself is encrypted.
no support for reading or writing multi-disk zip archives
no support for asynchronous operation


## DotNetZip does .zip files, not .gz files
If you want code to handle .gz files, see [this link](http://blogs.msdn.com/bclteam/archive/2005/06/15/429542.aspx)
