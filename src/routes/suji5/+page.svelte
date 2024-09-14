<div class="wrapper">
	<h1 class="takuann">Suji</h1>
	<div class="container-fluid p-5 my-5 text-white">
		<h1 style="text-align: center;" class="bg-danger">ToDoを追加する</h1>
		<div class="kyc-search-bar" style="margin:0 auto;">
			<input class="kyc-search-box" type="text" placeholder="検索" autocomplete="off" />
		</div>
		<h1 class="takuann">筋が通っていない！！</h1>
	</div>
	<div class="btn-group btn-group-lg" role="group" aria-label="Large button group">
		<button type="button" class="btn btn-outline-primary">💪</button>
		<button type="button" class="btn btn-outline-primary">＋</button>
		<button type="button" class="btn btn-outline-primary">✏️</button>
	</div>
</div>

<style>
	.kyc-search-bar {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 45px;
		width: 550px;
		border-radius: 30px;
		margin: 5px;
		border: solid 1px #dcdcdc;
	}

	.kyc-search-box {
		font-size: 16px;
		width: 100%;
		border: none;
		outline: none;
	}

	i.kyc-search-mark {
		margin-left: 10px;
		margin-right: 5px;
		color: #9aa0a6;
	}

	i.kyc-search-mic {
		margin-right: 10px;
		cursor: pointer;
		color: #9aa0a6;
	}

	@media only screen and (max-width: 480px) {
		.kyc-search-bar {
			width: 90%;
		}
	}

	.takuann {
		text-align: center;
		color: red;
	}
	.wrapper {
		display: grid;
		grid-template-rows: auto 1fr auto;
		min-height: 100svh;
	}
</style>
