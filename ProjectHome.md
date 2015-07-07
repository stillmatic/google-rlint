## About ##
**_RLint_** both checks and reformats R code to the [Google R Style Guide](https://google-styleguide.googlecode.com/svn/trunk/Rguide.xml). It warns of violations and optionally produces compliant code. It considers proper spacing, line alignment inside brackets, and other style violations, but like all lint programs does not try to handle all syntax issues.

Code that follows a uniform style eases maintenance, modification, and ensuring correctness, especially when multiple programmers are involved.  Thus, **_RLint_** is automatically used within Google as part of the peer review process for R code.  We encourage CRAN package authors and other R programmers to use this tool.  A user can run the open-source Python-based program in a Linux, Unix, Mac or Windows machine via a command line.

## Code Availability ##

As of 2014-07-02, the code is being finalized and will be tested within Google for a few weeks before release here.

## Usage ##
```
[python] rlint.py [-h] [--verbose [T|F]] [--fix [T|F] | --overwrite [T|F]] [file [file ...]]
```
or read the input from stdin
```
[python] rlint.py [--verbose [T|F]] [--fix [T|F] | --overwrite [T|F]] < yourinput.R [> youroutput.R]
```
All logical flags can be given as either T or True, F or False, or nothing, --e.g. --verbose is equivalent to --verbose T.

**Flags**:

positional arguments:
```
  file                  R files to analyze for style warnings and errors.
```

optional arguments:
```
  --help -h             show this help message and exit
  --verbose [T|F], -v [T|F]
                        If False, print a summary of errors and warnings. If True, print all error and warnings.
  --fix [T|F], -f [T|F]
                        Generate corrected R code, writing a new file under a system temporary directory, e.g.,
                        /tmp on Linux or Unix. This is ignored if --overwrite True or when processing
                        standard input.
  --overwrite [T|F], -o [T|F]
                        If True, then overwrite the file with corrected code or, if processing standard input, send
                        to the standard output. May not be used with --fix.
```

## Presentations ##

<a href='https://code.google.com/p/google-rlint/wiki/Documentation'>R User Conference 2014-07-02</a>