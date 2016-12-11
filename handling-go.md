#What is Go

Go Language
Go Libraries
Go tooling

#Google pattner workflow for Go Lang

https://golang.org/doc/code.html

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

#Go Version Manager - GVM

https://github.com/moovweb/gvm

```
$ bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
$ source ~/.gvm/scripts/gvm
$ gvm version
Go Version Manager v1.0.22 installed at ...
```

```
$ gvm
Usage: gvm [command]

Description:
  GVM is the Go Version Manager

Commands:
  version    - print the gvm version number
  get        - gets the latest code (for debugging)
  use        - select a go version to use (--default to set permanently)
  diff       - view changes to Go root
  help       - display this usage text
  implode    - completely remove gvm
  install    - install go versions
  uninstall  - uninstall go versions
  cross      - install go cross compilers
  linkthis   - link this directory into GOPATH
  list       - list installed go versions
  listall    - list available versions
  alias      - manage go version aliases
  pkgset     - manage go packages sets
  pkgenv     - edit the environment for a package set
```

```
$ gvm install go1.7.3 -B
Installing go1.7.3 from binary source
```

```
$ gvm list
gvm gos (installed)
   go1.7.3
   system
```

```
$ gvm use go1.7.3
Now using version go1.7.3
```

```
$ which go
~/.gvm/gos/go1.7.3/bin/go
```

```
$ gvm use system
Now using version system
```

```
$ which go
/usr/lib/golang/bin/go
```

```
$ gvm use go1.7.3 --default
Now using version go1.7.3
```

```
$ gvm list
gvm gos (installed)
=> go1.7.3
   system
```

So now we have a local version of go installed, our GOPATH and PATH are setup,
and we have access to the go executable. Now what? One of the neat things about
gvm is the notion of pkgsets, basically allowing you to define separate
"workspaces" and group a set of go projects using the same go version.


