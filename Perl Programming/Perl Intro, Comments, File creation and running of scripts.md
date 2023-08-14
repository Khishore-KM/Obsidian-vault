

#### Some facts:
- Perl is a general-purpose programming language originally developed for text manipulation and now used for a wide range of tasks including system administration, web development, network programming, GUI development, and more.
-  Though Perl is not officially an acronym but few people used it as **Practical Extraction and Report Language**.
-  Perl is an _Open Source_ software, licensed under its _Artistic License_, or the _GNU General Public License (GPL)_.
-  Perl was created by Larry Wall.
-  Perl takes the best features from other languages, such as C, awk, sed, sh, and BASIC, among others.
- Perl's database integration interface DBI supports third-party databases including Oracle, Sybase, Postgres, MySQL and others.
- Perl works with HTML, XML, and other mark-up languages.
- Perl supports Unicode.
- Perl is Y2K complaint.
- Perl is a procedural as well an object oriented language.
- Perl interfaces with external C/C++ libraries.
- The Perl interpreter can be embedded into other systems

#### Perl is interpreted:
Perl is an interpreted language, which means that your code can be run as is, without a compilation stage that creates a non portable executable program.

Traditional compilers convert programs into machine language. When you run a Perl program, it's first compiled into a byte code, which is then converted ( as the program runs) into machine instructions. So it is not quite the same as shells, or Tcl, which are **strictly** interpreted without an intermediate representation.

It is also not like most versions of C or C++, which are compiled directly into a machine dependent format. It is somewhere in between, along with _Python_ and _awk_ and Emacs .elc files.



Perl borrows syntax and concepts from many languages: awk, sed, C, Bourne Shell, Smalltalk, Lisp and even English.


A Perl program consists of a sequence of declarations and statements, which run from the top to the bottom. Loops, subroutines, and other control structures allow you to jump around within the code. Every simple statement must end with a semicolon (;).


Perl is a free-form language: you can format and indent it however you like. Whitespace serves mostly to separate tokens, unlike languages like Python where it is an important part of the syntax, or Fortran where it is immaterial.

~~~
$perl -e 'print "Hello World\n"'
~~~

The output will be.

~~~ 
Hello, world 
~~~


Writing perl as a script:

~~~
#!/usr/bin/perl

# This will print "Hello, World"
print "Hello, world\n";
~~~

You can create a perl file and then you can change its permission to run it as a file in command line.

~~~
$chmod 0755 hello.pl
$./hello.pl
~~~


You can also use:

~~~
chmod a+x hello.pl
./hello.pl
~~~

##### Perl file extension:

As a Perl convention, a Perl file must be saved with a .pl or .PL file extension in order to be recognized as a functioning Perl script. File names can contain numbers, symbols, and letters but must not contain a space. Use an underscore (_) in places of spaces.


##### Comments in Perl:

~~~
Single line comments are made using the # tag symbol as like the python scripts


Multi Line comments:

#!/usr/bin/perl

# This is a single line comment
print "Hello, world\n";

=begin comment
This is all part of multiline comment.
You can use as many lines as you like
These comments will be ignored by the 
compiler until the next =cut is encountered.
=cut
~~~

