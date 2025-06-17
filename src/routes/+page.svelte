<script>
  import Header from "../lib/Header.svelte"
  let books = []
  function addBook() {
    books = [...books, ""]
  }
</script>

<Header />
<main class="content section">
  <button on:click={addBook}>Add Book</button>

  {#each books as book, index}
    <input type="text" bind:value={books[index]} />
  {/each}
</main>

<!-- Steps: Make addbook have details of title and author 
 Give the books a read/unread tick box beside each - might have to have a confirm for this so that it saves to local storage
 Make all changes save to local storage and can reload-->

<footer class="footer">
  <p class="has-text-centered">&copy; Craighead Diocesan School 2025</p>
</footer>
