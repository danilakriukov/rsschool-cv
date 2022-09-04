# Danila Kriukov
# Contact info
* Github: [https://github.com/danilakriukov]
# About me
Music teacher, use the programming skills in my job
# Skills
* HTML/CSS
* JavaScript
* Python
* MySQL/PostgreSQL
* AJAX
# Code example
My musical tasks manager site
```
<script>
var listoftasks = {{listoftasks|tojson}};
var listoftasksarray = JSON.parse(listoftasks);
console.log(listoftasksarray);
arrayLenghth = listoftasksarray.length;
console.log(arrayLenghth);

for (let i=0; i<arrayLenghth; i++) {
    writeTasks(i);
}

function writeTasks(i){
	var specific_task = listoftasksarray[i];

	//Create DOM's of tasks
	var strtask = JSON.stringify(specific_task);
	let newDiv = document.createElement('p');
	newDiv.innerHTML = strtask;
	newDiv.id = i;
	let br = document.createElement('br');
	let newBtn = document.createElement('button');
	newBtn.innerHTML = 'Удалить задание';
	newBtn.id = 'newBtn' + ' ' + i;
	let newBtnid = newBtn.id;
	document.getElementById("list_of_tasks").appendChild(newDiv);
	document.getElementById(i).appendChild(br);
	if (strtask != '"Пока пусто..."'){
		document.getElementById(i).appendChild(newBtn);	
	}
	document.getElementById(newBtnid).addEventListener("click", function(e) {
		getId()
	});
	
  function getId(){
		var forTaskDel = newBtn.id;
		console.log(forTaskDel);
		var s = JSON.stringify(forTaskDel);
		
		$.ajax({
			url:"/numberbtn",
			type:"POST",
			contentType: "application/json",
			data: JSON.stringify(s)});
		location.href = "deletedtask";		
	}
}	
</script>
```
# Languages
* English - B2
* German - C1
* Russian - Native
