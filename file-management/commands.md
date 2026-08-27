# Linux File Management Commands

## 1. pwd — Print Working Directory

Shows the current working directory.

**2. ls — List Files and Directories**
ls
ls -l
ls -a
ls -la
ls -lh
ls -lt
ls -ltr
ls -R

ls → List files
ls -l → Detailed listing
ls -a → Show hidden files
ls -la → Detailed + hidden files
ls -lh → Human-readable sizes
ls -lt → Sort by modification time
ls -ltr → Reverse modification time
ls -R → Recursive listing

**3. cd — Change Directory**
cd /var/log
cd ..
cd .
cd ~
cd -
cd /

cd .. → Parent directory
cd ~ → Home directory
cd - → Previous directory
cd / → Root directory

**4. mkdir — Create Directory**
mkdir test
mkdir test1 test2 test3
mkdir -p project/logs/application

mkdir → Create directory
mkdir -p → Create parent directories if required

**5. rmdir — Remove Empty Directory**
rmdir test
rmdir test1 test2

Only removes empty directories.

**6. touch — Create File**
touch test.txt
touch file1.txt file2.txt file3.txt

Also updates the timestamp of an existing file:

touch existing.txt

**7. cp — Copy Files and Directories**
Copy a file:

cp file.txt backup.txt

Copy to another directory:

cp file.txt /tmp/

Copy multiple files:

cp file1.txt file2.txt /tmp/

Copy a directory:

cp -r project backup-project

Useful options:

cp -i file.txt backup.txt
cp -v file.txt backup.txt
cp -r folder1 folder2
cp -a project project-backup

-i → Ask before overwrite
-v → Verbose output
-r → Recursive copy
-a → Archive/preserve attributes

**8. mv — Move or Rename**
Rename a file:

mv old.txt new.txt

Move a file:

mv file.txt /tmp/

Move multiple files:

mv file1.txt file2.txt /tmp/

Useful options:

mv -i file.txt /tmp/
mv -v file.txt /tmp/

-i → Ask before overwrite
-v → Verbose output

**9. rm — Remove Files and Directories**
Remove a file:

rm file.txt

Remove multiple files:

rm file1.txt file2.txt

Remove a directory:

rm -r folder

Force removal:

rm -f file.txt

Force recursive removal:

rm -rf folder

WARNING: Be very careful with rm -rf.

**10. find — Search for Files and Directories**
Find a file:

find . -name "test.txt"

Find .log files:

find . -name "*.log"

Case-insensitive search:

find . -iname "*.log"

Find files:

find . -type f

Find directories:

find . -type d

Find files larger than 100 MB:

find . -type f -size +100M

Find files modified within the last day:

find . -type f -mtime -1

Find empty files:

find . -type f -empty

Find files by permission:

find . -type f -perm 644

Find files owned by a user:

find . -type f -user username

**11. file — Identify File Type**
file test.txt
file image.png
file application.log

Example:

test.txt: ASCII text

**12. stat — Display File Information**
stat test.txt

Displays:

File size
Permissions
Owner
Group
Access time
Modify time
Change time
Inode
**13. cat — Display File Contents**
cat test.txt

Display multiple files:

cat file1.txt file2.txt

Combine files:

cat file1.txt file2.txt > combined.txt

Append content:

cat file1.txt >> combined.txt

**14. less — View Large Files**
less application.log

Useful keys inside less:

Space   → Next page
b       → Previous page
/ERROR  → Search for ERROR
n       → Next search result
q       → Quit

Very useful for large log files.

**15. more — View Files Page by Page**
more application.log

less is generally more powerful and commonly preferred.

**16. head — Display Beginning of File**
head test.txt

First 20 lines:

head -20 test.txt

First 50 lines:

head -50 application.log

**17. tail — Display End of File**
tail test.txt

Last 20 lines:

tail -20 application.log

Monitor a log continuously:

tail -f application.log

This is very useful for QA and DevOps when monitoring application/test logs.

**18. ln — Create Links**
Create a hard link:

ln original.txt link.txt

Create a symbolic link:

ln -s original.txt link.txt

Symbolic link to a directory:

ln -s /var/log application-logs

**19. readlink — Read Symbolic Link**
readlink link.txt

Get the actual target:

readlink -f link.txt

**20. realpath — Get Absolute Path**
realpath test.txt

Example output:

/home/user/project/test.txt

**21. basename — Extract File Name**
basename /home/user/test.txt

Output:

test.txt

**22. dirname — Extract Directory Name**
dirname /home/user/test.txt

Output:

/home/user

**23. du — Check File/Directory Size**
Check file size:

du file.txt

Human-readable:

du -h file.txt

Check directory size:

du -sh project/

Check sizes of directories:

du -h --max-depth=1

**24. df — Check Disk Space**
df

Human-readable:

df -h

Check a specific filesystem:

df -h /home

Useful for troubleshooting disk-space problems.

**25. tree — Display Directory Structure**
If installed:

tree

Limit depth:

tree -L 2

Example:

project/
├── logs/
│   ├── application.log
│   └── error.log
├── scripts/
│   └── run.sh
└── README.md

**26. rename — Rename Multiple Files**
On systems using Perl rename:

rename 's/.txt/.bak/' *.txt

Note: rename syntax can vary between Linux distributions.

**27. truncate — Change File Size**
Empty a file:

truncate -s 0 application.log

Set file size:

truncate -s 10K test.txt

**28. shred — Overwrite a File**
shred file.txt

Overwrite and remove:

shred -u file.txt

Note: Secure deletion is not guaranteed on every filesystem/storage type.


