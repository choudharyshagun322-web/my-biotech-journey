# Stage 0: Mastering the Command Line Interface (CLI)

For a biologist entering bioinformatics, the command line is your new digital laboratory. It's where you'll run analyses, manage massive datasets, and automate your work. This stage will give you the foundational skills to navigate this powerful environment.

## Why the Terminal is Your Best Friend

*   **Power & Flexibility:** GUIs (Graphical User Interfaces) are easy, but they are limiting. The CLI allows you to chain commands together to perform complex tasks that would be impossible with a mouse.
*   **Automation:** You can write scripts to automate repetitive tasks, saving you countless hours.
*   **Server Access:** Most high-performance computing (HPC) clusters and cloud servers, where you'll do heavy-duty bioinformatics work, do not have a graphical interface. You *must* know the command line to use them.

## Your First Steps in the Ubuntu/Linux Terminal

### Core Commands Every Bioinformatician Must Know

| Command | Description | Example |
|---|---|---|
| `ls` | **L**i**s**t files and directories. | `ls -lh` (long, human-readable) |
| `pwd` | **P**rint **W**orking **D**irectory (shows where you are). | `pwd` |
| `cd` | **C**hange **D**irectory. | `cd /home/user/data` |
| `cp` | **C**o**p**y a file or directory. | `cp file1.txt file2.txt` |
| `mv` | **M**o**v**e or rename a file. | `mv old_name.txt new_name.txt` |
| `rm` | **R**e**m**ove a file. **(Use with caution!)** | `rm sample.fasta` |
| `mkdir` | **M**a**k**e a new **d**i**r**ectory. | `mkdir new_project` |
| `cat` | Con**cat**enate and print file content. | `cat file.txt` |
| `head` | Show the first 10 lines of a file. | `head data.csv` |
| `tail` | Show the last 10 lines of a file. | `tail data.csv` |
| `grep` | Search for a pattern in a file. | `grep "gene_name" annotation.gff` |

### Navigating the Filesystem

*   `.` refers to your **current** directory.
*   `..` refers to the **parent** directory (one level up).
*   `~` refers to your **home** directory.
*   `/` is the **root** directory of the entire filesystem.

**Pro Tip:** Use the `Tab` key for auto-completion. Start typing a command or filename and press `Tab`—the shell will try to finish it for you. This reduces typos and saves time.

## `nano`: Your First Command-Line Text Editor

`nano` is a simple, beginner-friendly text editor.

*   **Open or create a file:** `nano my_script.py`
*   **Save:** `Ctrl + O` (Write **O**ut)
*   **Exit:** `Ctrl + X`
*   The commands are always visible at the bottom of the screen.

## `neofetch`: Show Off Your System

`neofetch` is a fun command that displays a logo of your Linux distribution along with system information. It's a great way to quickly check your OS version, kernel, and hardware.

To install it: `sudo apt update && sudo apt install neofetch`
To run it: `neofetch`

## Essential Tips for Terminal Use

1.  **Don't Fear the Manual:** The `man` command gives you the manual for any other command. Example: `man ls` will teach you all about the `ls` command's options.
2.  **Redirection is a Superpower:**
    *   `>`: Redirects output to a file (overwrites the file).
        *   `ls -l > file_list.txt` (saves the file list to a text file)
    *   `>>`: Appends output to a file.
        *   `echo "New sample" >> samples.txt` (adds a new line to the file)
3.  **Piping (`|`) Chains Commands:** Use the output of one command as the input for another. This is the key to building powerful workflows.
    *   `cat data.fastq | grep "@read_id" | head -n 5`
        *   This pipeline reads a FASTQ file, finds all the read ID lines, and shows you just the first 5.

## Basic File and Format Operations

As a bioinformatician, you'll constantly be looking at text files.

*   **Check file type:** `file my_data.bam`
*   **Count lines/words/characters:** `wc -l my_sequences.fasta` (counts lines)
*   **Compressing files (essential for large data):**
    *   `gzip my_large_file.fastq` (compresses to `.gz`)
    *   `gunzip my_large_file.fastq.gz` (decompresses)
*   **Viewing compressed files without decompressing:**
    *   `zcat file.fastq.gz | head` (view the top of a gzipped file)
