# Challenge Tasks



## Task 4: Shared Directory (20 minutes)

1. Create directory: `/opt/dev-project`
2. Set group owner to `developers`
3. Set permissions to `775` (rwxrwxr-x)
4. Test by creating files as `tokyo` and `berlin`

**Verify:** Check permissions and test file creation


--  

### Task 1: Create Users (20 minutes)

Create three users with home directories and passwords:
- `tokyo`
- `berlin`
- `professor`

1> sudo adduser tokyo
    password : xxxxxxx
2> sudo adduser berlin
    password : xxxxxxx
3> sudo adduser professor
    password : xxxxxxx


**Verify:** Check `/etc/passwd` and `/home/` directory

>> ubuntu@ip-172-31-9-119:/$ ls /home
berlin  developer  professor  shubham  test  tokyo  ubuntu  vidya

-- 

---

## Task 2: Create Groups (10 minutes)

Create two groups:
- `developers`
- `admins`

1> sudo addgroup developers
2> sudo addgroup admins

**Verify:** Check `/etc/group`

>> developers:x:1007:
>> admins:x:1008:

--

### Task 3: Assign to Groups (15 minutes)

Assign users:
- `tokyo` → `developers`
- `berlin` → `developers` + `admins` (both groups)
- `professor` → `admins`

>> 
1> sudo usermod -aG developers tokyo
2> sudo usermod -aG developers,admins berlin
3> sudo usermod -aG admins professor


**Verify:** Use appropriate command to check group membership

>>
1> ubuntu@ip-172-31-9-119:/$ groups berlin
berlin : berlin users developers admins

2> ubuntu@ip-172-31-9-119:/$ groups professor
professor : professor users admins

3>ubuntu@ip-172-31-9-119:/$ groups tokyo
tokyo : tokyo users developers

--


### Task 4: Shared Directory (20 minutes)

1. Create directory: `/opt/dev-project`
2. Set group owner to `developers`
3. Set permissions to `775` (rwxrwxr-x)
4. Test by creating files as `tokyo` and `berlin`

>>
1. Create directory: `/opt/dev-project`
>>> sudo mkdir -p /opt/dev-project

2. Set group owner to `developers`
>> sudo chown :developers /opt/dev-project

3. Set permissions to `775` (rwxrwxr-x)
>> sudo chmod 775 /opt/dev-project

4. Test by creating files as `tokyo` and `berlin`
>> tokyo@ip-172-31-9-119:/$ touch practice.txt
touch: cannot touch 'practice.txt': Permission denied

>> berlin@ip-172-31-9-119:/$ touch practice.txt
touch: cannot touch 'practice.txt': Permission denied


### Note: as we have provided the 775 pemission, tokyo is the other user so he has no access for write so cant create a file. and same for berline






