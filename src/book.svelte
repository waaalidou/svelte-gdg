<script>
  export let bookTitle;
  export let bookPrice;
  export let bookDescription;

</script>

<div>
  <h1>Title {bookTitle}</h1>
  <h2>Price :{bookPrice}</h2>
  <p>Description {bookDescription}</p>
</div>

<style>
  div {
    margin: 1rem;
    padding: 1rem;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  }

  h2 {
    font-size: 1rem;
    margin: 0.25rem 0;
    font-weight: bold;
  }

  p {
    margin: 0.25rem 0;
  }
</style>
