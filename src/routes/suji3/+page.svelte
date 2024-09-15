<script>
	// @ts-nocheck

	async function fetchToDo() {
		console.log('リクエストスタート');
		const response = await fetch('http://localhost:8000/api/todo', {
			method: 'GET',
			headers: {
				'Content-Type': 'application/json'
			}
		});
		console.log(response.ok);
		const data = await response.json();
		console.log(data);
		return data;
	}

	let promise = fetchToDo();
</script>

<body>
	<h1 class="takuann">ToDo</h1>
	<div class="container-fluid p-5 my-5 text-white">
		{#await promise}
			<p>loading...</p>
		{:then todoList}
			<ul>
				{#each todoList as todo}
					<li class="ooter p-3 mt-2 bg-danger">{todo.title}</li>
				{/each}
			</ul>
		{/await}
	</div>
	<footer class="footer fixed-bottom d-flex justify-content-around align-items-center">
		<a href="/suji" class="btn">💪</a>
		<a href="/suji4" class="btn"> ＋ </a>
		<a href="/suji3" class="btn">✏️</a>
	</footer>
</body>

<style>
	div {
		text-align: center;
	}
	.takuann {
		text-align: center;
		color: red;
	}
	/* フッターの設定 */
	.footer {
		width: 100%;
		padding: 10px;
	}

	/* フッターのボタンのスタイル調整 */
	.footer button {
		border: none;
		background: none;
	}
</style>
