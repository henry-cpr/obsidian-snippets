```dataviewjs
let tags = dv.pages().file.tags
let tag_counts = {}
tags.forEach(tag => tag_counts[tag] = (tag_counts[tag] || 0) + 1)
const chartData = {
	type: 'bar',
	width: '100%',
	options: {
		indexAxis: 'y',
	},
	data: {
		labels: tags,
		datasets: [{
			label: "#",
			data: Object.values(tag_counts),
			stack: 'bar',
            backgroundColor: [
                'rgba(50, 255, 50, 0.7)'
            ],
		}]
	}
}
window.renderChart(chartData, this.container)
```