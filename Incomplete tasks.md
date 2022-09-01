```dataviewjs
let tasks = dv.pages().file.where(f => f.tasks.length > 1).tasks
let task_paths = [...new Set(tasks.path)] //Remove duplicates
let uncompleted = tasks.where(t => !t.completed)

dv.taskList(uncompleted)
```
