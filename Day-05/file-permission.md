## Challenge Tasks

### Task 1: Create Files

1. Create empty file `devops.txt` using `touch`
2. Create `notes.txt` with some content using `cat` or `echo`
3. Create `script.sh` using `vim` with content: `echo "Hello DevOps"`

**Verify:** `ls -l` to see permissions
![alt text](image-1.png)


-- 

1. Create empty file `devops.txt` using `touch`.
>> touch devops.txt

2. Create `notes.txt` with some content using `cat` or `echo`
>> cat > notes.txt

3. Create `script.sh` using `vim` with content: `echo "Hello DevOps"`
>> vim script.sh


**Verify:** `ls -l` to see permissions
>>
ubuntu@ip-172-31-9-119:~$ ls -l
total 8
-rw-rw-r-- 1 ubuntu ubuntu  0 Jul  1 05:41 devops.txt
-rw-rw-r-- 1 ubuntu ubuntu 46 Jul  1 05:49 notes.txt
-rw-rw-r-- 1 ubuntu ubuntu 15 Jul  1 05:51 script.sh

--


**Task 2: Read Files**

1. Read `notes.txt` using `cat`
2. View `script.sh` in vim read-only mode
3. Display first 5 lines of `/etc/passwd` using `head`
4. Display last 5 lines of `/etc/passwd` using `tail`


1. Read `notes.txt` using `cat`
>> cat notes.txt

2. View `script.sh` in vim read-only mode.
>> vim script.sh

3. Display first 5 lines of `/etc/passwd` using `head`.
>> head -n 5 /etc/passwd

4. Display last 5 lines of `/etc/passwd` using `tail`
>> tail -n 5 /etc/passwd

--

### Task 3: Understand Permissions 

Format: `rwxrwxrwx` (owner-group-others)
- `r` = read (4), `w` = write (2), `x` = execute (1)

Check your files: `ls -l devops.txt notes.txt script.sh`

Answer: What are current permissions? Who can read/write/execute?

>>
ubuntu@ip-172-31-9-119:~$ ls -l devops.txt  notes.txt  script.sh
-rw-rw-r-- 1 ubuntu ubuntu  0 Jul  1 05:41 devops.txt
-rw-rw-r-- 1 ubuntu ubuntu 46 Jul  1 05:49 notes.txt
-rw-rw-r-- 1 ubuntu ubuntu 15 Jul  1 06:03 script.sh

>>
ubuntu@ip-172-31-9-119:~$ chmod 777 devops.txt
ubuntu@ip-172-31-9-119:~$ ls -l devops.txt
-rwxrwxrwx 1 ubuntu ubuntu 0 Jul  1 05:41 devops.txt

>>
ubuntu@ip-172-31-9-119:~$ chmod u=rwx,g=rw,o=r devops.txt

--

### Task 4: Modify Permissions 

1. Make `script.sh` executable → run it with `./script.sh`
2. Set `devops.txt` to read-only (remove write for all)
3. Set `notes.txt` to `640` (owner: rw, group: r, others: none)
4. Create directory `project/` with permissions `755`

**Verify:** `ls -l` after each change


1. Make `script.sh` executable → run it with `./script.sh`
>>
ubuntu@ip-172-31-9-119:~$ ls -l script.sh
-rw-rw-r-- 1 ubuntu ubuntu 15 Jul  1 06:03 script.sh
>>
chmod 764 script.sh (so the user now can execute the file)
>>
./script.sh

---

2. Set `devops.txt` to read-only (remove write for all)
>>
ubuntu@ip-172-31-9-119:~$ ls -l devops.txt
-rwxrw-r-- 1 ubuntu ubuntu 0 Jul  1 05:41 devops.txt
>>
ubuntu@ip-172-31-9-119:~$ chmod 444 devops.txt
>>
ubuntu@ip-172-31-9-119:~$ ls -l devops.txt
-r--r--r-- 1 ubuntu ubuntu 0 Jul  1 05:41 devops.txt


---

3. Set `notes.txt` to `640` (owner: rw, group: r, others: none)
>>
ubuntu@ip-172-31-9-119:~$ ls -l notes.txt
-rw-rw-r-- 1 ubuntu ubuntu 46 Jul  1 05:49 notes.txt
>>
ubuntu@ip-172-31-9-119:~$ chmod 640 notes.txt
>>
ubuntu@ip-172-31-9-119:~$ ls -l notes.txt
-rw-r----- 1 ubuntu ubuntu 46 Jul  1 05:49 notes.txt


---

4. Create directory `project/` with permissions `755`
>>
ubuntu@ip-172-31-9-119:~$ mkdir project
>>
ubuntu@ip-172-31-9-119:~$ ls
devops.txt  notes.txt  project  script.sh
>>
ubuntu@ip-172-31-9-119:~$ chmod 755 project
>>
ubuntu@ip-172-31-9-119:~$ ls -ld project
drwxr-xr-x 2 ubuntu ubuntu 4096 Jul  1 10:12 project


---



### Task 5: Test Permissions

1. Try writing to a read-only file - what happens?
 - If we tired writing the ready only file it will show permission denied.
2. Try executing a file without execute permission
 
 ![alt text](image-5.png)
 
3. Document the error messages


--


1. Try writing to a read-only file - what happens?
 - If we tired writing the ready only file it will show permission denied.
>>
ubuntu@ip-172-31-9-119:~$ ls -l devops.txt
-r--r--r-- 1 ubuntu ubuntu 0 Jul  1 05:41 devops.txt
>>
ubuntu@ip-172-31-9-119:~$ cat > devops.txt
-bash: devops.txt: Permission denied


2. Try executing a file without execute permission
>>
ubuntu@ip-172-31-9-119:~$ ls -l devops.txt
-r--r--r-- 1 ubuntu ubuntu 0 Jul  1 05:41 devops.txt
>>
ubuntu@ip-172-31-9-119:~$ ./devops.txt
-bash: ./devops.txt: Permission denied


---

Day 5 task complete