#What is Go

Go Language
Go Libraries
Go tooling

#Go Workspace

Go programs must be kept in a directory hierarchy called a workspace, which is
simply a root directory of the Go programs.  A workspace contains three 
subdirectories at its root:

1. root src: This directory contains Go source files organized into packages.
2. packages pkg: This directory contains Go package objects.
3. objects bin: This directory contains executable commands (executable
programs).

Go source files are organized into directories called packages, in which 
a single directory is used for a single package. You can write two types 
of packages in Go:

1. Go Packages resulting in executable programs
2. programs Packages resulting in a shared library

The Go tool builds Go packages and installs the resulting binaries into the pkg
directory if it is a shared library, and into the bin directory if it is an 
executable program.

#GOPATH

You write Go programs in the workspace, which you should manually specify so
that Go runtime knows the workspace location. You can set the workspace 
location by using the GOPATH environment variable.

You write Go programs as packages into the GOPATH src directory. A single
directory is used for a single package. Go is designed to easily work with 
remote repositories such as GitHub and Google Code. When you maintain your 
programs in a remote source repository, use the root of that source repository 
as your base path.  

Note: For example, if you have a GitHub account at github.com/user, it should
be your base path. Let’s say you write a package named "mypackage" at 
github.com/user; your code organization path will be at 
%GOPATH%/src/github.com/user/mypackage. When you import this package to other
%programs, the path for importing the package will be github.com/user/mypackage. 
If you maintain the source in your local system, you can directly write programs 
under the GOPATH src directory. Suppose that you write a package named mypackage 
on a local system; your code organization path will be at %GOPATH%/src/mypackage, 
and the path for importing the package will be mypackage.


