<script>
	export let name;

	/*
	0.1 -> Go through the 3 main parts of a Svelte component
	0.2 -> JavaScript syntax: let/const, function, array, if/else, while/for/array.map
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

	import Card, { Content } from '@smui/card';
  import List, { Item, Text } from '@smui/list';

	let numbers = [1, 2, 3, 4];
	let a = numbers.length

	function addNumber() {
		numbers.push(numbers.length + 1);
		numbers = numbers;
		console.log(numbers);
	}

	$: numbers = [...Array(a).keys()];

	$: sum = numbers.reduce((t, n) => t + n, 0);
 
  let clicked = 0;
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

	<p>{numbers.join(' + ')} = {sum}</p>

	<label>
		<input type=number bind:value={a} min=0 max=10>
		<input type=range bind:value={a} min=0 max=10>
	</label>

	<button on:click={addNumber}>
		Add a number
	</button>
	<br>

	{#if sum > 45}
		<img src="https://i.imgflip.com/14hbfq.jpg" alt="">
	{/if}


	<div class="card-display">
		<div class="card-container">
			<Card>
				<Content component={List}>
					<Item on:click={() => clicked++}>
						<Text>A card with a list as content.</Text>
					</Item>
					{#each [...Array(5)].map((_v, i) => i + 1) as item}
						<Item on:click={() => clicked++}>
							<Text>Item #{item}</Text>
						</Item>
					{/each}
				</Content>
			</Card>
		</div>
	</div>
	
	<pre class="status">Clicked: {clicked}</pre>
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

<svelte:head>
  <!-- SMUI -->
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/svelte-material-ui@6.0.0-beta.0/bare.min.css"
  />
</svelte:head>