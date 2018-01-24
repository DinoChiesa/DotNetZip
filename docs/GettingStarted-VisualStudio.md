## Get Started using DotNetZip in Visual Studio

You can use any sort of Visual Studio project to build an application that creates or reads zip files. You will need only to add a reference to the DotNetZip library into the project.

# Example

1. Download the latest DotNetZip Developer's Kit package from http://dotnetzip.codeplex.com/Release/ProjectReleases.aspx. The developer's kit is for those building apps that use the library. The devkit download includes the DLL, the XML intellisense file, and the .chm help file for DotNetZip.

2. Unpack the DevKit archive, including those three files, into a new directory. Name it anything you like. Remember the location.

3. Create a project in Visual Studio. For example, File...New....Project... and select Windows Forms Application. You can use any language: VB, C#, etc.

4. Right-click the project, and select "Add Reference..."

5. Select the Browse tab, and browse to the folder or directory where you unpacked DotNetZip.

6. Select the DotNetZip DLL for your project. Use Ionic.Zip.dll if you will be reading or writing ZIP files. Use Ionic.Zlib.dll if you want only ZLIB capability. (The zip.dll includes zip capability, as well as all the function of the ZLIB dll). If you are building a Compact Framework app, select the appropriate CF version of the DLL. The Reduced DLL is a ZIP dll that lacks the ability to produce self-extracting archives.

7. Include "using Ionic.Zip;" at the top of your source file.

7. Write your application code that uses the DotNetZip library.

8. Remember to include the DotNetZip license in anything you distribute that relies on DotNetZip.
