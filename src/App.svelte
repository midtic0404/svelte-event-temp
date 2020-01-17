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


<Modal>
	<h1>Hi!</h1>
</Modal>