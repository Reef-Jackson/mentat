<script>
	let showInput = true;

	function toggleInput() {
		showInput = !showInput;
	}
</script>

<main>
	<div class="header-wrapper">
		<div class="header">
			<h1>Mentat</h1>
		</div>
	</div>
	<div class="main-wrapper">
		<div class="main">
			<button type="button" on:click={toggleInput}>New Entry</button>
			<!--- Modal on click-->
			{#if !showInput}
				<div class="menu">
					<select name="mood-score" id="mood-score">
						<option value="placeholder">Mood /5</option>
						<option value="1">1</option>
						<option value="2">2</option>
						<option value="3">3</option>
						<option value="4">4</option>
						<option value="5">5</option>
					</select>
					<input type="date" />
					<button on:click={toggleInput}>Add entry</button>
				</div>
				<textarea
					name="input"
					id="entry"
					cols="30"
					rows="10"
					placeholder="Explain your day... This will be hidden behind a button press."
				/>
			{/if}
		</div>
	</div>
</main>

<style>
	:global(html, body) {
		background-color: #1b1725;
		color: white;
		font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
			Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue",
			sans-serif;
	}

	.header-wrapper {
		display: flex;
		flex-direction: column;
		justify-content: center;
	}

	.header h1 {
		color: rgb(248, 213, 39);
		padding-left: 2rem;
	}

	.main-wrapper {
		display: flex;
		width: 66vw;
		justify-content: center;
		margin: auto;
	}

	.main {
		display: flex;
		flex-direction: column;
		width: 100%;
	}

	.main button {
		width: fit-content;
	}

	.main textarea {
		height: 50rem;
		background-color: rgb(40, 40, 38);
		color: white;
	}
</style>
