Objective

The objective is to identify duplicate assignment submissions, create backups of unique submissions, generate a report showing the processing results, and store error messages separately.

Solution Explanation

The shell script processes the files in the submissions directory one by one. It calculates a SHA-256 hash for each file and compares the hash with previously processed files. If two files have the same hash, they have identical content and the second file is identified as a duplicate.

Unique files are copied to the backup directory. The script also maintains counters for the total number of files processed, duplicate files, and unique files backed up.

Commands and Their Purpose
mkdir

The mkdir command creates directories such as the submissions directory and the backup directory. These directories organize the input files and their backups.

echo

The echo command creates sample submission files and writes content into them. It is useful for generating test data for the script.

ls

The ls command lists files and directories. It was used to verify the contents of the submissions and backup directories.

cat

The cat command displays the contents of a file. It was used to compare submission contents and view the generated report.

cp

The cp command copies files. It was used to create a duplicate submission for testing and to back up unique submissions.

chmod +x

The chmod +x command gives execute permission to the shell script. This allows the script to be executed directly using ./script_name.

shasum -a 256

The shasum -a 256 command calculates the SHA-256 hash of a file. Files with identical contents produce the same hash, making hash comparison an efficient method for detecting duplicate submissions.

awk

The awk command extracts specific fields from command output. In this solution, it can be used to extract the hash value from the output of shasum.

>

The > redirection operator creates a new file or overwrites an existing file. It can be used to clear or initialize the report and error files.

>>

The >> redirection operator appends output to an existing file without deleting its previous contents. It is used to add processing information and duplicate details to the report.

2>>

The 2>> operator redirects standard error messages to a file. In this solution, errors are stored separately in errors.log.

File-Handling Techniques

The script processes regular files from the submissions directory. A hash is calculated for each file and compared with previously processed hashes. If a matching hash is found, the file is considered a duplicate. Otherwise, it is copied to the backup directory.

Result

The script successfully processed the submissions, detected duplicate files, backed up unique submissions, generated a report, and stored error messages separately.
