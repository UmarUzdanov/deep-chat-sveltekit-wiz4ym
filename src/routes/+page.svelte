<script>
	import { onMount } from 'svelte';
  
  // Make sure to use onMount and render deep-chat on load
	onMount(async () => {
		await import("deep-chat");
    isLoaded = true;
	});

  let isLoaded = false;
	const initialMessages = [
		{ role: "user", text: "Hey, how are you today?" },
		{ role: "ai", text: "I am doing very well!" }
	];
</script>

<main>
	<h1>Deep Chat</h1>
  {#if isLoaded}
    <!-- demo/textInput are examples of passing an object directly into a property -->
    <!-- initialMessages is an example of passing an object from script into a property -->
    <deep-chat
      demo={true}
      textInput={{"placeholder":{"text": "Welcome to the demo!"}}}
      initialMessages={initialMessages}
    />
  {/if}
</main>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
    justify-content: center;
    display: grid;
  }
</style>