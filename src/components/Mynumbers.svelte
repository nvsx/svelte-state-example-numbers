<script>
	export let numbers = []; // parent value, empty array is only a default
	export let add_num;      // parent function that's accessible for child
	let current_number = 1;  // only compnents own property
	const add_num_local = () => {
		add_num(current_number)
	}
	// multiple possible ways to call parent function
	// 1. like with delete_num: event forwarding
	//    child: on:click without any more instructions
	//    parent: <Mynumbers on:click={delete_num} />
	// 2. like in this case
	//    we get add_num as prop 
	//    parent gives function and child uses it
	//    child: on:click function name
	//    parent: <Mynumbers add_num={add_num} />
	// 3. dispatch, we do not care if parent catches it: 
	//     import { createEventDispatcher} from 'svelte';
	//     const dispatch = createEventDispatcher();
	//     dispatch('add_num', current_number);
	//     in Parent: component event: <Mynumbers on:add_num={add_num}
	//     in Parent: function add_num(e) { do something with e.detail }
	// 4. Context
	//     import { setContext } from 'svelte';
	//     import App from '../App.svelte';
	//     setContext('update_nums', {add_num, delete_num});
	//     possible for child or grandchildren...
</script>

<div class="my_number_module">
	<h3>Child: List of numbers</h3>
	<div class="my_number_list">
		{numbers}
	</div>
	<input type="number" name="my_numbers" id="my_numbers" bind:value={current_number} />
	<button class="my_number_add" on:click={add_num_local}>Add new number</button>
	<button class="my_number_delete" on:click>Delete first one</button>
</div>

<style>
 	.my_number_module {
		margin: 50px 0;
		padding: 20px;
		text-align: center;
		background-color: lightsteelblue;
		border: 1px solid seagreen;
		border-radius: 20px;
	}
	.my_number_list {
		margin:20px;
		padding: 20px;
		border: 1px solid #fafafa;
		border-radius: 20px;
		font-size: 1.5em;
		font-weight: bold;
	}
</style>
