# task-cli
task-cli is a simple tool used to have a lightweight TODO list. Hate electron? Got bored of BIG TECH companies having the 'best' TODO list apps? This is your tool. It runs at your terminal, uses simple commands (task new/finish/list) and runs on Lua.

Available commands are:
### task new
To make a new task. Example: task new "Drink water"
### task list
To list current tasks. Example:
Current ToDo List:
1. Drink water
2. Have a jug
3. Sleep
### task finish
To finish a current task. Uses task's number so make sure you know it OR check task list. Example:
task finish 3
### task nuke
To remove all current tasks. Example:
task nuke

# Installation
Installing task-cli is quite simple. If you want to install it globally, run these commands in your terminal:
```bash
curl -s https://raw.githubusercontent.com/abu-tuqa/task-cli/main/task -o task

chmod +x task

sudo mv task /usr/local/bin/
```
