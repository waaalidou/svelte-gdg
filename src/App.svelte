<script>
	import Book from "./book.svelte";
	import Button from "./button.svelte";

	let title = "";
	let price = 20;
	let description = "";

	let books = [];

	function setTitle(event) {
		title = event.target.value;
	}

	function addBook() {
		const newBook = {
			title: title,
			price: price,
			description: description,
		};
		books = books.concat(newBook);
	}


</script>

<h1>Book Store</h1>

<div id="root">
	<section>
	<h2>Add New Book</h2>
	<div>
		<label for="title">Title</label>
		<input type="text" id="title" value={title} on:input={setTitle} />
	</div>

	<div>
		<label for="price"> Price</label>
		<input type="number" id="price" bind:value={price} />
	</div>

	<div>
		<label for="description">Description</label>
		<textarea rows="3" id="description" bind:value={description} />
	</div>

	<Button on:click={addBook}>Add Book</Button>
</section>

<section>
	
	<h2>Stock</h2>
	{#if books.length === 0}
		<p>No books in stock.</p>
	{:else}
		{#each books as book}
			<Book
				bookTitle={book.title}
				bookPrice={book.price}
				bookDescription={book.description}
			/>
		{/each}
	{/if}
</section>
</div>

<style>
	#root {
		padding-bottom : 20px;
	}
	h1 {
		color: purple;
		text-align: center;
	}

	section {
		margin: 20px auto 30px;
		width: 30rem;
	}

	label,
	input,
	textarea {
		width: 100%;
	}
</style>
