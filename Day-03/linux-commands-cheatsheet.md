## Question
Follow these rules while creating your cheat sheet:

- Include **at least 20 commands** with one‑line usage notes
- Add **3 networking commands** (`ping`, `ip addr`, `dig`, `curl`, etc.)
- Group commands by category
- Keep it concise and readable
- Run and record output for **at least 6 commands**
- Include **2 process commands** (`ps`, `top`, `pgrep`, etc.)
- Include **2 service commands** (`systemctl status`, `systemctl list-units`, etc.)
- Include **2 log commands** (`journalctl -u <service>`, `tail -n 50`, etc.)
- Pick **one service on your system** (example: `ssh`, `cron`, `docker`) and inspect it
- Keep it **simple and actionable**

--  

1. Include **at least 20 commands** with one‑line usage notes.
>>
1> ls → List files and directories.
2> pwd → Show current working directory.
3> cd <dir> → Change directory.
4> mkdir <dir> → Create a new directory.
5> rmdir <dir> → Remove an empty directory.
6> rm -rf <dir> → Remove a directory and its contents.
7> touch <file> → Create an empty file.
8> cat <file> → Display file contents.
9> less <file> → View file contents page by page.
10> head <file> → Show first 10 lines of a file.
11> tail <file> → Show last 10 lines of a file.
12> cp <src> <dest> → Copy files or directories.
13> mv <src> <dest> → Move or rename files/directories.
14> rm <file> → Delete a file.
15> echo "text" → Print text to terminal.
16> man <command> → Show manual/help for a command.
17> chmod 755 <file> → Change file permissions.
18> chown user:group <file> → Change file ownership.
19> ps aux → List running processes.
20> kill <pid> → Terminate a process by ID.
21> top → Show real‑time process/resource usage.
22> df -h → Show disk space usage.
23> du -sh <dir> → Show size of a directory.
24> uname -a → Show system info.
25> whoami → Display current logged‑in user.

--  

2. Add **3 networking commands** (`ping`, `ip addr`, `dig`, `curl`, etc.)
>> Networking Commands

1> ping <host> → Test connectivity to a host (e.g., ping google.com).

2> ip addr → Show IP addresses and network interfaces.

3> curl <url> → Fetch data from a URL (test APIs or websites).

--


3. Group commands by category
>> 
📂 File & Directory Management

ls → List files and directories.
pwd → Show current working directory.
cd <dir> → Change directory.
mkdir <dir> → Create a new directory.
rmdir <dir> → Remove an empty directory.
rm -rf <dir> → Remove a directory and its contents.
touch <file> → Create an empty file.
cp <src> <dest> → Copy files or directories.
mv <src> <dest> → Move or rename files/directories.
rm <file> → Delete a file.

📄 File Viewing & Editing

cat <file> → Display file contents.
less <file> → View file contents page by page.
head <file> → Show first 10 lines of a file.
tail <file> → Show last 10 lines of a file.
echo "text" → Print text to terminal.
man <command> → Show manual/help for a command.

🔐 Permissions & Ownership

chmod 755 <file> → Change file permissions.
chown user:group <file> → Change file ownership.


⚙️ Process & System Management

ps aux → List running processes.
kill <pid> → Terminate a process by ID.
top → Show real‑time process/resource usage.
df -h → Show disk space usage.
du -sh <dir> → Show size of a directory.
uname -a → Show system info.
whoami → Display current logged‑in user.


🌐 Networking

ping <host> → Test connectivity to a host.
ip addr → Show IP addresses and network interfaces.
curl <url> → Fetch data from a URL (test APIs or websites).


👉 In short:

File/Directory → create, move, delete.
Viewing → read and inspect files.
Permissions → control access.
Processes/System → monitor and manage.
Networking → test and troubleshoot connections.

--  

4. Include **2 process commands** (`ps`, `top`, `pgrep`, etc.)
>>
1> ps aux → Lists all running processes with details like PID, user, CPU/memory usage.
2> top → Displays real‑time process and resource usage (CPU, memory, tasks).
3> pgrep <name> → Finds process IDs by name.

--  

5. Include **2 service commands** (`systemctl status`, `systemctl list-units`, etc.)
>> 
🖥️ Service & Unit Management

1> systemctl status <service> → Show the current status of a service.
ex : systemctl status nginx
2> systemctl start <service> → Start a service immediately.
3> systemctl stop <service> → Stop a running service.
4> systemctl restart <service> → Restart a service.
5> systemctl enable <service> → Enable service to start at boot.
6> systemctl disable <service> → Disable service from starting at boot.

📋 Unit Listing & Control

1> systemctl list-units → Show all active units (services, sockets, devices, etc.).
2> systemctl list-unit-files → Show all installed unit files and their enable/disable state.
3> systemctl is-active <service> → Check if a service is currently active.
4>systemctl is-enabled <service> → Check if a service is enabled at boot.

⚡ System Control

1> systemctl reboot → Reboot the system.
2> systemctl poweroff → Shut down the system.
3> systemctl isolate <target> → Switch to a different target (like runlevel).
4> systemctl default → Return to the default target (usually graphical or multi-user).


👉 In short:

Use systemctl status to inspect services.

Use systemctl list-units to see what’s running.

Use systemctl start/stop/restart/enable/disable to control services.

-- 

6. Include **2 log commands** (`journalctl -u <service>`, `tail -n 50`, etc.)
>> 
📜 Log & Monitoring Commands

1> journalctl -u <service> → Show logs for a specific service managed by systemd.
Example: journalctl -u nginx

2> journalctl -f -u <service> → Follow (tail) logs live for a service.
Example:  journalctl -f -u ssh

3> tail -n 50 <file> → Show the last 50 lines of a log file.
Example:  tail -n 50 /var/log/syslog

4> tail -f <file> → Continuously follow a log file as new entries are written.
Example:  tail -f /var/log/auth.log


👉 In short:

-- Use journalctl for systemd‑managed service logs.

-- Use tail for traditional log files in /var/log.
--
