# Textmate grammar in Visual Studio

[![Build status](https://ci.appveyor.com/api/projects/status/x5v4qf0i0es5750h?svg=true)](https://ci.appveyor.com/project/madskristensen/textmatesample)

---------------------------------------

This is a sample project that demonstrates how to ship Textmate grammars inside Visual Studio extensions.

## Ship your own Textmate bundle
Here is how to ship any existing Textmate bundle as a Visual Studio extension.

### Step 1 - Clone this project
Clone or download this project. Find it [on GitHub](https://github.com/madskristensen/TextmateSample).

Then open the solution (.sln file) in Visual Studio 2017. It should look similar to this:

![Solution Explorer](art/solution-explorer.png)

### Step 2 - Modify metadata
Open the solution (.sln file) in Visual Studio 2017 or newer and open the `source.extension.vsixmanifest` file.

Update all the metadata such as name, author etc. and **make sure to use a new GUID as the Product ID**.

### Step 3 - Update license
Open `/Resources/LICENSE` file and update it to your needs. If the Apache 2.0 license works for you then just update the name in the top of the file.

### Step 4 - Add the Textmate files
Delete the files inside the `Grammars` folder and add your own `.tmLanguage` and/or `.tmTheme` files from the Textmate bundle. They are sometimes found inside a folder called `Syntaxes` in the Textmate bundle.

Make sure to set the **Build Action** to *Content* and the **Include in VSIX** to *True* for each of the Textmate files in the `/Grammars` folder.

> Select all the files and hit F4 to open the Properties tool window.

![Properties](art/properties.png)

### Step 5 - Update languages.pkgdef
This file registers the Textmate bundle with Visual Studio and associates the file extensions with icons.