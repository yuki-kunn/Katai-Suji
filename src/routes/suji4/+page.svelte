<script>
	import { goto } from '$app/navigation';
	let title = '';

	const addToDo = async () => {
		if (!title) {
			alert('筋を入力してください');
			return;
		}

		const response = await fetch('http://localhost:8000/api/todo', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json'
			},
			body: JSON.stringify({ title })
		});

		if (response.status === 400) {
			alert('筋を通せません');
		} else {
			alert('筋を通せました');
		}
		goto('/suji3');
	};
</script>

<body>
	<h1 class="takuann">ToDo</h1>
	<div class="container">
		<div class="input-group">
			<input type="text" class="form-control" placeholder="ToDoを入力" bind:value={title} />
		</div>
		<button type="button" class="footer p-3 btn btn-danger mt-2" on:click={addToDo}
			>ToDoを追加する</button
		>
	</div>

	<footer class="footer fixed-bottom d-flex justify-content-around align-items-center">
		<a href="/suji" class="btn">💪</a>
		<a href="/suji4" class="btn"> ＋ </a>
		<a href="/suji3" class="btn">✏️</a>
	</footer>
</body>

<style>
	.takuann {
		text-align: center;
		color: red;
		margin-bottom: 11em;
	}

	.container {
		height: 10px;
		margin: 0 auto;
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
