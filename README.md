#Tables
##Description
'Tables' automatically places guests at any number of tables, keeping their party together as much as possible. This tool was inspired by the need to place different families at our wedding.

##Synopsis
```bash
Tables [options] -g GUEST_FILE
```

##Options
'Tables' supports a multitude of options including:
1. `-g GUEST_FILE`: Read in a list of attendees with the format described below
2. `-t (t, p)`: Assume `t` tables with `p` people each. Cannot be used with `-T`
3. `-T TABLE_FILE`: Read in a list of table properties with the format described below. Cannot be used with `-t`
4. `-o OUTPUT_FILE`: Output file (defaults to current directory with name of `GUEST_FILE.tables`)
5. `-i`: Interactive mode
6. `-d`: Diagram output
7. `-v`: Operate in verbose mode
8. `-q`: Quiet mode
9. `-h`: Display the help

##Guest File
The `GUEST_FILE` must be a CSV file with the following format:
```
Name, Guest Count, Has Children (true/false)
```

For example:
```
Paniagua Family, 5, true
Gibson Family, 2, false
Ricky and Julian, 2, false
Bubbles, 1, false
```

##Table File
The `TABLE_FILE` must be a file with the following format:
```
$Regular Tables
(t, p)

$Special Tables
(n0, p0)
(n1, p1)
...
```

For example:
```
$Regular Tables
(10, 6)

$Special Tables
(Long Table, 8)
(Short Table, 4)
```

##Output File
The `OUPUT_FILE` will be a `.tables` file with the following format:
```
Total Number of Guests:
    Total Number

Total Number of Seats:
    Total Number

Table Number 1:
    Party Name 1    [Guest Count]   [Split Indicator]
    Party Name 2    [Guest Count]   [Split Indicator]
    ...

Table Number 2:
    Party Name 3    [Guest Count]   [Split Indicator]
    ...

...
```

If the `-d` flag is included, an ASCII art representation of the table will also be displayed
