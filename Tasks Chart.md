```dataviewjs
let tasks = dv.pages().file.where(f => f.tasks.length > 1).tasks
let task_paths = [...new Set(tasks.path)] //Remove duplicates
let completed = tasks.where(t => t.completed).path
let uncompleted = tasks.where(t => !t.completed).path

let completed_counts = {}
tasks.forEach(task => completed_counts[task.path] = (completed_counts[task.path] || 0) + (task.completed ? 1 : 0))

let incomplete_counts = {}
tasks.forEach(task => incomplete_counts[task.path] = (incomplete_counts[task.path] || 0) + (task.completed ? 0 : 1))

dv.paragraph("## Tasks completed: " + Object.values(completed_counts).reduce((a,b) => a + b) + ", uncompleted: " + Object.values(incomplete_counts).reduce((a,b) => a + b) )

const chartData = {
type: 'bar',
fitPanelWidth: true,
data: {
	labels: task_paths,
	datasets: [{
		label: "# complete",
		data: Object.values(completed_counts),
		stack: 'bar',
		backgroundColor: [
			'rgba(50, 255, 50, 0.7)'
		],
	},
	{
		label: "# incomplete",
		data: Object.values(incomplete_counts),
		stack: 'bar',
		backgroundColor: [
			'rgba(255, 50, 50, 0.8)'
		],
	}]
}
}
window.renderChart(chartData, this.container)
```

