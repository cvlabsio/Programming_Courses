### Lesson 1: Introduction to Perl

#### What is Perl?
Perl stands for Practical Extraction and Reporting Language. It's a high-level, interpreted, general-purpose programming language developed by Larry Wall. Perl is known for its flexibility, powerful text-processing features, and its motto of "There's more than one way to do it" (TMTOWTDI).

#### Installing Perl:
Perl is typically pre-installed on Unix-like operating systems. For Windows, you can download and install it from [ActiveState Perl](https://www.activestate.com/products/perl/).

#### Hello, World!:
Let's start with a simple "Hello, World!" program:

```perl
#!/usr/bin/perl
use strict;
use warnings;

print "Hello, World!\n";
```

#### Explanation:
- `#!/usr/bin/perl`: This is called a shebang line. It tells the system to execute the script using Perl.
- `use strict;` and `use warnings;`: These are pragmas that enforce stricter rules and enable warnings, helping to write cleaner and safer code.
- `print "Hello, World!\n";`: This line prints the string "Hello, World!" followed by a newline character.

#### Running the Script:
Save the above code in a file (e.g., hello.pl) and execute it using the Perl interpreter:

```bash
perl hello.pl
```

Congratulations! You've written and executed your first Perl program. In the next lesson, we'll dive deeper into Perl syntax and variables.

### Lesson 2: Perl Syntax and Variables

#### Comments:
In Perl, you can use `#` to add comments:

```perl
# This is a comment
```

#### Variables:
Perl has three main types of variables: scalars, arrays, and hashes.

- **Scalars**: They hold single values such as numbers or strings.
- **Arrays**: They hold ordered lists of scalar values.
- **Hashes**: They hold key-value pairs.

#### Scalars:
Scalars are defined using the `$` symbol followed by the variable name. They can hold numbers or strings.

```perl
my $name = "Alice";
my $age = 30;
```

#### Arrays:
Arrays are defined using `@` symbol followed by the variable name. They can hold a list of scalar values.

```perl
my @numbers = (1, 2, 3, 4, 5);
my @names = ("Alice", "Bob", "Charlie");
```

#### Hashes:
Hashes are defined using `%` symbol followed by the variable name. They store key-value pairs.

```perl
my %student = (
    "name" => "Alice",
    "age"  => 20,
    "grade" => "A"
);
```

#### Printing Variables:
You can use the `print` function to display the values of variables:

```perl
print "Name: $name\n";
print "Age: $age\n";
```

#### Array and Hash Access:
You can access elements of arrays and hashes using square brackets `[]` and curly braces `{}` respectively:

```perl
print "First number: $numbers[0]\n";       # Accessing the first element of the array
print "Name: $student{'name'}\n";           # Accessing the value associated with the key 'name' in the hash
```

#### Special Variables:
Perl also has a set of special variables, such as `$ARGV`, `$_`, `@ARGV`, etc., which have predefined meanings and uses.

#### Example Program:
Let's write a simple program to demonstrate the usage of variables:

```perl
#!/usr/bin/perl
use strict;
use warnings;

my $name = "Alice";
my $age = 30;

print "Name: $name\n";
print "Age: $age\n";
```

#### Running the Script:
Save the above code in a file (e.g., variables.pl) and execute it using the Perl interpreter:

```bash
perl variables.pl
```

You've learned about Perl syntax and variables. In the next lesson, we'll explore control structures like loops and conditionals.

### Lesson 3: Control Structures in Perl

#### Conditional Statements:
Perl supports standard conditional statements like `if`, `else`, and `elsif`.

```perl
my $age = 25;

if ($age < 18) {
    print "You are a minor\n";
} elsif ($age >= 18 && $age < 65) {
    print "You are an adult\n";
} else {
    print "You are a senior citizen\n";
}
```

#### Loops:
Perl provides different types of loops such as `for`, `while`, and `foreach`.

- **`for` Loop:**
```perl
for (my $i = 1; $i <= 5; $i++) {
    print "$i\n";
}
```

- **`while` Loop:**
```perl
my $i = 1;
while ($i <= 5) {
    print "$i\n";
    $i++;
}
```

- **`foreach` Loop (or `for` each):**
```perl
my @colors = ("red", "green", "blue");
foreach my $color (@colors) {
    print "$color\n";
}
```

#### Control Statements:
Perl supports control statements like `next`, `last`, and `redo` within loops.

```perl
for (my $i = 1; $i <= 10; $i++) {
    next if $i % 2 == 0;  # Skips even numbers
    last if $i == 7;      # Exits loop when $i is 7
    print "$i\n";
}
```

#### Example Program:
Let's write a program that prints even numbers from 1 to 10 using a loop and conditional statement:

```perl
#!/usr/bin/perl
use strict;
use warnings;

for (my $i = 1; $i <= 10; $i++) {
    next if $i % 2 != 0;  # Skips odd numbers
    print "$i\n";
}
```

#### Running the Script:
Save the above code in a file (e.g., control_structures.pl) and execute it using the Perl interpreter:

```bash
perl control_structures.pl
```

You've learned about control structures in Perl. In the next lesson, we'll cover subroutines and functions.

### Lesson 4: Subroutines and Functions in Perl

#### Subroutines:
Subroutines are blocks of code that can be reused throughout a program. They are defined using the `sub` keyword.

```perl
sub greet {
    my $name = shift;   # shift removes and returns the first element of @_
    print "Hello, $name!\n";
}

greet("Alice");
```

#### Return Values:
Subroutines can return values using the `return` statement.

```perl
sub add {
    my ($a, $b) = @_;
    return $a + $b;
}

my $result = add(3, 5);
print "Result: $result\n";
```

#### Passing Arguments:
Arguments can be passed to subroutines using the special array `@_`.

#### Default Arguments:
You can provide default values for subroutine arguments.

```perl
sub greet {
    my $name = shift // "Stranger";  # Default value is "Stranger" if no argument is passed
    print "Hello, $name!\n";
}

greet();       # Outputs: Hello, Stranger!
greet("Alice");  # Outputs: Hello, Alice!
```

#### Anonymous Subroutines:
Perl supports anonymous subroutines, also known as closures.

```perl
my $square = sub {
    my $num = shift;
    return $num * $num;
};

print $square->(5);  # Outputs: 25
```

#### Example Program:
Let's write a program that calculates the factorial of a number using a subroutine:

```perl
#!/usr/bin/perl
use strict;
use warnings;

sub factorial {
    my $n = shift;
    return 1 if $n == 0;
    return $n * factorial($n - 1);
}

my $number = 5;
my $result = factorial($number);
print "Factorial of $number is $result\n";
```

#### Running the Script:
Save the above code in a file (e.g., subroutines.pl) and execute it using the Perl interpreter:

```bash
perl subroutines.pl
```

You've learned about subroutines and functions in Perl. In the next lesson, we'll cover file handling and input/output operations.

### Lesson 5: File Handling and Input/Output in Perl

#### File Handling:
Perl provides built-in functions for file handling such as `open`, `close`, `read`, `write`, etc.

#### Opening a File:
You can open a file using the `open` function.

```perl
my $filename = "example.txt";
open(my $fh, '<', $filename) or die "Could not open file '$filename' $!";
```

#### Reading from a File:
You can read from a file line by line using the `<$fh>` notation.

```perl
while (my $line = <$fh>) {
    print "Read: $line";
}
```

#### Writing to a File:
You can open a file for writing using `>` mode and append using `>>` mode.

```perl
my $output_file = "output.txt";
open(my $out_fh, '>', $output_file) or die "Could not open file '$output_file' $!";
print $out_fh "This is a line written to the file.\n";
close($out_fh);
```

#### Filehandles:
Filehandles are used to associate a file with a name. They can be scalar variables.

#### Standard Input/Output:
Perl uses `STDIN`, `STDOUT`, and `STDERR` for standard input, output, and error streams respectively.

```perl
print "Enter your name: ";
my $name = <STDIN>;
chomp($name);
print "Hello, $name!\n";
```

#### Example Program:
Let's write a program that reads from one file and writes to another.

```perl
#!/usr/bin/perl
use strict;
use warnings;

my $input_file = "input.txt";
my $output_file = "output.txt";

open(my $in_fh, '<', $input_file) or die "Could not open file '$input_file' $!";
open(my $out_fh, '>', $output_file) or die "Could not open file '$output_file' $!";

while (my $line = <$in_fh>) {
    print $out_fh $line;
}

close($in_fh);
close($out_fh);
```

#### Running the Script:
Save the above code in a file (e.g., file_io.pl) along with an input file (input.txt) and execute it using the Perl interpreter:

```bash
perl file_io.pl
```

You've learned about file handling and input/output operations in Perl. In the next lesson, we'll delve into regular expressions for text processing.

### Lesson 6: Regular Expressions in Perl

#### What are Regular Expressions?
Regular expressions (regex) are patterns used to match character combinations in strings. Perl provides powerful support for regular expressions.

#### Basic Regular Expression Metacharacters:
- `.` : Matches any single character except newline.
- `^` : Anchors the match to the beginning of the string.
- `$` : Anchors the match to the end of the string.
- `*` : Matches zero or more occurrences of the preceding element.
- `+` : Matches one or more occurrences of the preceding element.
- `?` : Matches zero or one occurrence of the preceding element.
- `|` : Alternation, matches either the expression before or after the `|`.

#### Using Regular Expressions in Perl:
Perl provides the `=~` operator to apply a regular expression to a string.

```perl
my $string = "The quick brown fox jumps over the lazy dog";

if ($string =~ /quick/) {
    print "Match found!\n";
} else {
    print "No match found!\n";
}
```

#### Metacharacters in Patterns:
To match metacharacters themselves, you can use a backslash `\`.

```perl
if ($string =~ /\./) {
    print "Period found!\n";
}
```

#### Character Classes:
Character classes allow you to match any one of a set of characters.

```perl
if ($string =~ /[aeiou]/) {
    print "Vowel found!\n";
}
```

#### Quantifiers:
Quantifiers specify how many occurrences of the previous element are allowed.

```perl
if ($string =~ /o+/) {
    print "One or more 'o's found!\n";
}
```

#### Example Program:
Let's write a program that extracts email addresses from a given text using regular expressions:

```perl
#!/usr/bin/perl
use strict;
use warnings;

my $text = "Contact us at support@example.com or info@test.com";

while ($text =~ /([a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,})/g) {
    print "Email: $1\n";
}
```

#### Running the Script:
Save the above code in a file (e.g., regex_example.pl) and execute it using the Perl interpreter:

```bash
perl regex_example.pl
```

You've learned about regular expressions in Perl. In the next lesson, we'll cover some advanced topics such as modules and error handling.

### Lesson 7: Advanced Perl Topics - Modules and Error Handling

#### Modules in Perl:
Perl modules are reusable packages of code that can be used to extend Perl's capabilities. They are stored in files with a `.pm` extension.

#### Using Modules:
You can use modules in your Perl script using the `use` keyword followed by the module name.

```perl
use Module::Name;
```

#### Standard Perl Modules:
Perl comes with a rich set of standard modules. Some common ones include:
- `strict`: Enforces more stringent syntax checking.
- `warnings`: Enables optional warnings.
- `File::Copy`: Provides functions for copying files.
- `File::Path`: Provides functions for creating directories.

#### Installing Modules:
You can install additional modules using the CPAN (Comprehensive Perl Archive Network) tool.

```bash
cpan Module::Name
```

#### Error Handling:
Perl provides several mechanisms for error handling, including `die`, `warn`, and `eval`.

- `die`: Terminates the program and prints an error message.
- `warn`: Prints a warning message.
- `eval`: Evaluates a block of code and catches exceptions.

```perl
my $result = eval {
    # Code that might throw an exception
};
if ($@) {
    warn "An error occurred: $@";
}
```

#### Example Program:
Let's write a program that copies a file and handles errors gracefully:

```perl
#!/usr/bin/perl
use strict;
use warnings;
use File::Copy;

my $source = "source.txt";
my $destination = "destination.txt";

eval {
    copy($source, $destination) or die "Copy failed: $!";
    print "File copied successfully!\n";
};
if ($@) {
    warn "An error occurred: $@";
}
```

#### Running the Script:
Save the above code in a file (e.g., module_error_handling.pl) and execute it using the Perl interpreter:

```bash
perl module_error_handling.pl
```

You've learned about modules and error handling in Perl. These are essential topics for writing robust and maintainable Perl programs. In the next lesson, we'll cover some practical applications of Perl in the field of cybersecurity.

### Lesson 7: Advanced Perl Topics

#### 1. Modules:
Perl has a vast ecosystem of modules available through CPAN (Comprehensive Perl Archive Network). Modules provide reusable code for various tasks, such as text processing, networking, and database interaction.

##### Using Modules:
You can use modules in your Perl programs using the `use` keyword.

```perl
use Module::Name;
```

##### Example:
Let's use the `File::Copy` module to copy a file.

```perl
use strict;
use warnings;
use File::Copy;

copy("source.txt", "destination.txt") or die "Copy failed: $!";
print "File copied successfully.\n";
```

#### 2. Error Handling:
Error handling is crucial for writing robust Perl programs. You can handle errors using the `die` function to print an error message and terminate the program.

```perl
open(my $fh, '<', 'filename.txt') or die "Unable to open file: $!";
```

#### 3. Command Line Arguments:
Perl scripts can accept command-line arguments using the special array `@ARGV`.

```perl
my $filename = $ARGV[0];
print "Filename: $filename\n";
```

#### Example Program:
Let's write a program that takes a filename as a command-line argument, reads the file, and prints its contents.

```perl
#!/usr/bin/perl
use strict;
use warnings;

my $filename = $ARGV[0] or die "Usage: $0 <filename>\n";

open(my $fh, '<', $filename) or die "Unable to open file '$filename' $!";

while (my $line = <$fh>) {
    print $line;
}

close($fh);
```

#### Running the Script:
Save the above code in a file (e.g., file_reader.pl) and make it executable:

```bash
chmod +x file_reader.pl
```

Execute the script with a filename as an argument:

```bash
./file_reader.pl input.txt
```

You've learned about advanced Perl topics like modules, error handling, and command-line arguments. These concepts will help you write more robust and versatile Perl programs. In the next lesson, we'll explore how Perl can be applied in cybersecurity tasks.

### Lesson 7: Advanced Topics in Perl

#### Modules:
Perl has a vast ecosystem of modules available on CPAN (Comprehensive Perl Archive Network) for various tasks. You can use these modules to extend the functionality of your Perl programs.

- **Installing Modules**: You can install modules using tools like CPAN or CPAN Minus (`cpanm`). For example:
  ```bash
  cpanm Module::Name
  ```

- **Using Modules**: Once installed, you can use modules in your Perl scripts using the `use` keyword.
  ```perl
  use Module::Name;
  ```

#### Error Handling:
Perl provides several mechanisms for error handling, including `die`, `warn`, and `eval`.

- **die**: Terminates the program and prints an error message.
  ```perl
  open(my $fh, '<', $filename) or die "Could not open file: $!";
  ```

- **warn**: Prints a warning message but allows the program to continue.
  ```perl
  if ($age < 0) {
      warn "Age cannot be negative!";
  }
  ```

- **eval**: Evaluates a block of code and catches exceptions.
  ```perl
  eval {
      # Code that might throw an exception
  };
  if ($@) {
      warn "An error occurred: $@";
  }
  ```

#### Object-Oriented Programming (OOP):
Perl supports object-oriented programming with classes and objects.

- **Defining a Class**:
  ```perl
  package MyClass;
  
  sub new {
      my ($class, $arg1, $arg2) = @_;
      my $self = {
          attribute1 => $arg1,
          attribute2 => $arg2,
      };
      bless $self, $class;
      return $self;
  }
  ```

- **Creating Objects**:
  ```perl
  my $object = MyClass->new($value1, $value2);
  ```

- **Method Calls**:
  ```perl
  $object->method_name($arg);
  ```

#### Example Program:
Let's create a simple example demonstrating the usage of a module, error handling, and object-oriented programming:

```perl
#!/usr/bin/perl
use strict;
use warnings;
use LWP::Simple;  # Using LWP::Simple module for fetching webpage content

# Define a simple class
package MyClass;

sub new {
    my ($class, $url) = @_;
    my $self = {
        url => $url,
    };
    bless $self, $class;
    return $self;
}

sub fetch_content {
    my $self = shift;
    my $content = get($self->{url});
    die "Failed to fetch content from URL: $self->{url}" unless defined $content;
    return $content;
}

# Main program
my $url = "https://www.example.com";
my $object = MyClass->new($url);

eval {
    my $content = $object->fetch_content();
    print "Content from $url:\n$content\n";
};
if ($@) {
    warn "An error occurred: $@";
}
```

#### Running the Script:
Save the above code in a file (e.g., advanced_example.pl) and execute it using the Perl interpreter:

```bash
perl advanced_example.pl
```

You've learned about advanced topics in Perl, including modules, error handling, and object-oriented programming. These concepts will be valuable as you continue to develop more complex Perl applications. If you have any questions, feel free to ask!

### Lesson 8: Interacting with the Operating System in Perl

Perl provides powerful features for interacting with the operating system, including executing external commands, manipulating files and directories, and handling processes.

#### Executing External Commands:
You can execute external commands using backticks `` or the `system` function.

- **Using Backticks:**
  ```perl
  my $output = `ls -l`;
  print "Output of ls -l:\n$output\n";
  ```

- **Using system Function:**
  ```perl
  system("ls", "-l");
  ```

#### File and Directory Operations:
Perl provides functions for working with files and directories, such as `open`, `close`, `mkdir`, `rmdir`, `chdir`, `unlink`, etc.

- **Creating a Directory:**
  ```perl
  mkdir("new_directory") or die "Cannot create directory: $!";
  ```

- **Reading Directory Contents:**
  ```perl
  opendir(my $dir_handle, ".") or die "Cannot open directory: $!";
  while (my $file = readdir($dir_handle)) {
      print "File: $file\n";
  }
  closedir($dir_handle);
  ```

#### Process Management:
Perl allows you to manage processes using functions like `fork`, `wait`, and `kill`.

- **Forking a Process:**
  ```perl
  my $pid = fork();
  if ($pid == 0) {
      # Child process
      print "Child process\n";
  } elsif ($pid > 0) {
      # Parent process
      print "Parent process\n";
  } else {
      die "Failed to fork: $!";
  }
  ```

- **Waiting for Child Processes:**
  ```perl
  my $child_pid = wait();
  print "Child process with PID $child_pid has exited\n";
  ```

#### Example Program:
Let's write a program that creates a directory, lists its contents, and executes an external command.

```perl
#!/usr/bin/perl
use strict;
use warnings;

# Create a directory
mkdir("new_directory") or die "Cannot create directory: $!";

# List directory contents
opendir(my $dir_handle, ".") or die "Cannot open directory: $!";
while (my $file = readdir($dir_handle)) {
    print "File: $file\n";
}
closedir($dir_handle);

# Execute an external command
system("ls", "-l");
```

#### Running the Script:
Save the above code in a file (e.g., os_interactions.pl) and execute it using the Perl interpreter:

```bash
perl os_interactions.pl
```

You've learned how to interact with the operating system in Perl, including executing external commands, manipulating files and directories, and managing processes. These features are essential for many real-world Perl applications. If you have any questions, feel free to ask!

### Lesson 9: Working with Regular Expressions in Perl (Continued)

#### More Advanced Regular Expression Features:

#### Grouping:
You can group parts of a regular expression together using parentheses `()`.

```perl
my $string = "The quick brown fox";
if ($string =~ /(quick).*(fox)/) {
    print "Match: $1 $2\n";
}
```

#### Backreferences:
You can reference captured groups in a regular expression using `\1`, `\2`, etc.

```perl
my $string = "hello hello";
if ($string =~ /(hello) \1/) {
    print "Repeated word: $1\n";
}
```

#### Anchors:
Anchors are used to match a pattern at the beginning or end of a string.

- `^`: Matches the start of a string.
- `$`: Matches the end of a string.

```perl
my $string = "start middle end";
if ($string =~ /^start/) {
    print "Start of the string matched!\n";
}
if ($string =~ /end$/) {
    print "End of the string matched!\n";
}
```

#### Quantifiers:
Quantifiers can be greedy or non-greedy.

- Greedy: Matches as much as possible.
- Non-greedy: Matches as little as possible.

```perl
my $string = "abbc";
if ($string =~ /(b+)/) {
    print "Greedy match: $1\n";
}
if ($string =~ /(b+?)/) {
    print "Non-greedy match: $1\n";
}
```

#### Lookahead and Lookbehind Assertions:
Lookahead and lookbehind assertions match a pattern without consuming characters.

- **Positive Lookahead `(?=...)`**: Matches if the pattern inside the lookahead matches next.
- **Negative Lookahead `(?!...)`**: Matches if the pattern inside the lookahead does not match next.
- **Positive Lookbehind `(?<=...)`**: Matches if the pattern inside the lookbehind matches behind.
- **Negative Lookbehind `(?<!...)`**: Matches if the pattern inside the lookbehind does not match behind.

```perl
my $string = "apple orange banana";
if ($string =~ /(\w+)\s+(?=\w+)/) {
    print "Matched word followed by a word: $1\n";
}
```

#### Example Program:
Let's write a program that extracts phone numbers from a given text using regular expressions with lookahead assertions:

```perl
#!/usr/bin/perl
use strict;
use warnings;

my $text = "Contact us at 123-456-7890 or 987-654-3210";

while ($text =~ /(\d{3}-\d{3}-\d{4})(?=\D|$)/g) {
    print "Phone number: $1\n";
}
```

#### Running the Script:
Save the above code in a file (e.g., regex_advanced.pl) and execute it using the Perl interpreter:

```bash
perl regex_advanced.pl
```

You've learned about more advanced features of regular expressions in Perl, including grouping, backreferences, anchors, quantifiers, and assertions. These techniques are useful for more complex pattern matching tasks. If you have any questions, feel free to ask!

### Lesson 10: Handling Exceptions and Error Logging in Perl

#### Exception Handling with `eval`

Perl provides the `eval` function to catch exceptions and handle errors gracefully.

```perl
eval {
    # Code that might throw an exception
};
if ($@) {
    print "An error occurred: $@\n";
}
```

#### Using `die` and `warn` for Error Reporting

- **die**: Terminates the program immediately and prints an error message.
  
  ```perl
  open(my $fh, '<', $filename) or die "Cannot open file: $!";
  ```

- **warn**: Prints a warning message but allows the program to continue executing.

  ```perl
  if ($age < 0) {
      warn "Age cannot be negative!";
  }
  ```

#### Logging Errors to a File

You can log errors to a file using the `Log::Log4perl` module.

```perl
use Log::Log4perl;

Log::Log4perl->init("log.conf");

my $logger = Log::Log4perl->get_logger();

eval {
    # Code that might throw an exception
};
if ($@) {
    $logger->error("An error occurred: $@");
}
```

#### Example Program: Exception Handling and Logging

Let's write a program that attempts to open a file, handles any exceptions, and logs errors to a file.

```perl
#!/usr/bin/perl
use strict;
use warnings;
use Log::Log4perl;

# Initialize logger
Log::Log4perl->init("error.log.conf");
my $logger = Log::Log4perl->get_logger();

# Attempt to open file
my $filename = "non_existent_file.txt";
eval {
    open(my $fh, '<', $filename) or die "Cannot open file: $!";
};
if ($@) {
    $logger->error("An error occurred: $@");
}
```

#### Running the Script

Save the above code in a file (e.g., error_handling.pl) and create a Log4perl configuration file (e.g., error.log.conf) with the appropriate logging settings. Then, execute the script using the Perl interpreter:

```bash
perl error_handling.pl
```

#### Conclusion

You've learned how to handle exceptions and errors gracefully in Perl using `eval`, `die`, and `warn`, as well as how to log errors to a file using the `Log::Log4perl` module. These techniques are essential for building robust Perl applications. If you have any questions or need further clarification, feel free to ask!

