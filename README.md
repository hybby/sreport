[![Build Status](https://travis-ci.org/hybby/sreport.svg?branch=main)](https://travis-ci.org/hybby/sreport)

# sreport
## Overview
A Python program to make HTTP(S) requests and report on the results.

Provide a newline serperated list of URLs as `stdin` and each will be tested
in turn. A summary report will be output after all URLs have been processed

```
$ ./sreport.py < test.txt
{
    "Url": "https://www.google.com",
    "Status_code": 200,
    "Date": "Sun, 04 Oct 2020 20:43:44 GMT"
}
[
    {
        "Status_code": 200,
        "Number_of_responses": 1
    },
    {
        "Number_of_responses": 1
    }
]
```

Requests will time out after 10 seconds and redirects will be followed.


## Getting Started
### Help?
Embedded help is built into the provided Makefile.  Just run:

```
make
```

### Installation
This script requires Python 3.

Install the script's dependencies:

```
make requirements
```

### Running
#### One URL
```
echo "https://www.google.com" | ./sreport.py
```

#### A file of multiple URLs
Run for a list of sites, contained within a file:

```
echo "https://www.google.com" >  urls.txt
echo "https://www.gmail.com"  >> urls.txt

./sreport.py < urls.txt
```

### Testing
The following tests are provided:

  * `pycodestyle` - ([PEP8](http://www.python.org/dev/peps/pep-0008/)) code style checks
  * `pylint` - Code linting checks
  * `pytest` - Unit tests

These can be run by using the provided Makefile:

```
make test
```
