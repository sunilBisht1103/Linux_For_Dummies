## 1.grep

grep command is a powerful tool used for searching and matching patterns in text files.

```bash
grep "fox" sample.txt
```

The grep command searches the file and prints out the lines that contain the specified pattern, in this case, "fox".

Options

i option makes the search case-insensitive, so it will match both "dog" and "Dog".

-v command is used to exclude lines that match the given pattern.

-n option adds the line number before each matching line.

-E option enables extended regular expressions, 

```bash
grep -E "dog.*lazy|lazy.*dog" sample.txt
```

## 2.sed

sed command is a powerful tool for text processing and editing, allowing you to perform various operations on text files.

print the entire contents of the file, use the following command:

```bash
sed 's/.*/' sample.txt
```

To print a specific line, use the line number with the p command:

```bash
sed -n '2p' sample.txt
```

To substitute text, use the s command followed by the pattern and replacement:

```bash
sed 's/sample/new/' sample.txt
```

To delete a specific line, use the d command followed by the line number:

```bash
sed '2d' sample.txt
```
To insert text before a line, use the i command. To append text after a line, use the a command:

```bash
sed '2i This is an inserted line.' sample.txt
sed '2a This is an appended line.' sample.txt
```

To replace all occurrences of a word, use the global g flag:

```bash
sed 's/old/new/g' sample.txt
```

To replace text on a specific line, use the line number before the s command:

```bash
sed '1s/old/new/' sample.txt
```

## 3.awk

awk command is a powerful text processing tool that can be used for a variety of tasks, such as data extraction, manipulation, and analysis.

awk 'pattern {action}' file

print the second field (age) of each line:

```bash
awk -F',' '{print $2}' data.txt
```
-F',' option tells awk to use the comma , as the field separator. The {print $2} action tells awk to print the second field of each line.

 print the name and department of people older than 30:

 ```bash
awk -F',' '$2 > 30 {print $1, $3}' data.txt
```

## 4.cut

cut command is a powerful tool for extracting specific columns or fields from a text file or the output of a command.

 ```bash
cut -d ' ' -f 2,4 file.txt
```
In this command:

cut is the command name

-d ' ' specifies the delimiter (in this case, a space) to use when splitting the input

-f 2,4 tells cut to extract the 2nd and 4th fields (columns) from each line

other options:

-c: Extract characters instead of fields

-b: Extract bytes instead of fields

--complement: Select the complement of the set of bytes, characters or fields

-s: Only output lines with delimiter characters


 ```bash
cut -c 1-5,10-15 file.txt
```

extracts the characters from positions 1 to 5, and 10 to 15 from each line in the file.

--output-delimiter option to change the delimiter in the output:

## 5.Sort

sort command is used to sort the lines of a file or the output of a command in a specific order.


 ```bash
sort data.txt
```

The sort command has several options that allow you to customize the sorting behavior. Some common options include:

-r: Sort in reverse order (descending)

-n: Sort numerically

-k <field>: Sort based on a specific field or column

-t <delimiter>: Use a custom field delimiter

 ```bash
sort -t ',' -k 2n data2.txt
```
The n option in -k 2n tells sort to sort the second field numerically.

## 6.Head

head command is a useful tool for quickly viewing the contents of a file, especially when dealing with large files.

 ```bash
head example.txt

head -n 5 example.txt

head -c 20 example.txt
```
-c, which allows you to display a specific number of bytes instead of lines.

## 7.Tail

tail command is used to display the last few lines of a file or the output of a command.

tail [options] [file]

the most common options for the tail command are:

-n: Specifies the number of lines to display. For example, tail -n 5 file.txt will display the last 5 lines of the file.
-f: Follows the file, continuously displaying new lines as they are added to the file. This is useful for monitoring log files.
tail -f sample.log

## 8.wc

wc command is a powerful tool that allows you to count the number of lines, words, and characters in a file.


 ```bash
wc sample.txt
```


 ```text
 1  7 28 sample.txt
```

The output shows that the file has 1 line, 7 words, and 28 characters.

 ```bash
wc -l sample.txt ## Count lines

wc -w sample.txt ## Count words

wc -c sample.txt ## Count characters

```


## 9.Diff

diff command is a powerful tool used to compare the contents of two files and display the differences between them.

 ```bash
diff file1.txt file2.txt
```

Some common options for the diff command include:

-c: Display the differences in a context format, showing the lines around the changes.
-u: Display the differences in a unified format, showing the lines around the changes.
-r: Recursively compare directories and their contents.
-w: Ignore white space differences

## 10.vi
vi is a powerful and widely-used text editor in the Linux environment, and understanding its fundamentals is crucial for efficient text processing.
