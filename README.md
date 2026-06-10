# task-cli
task-cli is a simple tool used to have a lightweight TODO list. Hate electron? Got bored of BIG TECH companies having the 'best' TODO list apps? This is your tool. It runs at your terminal, uses simple commands (task new/finish/list) and runs on Lua.

Available commands are:
### task new
To make a new task. Example: `task new "Drink water"`

It adds your new task to the 'todo_list.txt' file.
### task list
To list current tasks. Example:
Current ToDo List:
1. [2026-06-10] Drink water
2. [2026-06-10] Have a jug
3. [2026-06-10] Sleep

It basically shows the contents of your todo_list.txt file numbered.
### task finish
To finish a current task. Uses task's number so make sure you know it OR check task list. Example:
task finish 3

It moves your finished tasks to the "todo_done.txt" file, so you can back them up or check your progress whenever you would like to.
### task nuke
To remove all current tasks. Example:
`task nuke`

It overwrites the todo_list file with nothing.

**WARNING**: Some might say 'Umm where's the confirmation pal 🤓'; the command's name is nuke, it's meant to be used when your list is getting too messy or uncontrollable.
# Installation
Installing task-cli is quite simple. If you want to install it globally, run these commands in your terminal:
```bash
curl -s https://raw.githubusercontent.com/abu-tuqa/task-cli/main/task -o task

chmod +x task

sudo mv task /usr/local/bin/
```
