<script>
	import {createEventDispatcher} from 'svelte';
	import Button from './Button.svelte';
	export let productTitle;
	export let productPrice;
	export let productDescription;

	const dispatch = createEventDispatcher();

	function addToCart(){
		dispatch('addtocart',productTitle);
	}
</script>

<div>
	<h1>{productTitle}</h1>
	<h2>{productPrice}</h2>
	<p>{productDescription}</p>
	<Button on:click={addToCart}>Add to Cart</Button>
</div>

<style>
	div {
		margin: 1rem;
		box-shadow: 0 2px 8px rgba(0,0,0,0.26);
		padding: 1rem;
		border-radius: 5px;
		background-color: white;
	}
	h1{
		font-size: 1.25rem;
		margin: 0.25rem 0;
	}
	h2{
		font-size: 1rem;
		margin: 0.25rem 0;
		color: #4B4B4B;
	}
	p{
		margin: 0.25rem 0;
	}
	button {
		font:inherit;
		padding: 0.15rem 0.5rem;
		background-color: #D10057;
		border: 1px solid #D10057;
		color: white;
		cursor: pointer;
	}
	button:hover, 
	button:active {
		box-shadow: 1px 1px 6px rgba(0, 0, 0, 0.26);
	}
</style>