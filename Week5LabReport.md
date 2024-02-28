# Week 5 Lab Report by Gabriel Renslow

# `Part 1 - Bugs`

# Failure Inducing Test
```int[] input1 = { 1, 2, 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
```
# Non-Failure Inducing Test
```int[] input1 = { 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3 }, input1);
```
# Sympton

![Image](Week5_Part1.png)

# Bug/Solution

Before
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

After
```
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      temp[i] = arr[arr.length - i - 1];
    }
    for(int i = 0; i < arr.length; i +=1) {
      arr[i] = temp[i];
    }
  }
```

# Explanation

In the before section, the loop was editing the array itself that was being used as a source of information, and so as the array was being changed, some essential data was lost. To fix this I implemented a temperorary array system that was copied over at the end.

# `Part 2 - Researching Commands`

Today I will be talking about the 'grep' command.

# 4 examples on txt files

```grep -v "error" log.txt```
This will display all lines that do NOT include 'error'

```grep -l "pattern" *.txt```
This will list of all the names of .txt files that have "pattern" in the name in the current directory

```grep -c "pattern" file.txt```
This will count the amount of lines including "pattern" in 'file.txt'

```grep -E "word1|word2" file.txt```
This will print all lines from file.txt containing either 'word1' or 'word2'

# 4 examples on directories files

```grep -rv "debug" ./src/```
This command will search all files under the ./src/ directory and display lines that do NOT have the word "debug".

```grep -rl "function" ./src/```
This command will search all files under the ./src/ directory and list the names of files that have the word "function".

```grep -rc "error" ./logs/```
This command will search all files under the ./logs/ directory and print the amount of lines containing the word "error" in each file.

```grep -Er "pattern1.*pattern2" ./dir/```
This command will search all files under the ./dir/ directory using the extended regular expression "pattern1.*pattern2".

# 'Citation'

I thought the instructions given for Part 2 served as a pretty good prompt, so I used it in ChatGPT.

# Prompt
```
Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose. To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works. Also consider asking ChatGPT!

For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.
```

# Output

### 1. `-v` Option (Invert Match)
**Description:** The `-v` option inverts the match, meaning it selects non-matching lines.

**Example 1: Using on Files**
```bash
grep -v "error" log.txt
```
**Output:** This command will display all lines from `log.txt` that do not contain the word "error".

**Example 2: Using on Directories**
```bash
grep -rv "debug" ./src/
```
**Output:** This command will recursively search all files under the `./src/` directory and display lines that do not contain the word "debug".

**Source:** I found out about the `-v` option from the official GNU Grep documentation: [GNU Grep Manual](https://www.gnu.org/software/grep/manual/grep.html)

### 2. `-l` Option (Print Only File Names)
**Description:** The `-l` option prints only the names of files containing matching lines.

**Example 1: Using on Files**
```bash
grep -l "pattern" *.txt
```
**Output:** This command will list the names of all `.txt` files in the current directory that contain the pattern "pattern".

**Example 2: Using on Directories**
```bash
grep -rl "function" ./src/
```
**Output:** This command will recursively search all files under the `./src/` directory and list the names of files that contain the word "function".

**Source:** I learned about the `-l` option from the Stack Overflow post [How do I find all files containing specific text on Linux?](https://stackoverflow.com/questions/16956810/how-do-i-find-all-files-containing-specific-text-on-linux)

### 3. `-c` Option (Count Matching Lines)
**Description:** The `-c` option displays only a count of matching lines.

**Example 1: Using on Files**
```bash
grep -c "pattern" file.txt
```
**Output:** This command will display the count of lines containing the pattern "pattern" in `file.txt`.

**Example 2: Using on Directories**
```bash
grep -rc "error" ./logs/
```
**Output:** This command will recursively search all files under the `./logs/` directory and display the count of lines containing the word "error" in each file.

**Source:** I found information about the `-c` option from the Linux man page for `grep` (`man grep`).

### 4. `-E` Option (Use Extended Regular Expressions)
**Description:** The `-E` option enables the use of extended regular expressions in `grep`.

**Example 1: Using on Files**
```bash
grep -E "word1|word2" file.txt
```
**Output:** This command will search for lines containing either "word1" or "word2" in `file.txt`.

**Example 2: Using on Directories**
```bash
grep -Er "pattern1.*pattern2" ./dir/
```
**Output:** This command will recursively search all files under the `./dir/` directory using the extended regular expression "pattern1.*pattern2".

**Source:** I found information about the `-E` option from the Linux man page for `grep` (`man grep`).

