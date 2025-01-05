
# Linux Process Management Commands

Linux provides a variety of commands to manage system processes. Below is a summary of commonly used commands, their purposes, and examples.

## 1. `ps` - Process Status
Displays information about active processes.

### Usage:
```bash
ps aux
ps -e
ps -u <username>
```

### Example:
```bash
ps aux | grep apache
```

## 2. `top` - Real-time Process Monitoring
Shows real-time information about system processes and resource usage.

### Usage:
```bash
top
```

### Example:
- Press `q` to quit.

## 3. `htop` - Interactive Process Viewer
A more user-friendly alternative to `top`.

### Usage:
```bash
htop
```

### Example:
- Navigate and kill processes interactively.

## 4. `kill` - Terminate Processes
Used to terminate a process by its PID.

### Usage:
```bash
kill <PID>
kill -9 <PID>
```

### Example:
```bash
ps aux | grep my_program
kill 1234
```

## 5. `pkill` - Kill by Process Name
Kills processes by matching names.

### Usage:
```bash
pkill <process_name>
```

### Example:
```bash
pkill apache
```

## 6. `jobs` - List Background Jobs
Lists all jobs running in the background.

### Usage:
```bash
jobs
```

### Example:
- Run a job in the background using `&`:  
  ```bash
  sleep 100 &
  jobs
  ```

## 7. `bg` - Resume Job in Background
Resumes a suspended job in the background.

### Usage:
```bash
bg <job_number>
```

### Example:
```bash
bg 1
```

## 8. `fg` - Resume Job in Foreground
Resumes a suspended job in the foreground.

### Usage:
```bash
fg <job_number>
```

### Example:
```bash
fg 1
```

## 9. `nice` - Set Process Priority
Starts a process with a specific priority.

### Usage:
```bash
nice -n <priority> <command>
```

### Example:
```bash
nice -n 10 gzip large_file
```

## 10. `renice` - Change Process Priority
Changes the priority of a running process.

### Usage:
```bash
renice <priority> -p <PID>
```

### Example:
```bash
renice 5 -p 1234
```

## 11. `uptime` - System Uptime and Load
Displays how long the system has been running and load averages.

### Usage:
```bash
uptime
```

### Example:
```bash
uptime
```

## 12. `watch` - Periodically Run a Command
Runs a command at regular intervals and shows the output.

### Usage:
```bash
watch <command>
```

### Example:
```bash
watch -n 2 ls
```

## Additional Notes
- Use `man <command>` to view the manual page for a command.
- Combining commands with pipes (`|`) and redirection (`>` or `<`) is powerful for managing processes.

---
