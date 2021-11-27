# findr
Walk a filesystem with configurable path and filename filters.


# Python Zind
*zind* is library for walking the filesystem and scanning files with configurable path and text filters.

# Zind features
* Walk filesystem
* Filter files and directories using configurable filters
* Print lines of text in files
* Filter lines of text using configurable filters
* Pure Python - no dependencies

# Installation
```
pip install zind
```

# Zind Cli
Some examples of the zind cli would look like this:
```
# Walk the filesystem
$ zind

# Filter out all paths that contain the text 'node_module'
$ zind -ge node_module

# Only include paths with the text 'py'
$ zind -g py

# Only include paths that end with the text py
# zind -gr ".*py$"
```

# Cli Usage
Filesystem files and directories can be filtered based on input tokens. `-g` <text> will only return lines with matching text. `-ge` <text> will exclude lines with matching text. `-gr` <text> will use regex matching to include text. `-gc` will enforce case sensitive matches. The options can be mix and matched. `-gre .*.py$` will exclude all files ending in .py.
  
Files can be scanned line by line as well. `-t` <text> will cause the tool to print matching lines within files that contain the matching text. `-te` will exclude  matching lines in text.

# Getting Started
The most simple example of the api would look like this:
```
from zind.api.core_find import Find

find = Find()
file_matches = find.find(".",[])

for file_match in file_matches:
  print(file_match)
```
