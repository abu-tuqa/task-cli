# task-cli's code process

System depends on two main sources for information: todo_list.txt; your local text file that we save tasks with, and task new [string]; our main way of getting new tasks being saved to your list file.



task new basically adds a line with the current timestamp [of sending the task] via os.date, then write beside your task. Let's say you've inserted `task new "Get a girlfriend and fast"`, system will write on your list file[YYYY-MM-DD] Get a girlfriend and fast`.



Code uses `task list` to provide you a quick yet organized list of your current tasks.



When finishing a task, you might want to finish IN your system thus your list stays clean. We use `task remove [number of task]` to do so. It transfers the current task's content into your todo_finished.txt file. That ensures that your content will be back upped when you need it (undoing a finish, or looking at your progress/history).



`task nuke` is quite straight-forward: List got messy or too long of random tasks? Punk the shit out of your list without backuping anything.
