<script>
	export let name;

	/*
	1. -> Add reactive array: https://svelte.dev/tutorial/updating-arrays-and-objects
	2. -> Add numeric input: https://svelte.dev/tutorial/numeric-inputs
	2.1 -> Create function that uses numeric input to adjust array length
	3. Create if block: https://svelte.dev/tutorial/if-blocks
	4. Import component from material UI: https://sveltematerialui.com
	4.1 Install in terminal: npm install --save svelte-material-ui
	4.2 Add stylesheet to <svelte:head>
	4.3 Pick any card you like, e.g. card with list: https://sveltematerialui.com/demo/card
	    By copying the relevant code.
	5. Debugging with console.log

	*/
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>