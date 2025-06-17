<script>
  import Header from "../lib/Header.svelte"
  let books = []
  let read = false
  function addBook() {
    books = [...books, ""]
  }
</script>

<Header />
<main class="content section">
  <button on:click={addBook}>Add Book</button>

  {#each books as book, index}
    <input type="text" bind:value={books[index]} />
    <input type="checkbox" bind:checked={read} />
    <p>The book is read: {read}</p>
  {/each}
</main>

<!-- 
 Give the books a read/unread tick box beside each - might have to have a confirm for this so that it saves to local storage yes and need to induvidualise the read state for each book as they are all the same when changed.
 Make all changes save to local storage and can reload-->

<footer class="footer">
  <p class="has-text-centered">&copy; Craighead Diocesan School 2025</p>
</footer>
