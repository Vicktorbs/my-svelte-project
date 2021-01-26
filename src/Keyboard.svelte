<script>
	import { message } from './store.js'
	let key;
	let keyCode;
	let noValidInputs = [16, 8, 13, 16, 20, 37, 38, 39,]

	function handleKeydown(event) {
		key = event.key;
		keyCode = event.keyCode;
		if (keyCode !== 16 && keyCode !== 8 && keyCode !== 13 & keyCode !== 16 && keyCode !== 20 && keyCode !== 37 && keyCode !== 38 && keyCode !== 39 && keyCode !== 40 && keyCode !== 9 && keyCode !== 17 && keyCode !== 225 && keyCode !== 93 && keyCode !== 18 && keyCode !== 123) {
			message.update(n => n += key)
		}
	}
</script>

<style>
	div {
		display: flex;
		height: 70%;
		align-items: center;
		justify-content: center;
		flex-direction: column;
	}

	kbd {
		background-color: #eee;
		border-radius: 4px;
		font-size: 6em;
		padding: 0.2em 0.5em;
		border-top: 5px solid rgba(255,255,255,0.5);
		border-left: 5px solid rgba(255,255,255,0.5);
		border-right: 5px solid rgba(0,0,0,0.2);
		border-bottom: 5px solid rgba(0,0,0,0.2);
		color: #555;
	}
</style>

<svelte:window on:keydown={handleKeydown}/>

<div style="text-align: center">
	{#if key}
		<kbd>{key === ' ' ? 'Space' : key}</kbd>
		<p>{keyCode}</p>
	{:else}
		<p>Focus this window and press any key</p>
	{/if}
</div>