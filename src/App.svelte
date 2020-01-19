<script>
	import Product from './Product.svelte';
	import Modal from "./Modal.svelte";

	let products = [
		{
			id: 'p1',
			title: 'A Book',
			price: 9.99
		}
	]

	let showModal = false;

	function addToCart(event) {
		console.log(event);
		
	}

	function deleteProduct(event) {
		console.log(event);
		
	}
</script>

{#each products as product}
	<Product 
	{...product}
	on:add-to-cart={addToCart}
	on:delete={deleteProduct} />
{/each}

<button on:click="{() =>{ showModal = true}}">Show Modal</button>
{#if showModal}
	<Modal on:cancel="{() => {showModal = false}}"
			on:close="{() => {showModal = false}}">
		<h1 slot="header">Hi!</h1>
		<p>This works!</p>
	</Modal>
{/if}