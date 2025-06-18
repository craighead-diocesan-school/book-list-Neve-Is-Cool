<script>
  import Header from "../lib/Header.svelte"
  let books = []
  let reads = [] // Initialize an array to hold the read state for each book
  function addBook() {
    books = [...books, ""]
    reads = [...reads, false]
  }
</script>

<!-- Checkbox is not working as I am changing the singular read variable, so perhaps I need to add this to the array or make another function/array to store this within so that there can be multiple stages of read/not read at once. -->

<Header />
<main class="content section">
  <button on:click={addBook}>Add Book</button>

  {#each books as book, index}
    <input type="text" bind:value={books[index]} />
    <input type="checkbox" bind:checked={reads} />
    <p>The book is read: {reads}</p>
  {/each}
</main>

<!-- 
 Give the books a read/unread tick box beside each - might have to have a confirm for this so that it saves to local storage yes and need to induvidualise the read state(check comment above) for each book as they are all the same when changed.
 Make all changes save to local storage and can reload-->

<footer class="footer">
  <p class="has-text-centered">&copy; Craighead Diocesan School 2025</p>
</footer>
