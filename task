#!/usr/bin/env lua

local cmd = arg[1]
local file_path = os.getenv("HOME") .. "/.todo_list.txt"
local archive_path = os.getenv("HOME") .. "/.todo_done.txt"

local function count_lines(path)
	local file = io.open(path, "r")
	if not file then return 0 end
	local count = 0
	for _ in file:lines() do count = count + 1 end
	file:close()
	return count
end

local function get_multiline_arg(start_index)
	local task_table = {}
	for i = start_index, #arg do
		table.insert(task_table, arg[i])
	end
	return table.concat(task_table, " ")
end

if cmd == "new" then
	local task = get_multiline_arg(2)
	if task ~= "" then
		local file = io.open(file_path, "a")
		if file then
			file:write(os.date("[%Y-%m-%d] ") .. task .. "\n")
			file:close()
			print("New task is being saved: " .. task)
		else
			print("Error: System couldn't reach to the file. Check its permissions.")
		end
	else
		print("Error: Task's name invalid.")
	end
		
elseif cmd == "list" then
	local file = io.open(file_path, "r")
	local active = 0
	if file then
		print("Current ToDo List:")
		for line in file:lines() do
			active = active + 1
			print(active .. ". " .. line)
		end
		file:close()
	end
	if active == 0 then print("List's empty. Insert tasks to begin listing them.") end
	print(string.format("\n[Pending: %d | Completed: %d]", active, count_lines(archive_path)))

elseif cmd == "oops" then
	local index = tonumber(arg[2])
	local new_content = get_multiline_arg(3)
	if not index or new_content == "" then
		print("Syntax is incorrect. It's oops <id> <text>.")
		return
	end

	local tasks = {}
	local file = io.open(file_path, "r")
	if file then
		for line in file:lines() do table.insert(tasks, line) end
		file:close()
	else return print("Error: Task's file's unreadable.") end

	if index > 0 and index <= #tasks then
		local ts = tasks[index]:match("^%[[%d%-]+%] ") or ""
		tasks[index] = ts .. new_content
		file = io.open(file_path, "w")
		if file then
			for _, t in ipairs(tasks) do file:write(t .. "\n") end
			file:close()
			print("Task has been modified.")
		end
	else print("Error: Given task is out of range.") end

elseif cmd == "finish" then
	local index = tonumber(arg[2])
	if not index then return print("Task not found. Give us a number that exists.") end

	local tasks = {}
	local file = io.open(file_path, "r")
	if file then
		for line in file:lines() do table.insert(tasks, line) end
		file:close()
	else return print("Error: Task's file's unreadable.") end

	if index > 0 and index <= #tasks then
		local removed = table.remove(tasks, index)
		file = io.open(file_path, "w")
		if file then
			for _, task in ipairs(tasks) do file:write(task .. "\n") end
			file:close()
		end	
		local archive = io.open(archive_path, "a")
		if archive then
			archive:write(removed .. " [Completed: " .. os.date("%Y-%m-%d") .. "]\n")
			archive:close()
			print("Task has been finished and archived: " .. removed)
		end
	else print("Error: Given task is out of range.") end

elseif cmd == "history" then
	local file = io.open(archive_path, "r")
	local count = 0
	if file then
		for line in file:lines() do
			count = count + 1
			print(count .. ". " .. line)
		end
		file:close()
	end
	if count == 0 then print("History file's empty. Why not try finishing some tasks?") end

elseif cmd == "nuke" then
	local file = io.open(file_path, "w")
	if file then
		file:close()
		print("All tasks have been wiped out. New list, new life.")
	else print("Error: Could not access the file to wipe it.") end

else
	print("Error: We could not recognize the given argument. Please use either new, list, oops, finish, history, or nuke.")
end
