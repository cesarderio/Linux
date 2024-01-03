# Managing Linux Process CPU Time

<br>

## Understanding Process Prioritization

- **Nice Value**: Controls process priority in relation to CPU time.
  - Range: `-20` (highest priority) to `+19` (lowest priority).
  - Essential for prioritizing CPU time among different processes.

<br>

## Commands for Monitoring and Setting Priority

1. **Using `ps -aux` and `ps -eo`**:
   - Lists running processes with details like USER, PID, %CPU.
   - `ps -eo pid,comm,ni` displays process ID, command, and nice value.

2. **Exploring `top` and `htop`**:
   - Both commands show the nice value of processes in their output.
   - `htop` provides an interactive way to sort and view processes.

3. **Setting Nice Value with `nice` and `renice`**:
   - `nice`: Used to start a process with a modified priority.
   - `renice`: Alters priority of an already running process.
   - Example: `sudo nice -n 5 ./test.sh` to start a script with a nice value of 5.
   - Example: `sudo renice -n -2 -p [PID]` to change the nice value of a process.

<br>

## Practical Example and Verification

- **Testing with a Script (`test.sh`)**:
  - A simple script created to demonstrate the process.
  - Initially run with a nice value of 5.
  - Priority altered to -2 using `renice`.

- **Verifying Changes**:
  - `ps -eo comm,ni,pid | grep test.sh` used to verify the nice value.
  - Confirmed change from 5 to -2 after using `renice`.

<br>

## Conclusion

Managing CPU time for processes in Linux is a critical skill for efficient system performance. Using commands like `ps`, `top`, `htop`, `nice`, and `renice` enables technicians to prioritize processes based on their importance, ensuring critical tasks receive adequate CPU time. This process management is essential for optimal system functionality, especially in environments with diverse and intensive workloads.
