<script>

	let newItem = "";
	let todosList = [];

	function addTodo() {
		if (newItem !== ""){
			todosList = [
				...todosList,
				{
					task: newItem,
					completed: false,
				}
			]
			newItem = "";
		}
	}

	function remove(){
		todosList.splice(index,1);
		todosList = todosList
	}





</script>

<main class="container">
	<h2 class="todo_header">Todos app</h2>
	<div class="">
		<form on:submit|preventDefault={addTodo}>
			<input bind:value={newItem} type="task" class="todo_input" placeholder="enter TODO" >
			<button class="todo_btn">ADD</button>

		</form>
		
		{#each todosList as item, index }
		<div class="todo">
			<span class={`todo_text ${item.completed ? "todo_checked--strike" : ""}`}> {item.task}
			</span>
			<div class="icons">
				
			</div>
		</div> 
		{/each}
	</div>

	
</main>


<style>
.container{
	display: flex;
	flex-direction: column;
	align-items: center;
	min-height: 92vh;
	background-image: url("https://th.bing.com/th/id/OIP.PJ9wbFbvRXatHsz90FMZJAHaEK?pid=ImgDet&rs=1");
	background-size: cover;
	padding-top: 10vh;
}
.todo_input{
	background-color: inherit;
	border: none;
	box-shadow: none;
	text-decoration: none;
	font-size: 1.2rem;
	border-bottom: 1px solid black;
	margin-top: 15px;
	outline: none;
	width: 500px;
}

.todo_btn{
	background-color: inherit;
	border: none;
	box-shadow: none;
	border-color: black;
	font-size: 1.2rem;
	border: 2px solid;
	cursor: pointer;
}

.todo{
	display: flex;
	padding: 20px;
	border-radius: 20px;
	box-shadow: 0 0 15px rgb(0,0,0/20%);
	background-color: hsla(0,0%, 100%, 0.2);
	margin: 1.2rem
	;
}

.todo_header{
	text-align: center;
	padding: 20px;
	border-radius: 20px;
	box-shadow: 0 0 15px rgb(0 0 0 / 20%);
	margin: 15px 0px 20px 0px;
	font-size: 3rem;

}



</style>


