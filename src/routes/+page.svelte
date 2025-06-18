<script>
  import Header from "../lib/Header.svelte"
  import BookSingular from "../lib/BookSingular.svelte"
  function saveList() {
    localStorage.todos = JSON.stringify(books)
  }
  function loadList() {
    books = JSON.parse(localStorage.todos)
  }
  function addBook() {
    books = [...books, ""]
  }
</script>

<Header />
<main class="content section">
  {(saveList(), loadList())}
  <button on:click={addBook}>Add Book</button>

  {#each books as book, index}
    <BookSingular />
  {/each}
</main>

<!--  Hello Future Neve.
  I am trying to make a book list that can be added to and saved to local storage. I want to be able to add books, mark them as read or unread, and save the state of each book. The read state is currently not working as expected because the checkbox is not updating the individual book's read state.

Note: The checkbox is not working as intended because it is bound to the entire `reads` array instead of the specific index. I need to bind it to `reads[index]` to ensure each book's read state is tracked individually.
  I also want to ensure that the changes are saved to local storage so that they persist across page reloads.

To induvidualise the read state. MAKE ANOTHER PAGE for each item then in the each have the component.

  In my own words:
  -Checkbox is not working as I am changing the singular read variable, so perhaps I need to add this to the array or make another function/array to store this within so that there can be multiple stages of read/not read at once. 
  -Give the books a read/unread tick box beside each - might have to have a confirm for this so that it saves to local storage -Need to induvidualise the read state for each book as they are all the same when changed.
  -Make all changes save to local storage and can reload
  
  Local Storage currently has the functions but I'm not quite sure where to put them for them to function best. Perhaps make a button to start with and progress to an automatic function from there. Maybe even make a function. -->

<footer class="footer">
  <p class="has-text-centered">&copy; Craighead Diocesan School 2025</p>
</footer>
