
# 📆 {{date}}
<svg viewBox="0 0 3760 100">
  <title>Timeline 2022</title>
  <g class='bars'>
    <rect fill='#0066FF' x='0' width='310' height='25'></rect>
    <rect fill='#3366AA' x='320' width='280' height='25'></rect>
    <rect fill='#99AA33' x='610' width='310' height='25'></rect>
    <rect fill='#99EE33' x='930' width='300' height='25'></rect>
    <rect fill='green' x='1240' width='310' height='25'></rect>
    <rect fill='yellow' x='1560' width='300' height='25'></rect>
    <rect fill='gold' x='1870' width='310' height='25'></rect>
    <rect fill='cyan' x='2190' width='310' height='25'></rect>
    <rect fill='orange' x='2510' width='300' height='25'></rect>
    <rect fill='red' x='2820' width='310' height='25'></rect>
    <rect fill='brown' x='3140' width='300' height='25'></rect>
    <rect fill='white' x='3450' width='310' height='25'></rect>
  </g>
  <g class='labels' style="font-size:50px;" text-anchor="middle">
    <text fill='#747474' x='0' y='80' text-anchor="start">January</text>
    <text fill='#747474' x='320' y='80' text-anchor="start">February</text>
    <text fill='#747474' x='610' y='80' text-anchor="start">March</text>
    <text fill='#747474' x='930' y='80' text-anchor="start">April</text>
    <text fill='#747474' x='1240' y='80' text-anchor="start">May</text>
    <text fill='#747474' x='1560' y='80' text-anchor="start">June</text>
    <text fill='#747474' x='1870' y='80' text-anchor="start">July</text>
    <text fill='#747474' x='2190' y='80' text-anchor="start">August</text>
    <text fill='#747474' x='2510' y='80' text-anchor="start">September</text>
    <text fill='#747474' x='2820' y='80' text-anchor="start">October</text>
    <text fill='#747474' x='3140' y='80' text-anchor="start">November</text>
    <text fill='#747474' x='3450' y='80' text-anchor="start">December</text>
  </g>
  <g>
    <circle cx="{{date:DDD}}0" cy="14" r="15" stroke="black" fill="white" />
  </g>
</svg>

## Tasks
- [ ] 
# Daily achievements

## Notes
## Shared calendar
<%* 
function parseAgendaTsv(agenda) {
return agenda.split("\n").map(event => {
	let props = event.split("\t");
	let startDT = new Date(props[0]);
	let days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
	return ({startDate: days[startDT.getDay()],
				startTime: props[1],
				endDate: props[2],
				endTime: props[3],
				title: props[6]
	})
})
}

let result = await tp.user.gcalload();
agenda = parseAgendaTsv(result);
tR += agenda.map(e => { return `${e.startDate} ${e.startTime} **${e.title}**`}).join('\n')
%>
