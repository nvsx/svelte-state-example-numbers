<script>
	import Mynumbers from './components/Mynumbers.svelte';

	export let name;
	let numbers = [1, 2, 3];
	const add_num = (this_number) => {
		if(this_number !== null) {
			// numbers.push(this_number)
			// but we also need to update arrays!
			// one way would be: numbers = numbers;
			// other way to add is use spread syntax like so: 
			numbers = [...numbers, this_number];
		}
	}
	const delete_num = () => {
		// this function is called by event forwarding
		// it is given as property to child component
		numbers.shift();
		// and we laso need to explicitly update arrays!
		// (arrays are somewhat special it this respect)
		numbers = numbers;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<Mynumbers numbers={numbers} on:click={delete_num} add_num={add_num} />
	<div>
		<h3>Parent: List of numbers</h3>
		<p>
			{numbers}
		</p>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	h1 {
		color: maroon;
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
