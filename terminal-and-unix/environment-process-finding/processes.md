## What is a process?
- A program on your computer that is being run
- Operating system ensures that the memory being used by one process cannot be accessed by another process. This means that if a program crashes, it should not affect the rest of the system. 

## Process commands
### ps
- Useful command to see which processes are running on your machine
- Most commonly exeucted as `ps aux` 
	- a: indicates that you’re interested in all processes, rather than just processes for the current user
	- u: ensures the process owner will be displayed
	- x: shows all active processes, not just those attached to the terminal
![[processes-1672533030446.jpeg]]
- USER column: username of user who exeucuted the process
- PID: number that uniquely identifies the process. Very useful for stopping a process

### kill
- Useful for stopping a process that is unresponsive
- To stop a process, run `kill` with the PID of the process. 
```
kill 26852
```

### `kill` vs  `kill -9`
- Kill process by default sends a ‘TERM’ signal, but if a process is unresponsive, it may not pick up this signal and may not terminate.
- The -9 flag turns this into a ‘KILL’ signal, which is non-ignorable. 
- If using `kill` doesn’t work, try using `kill -9`