<script>
  let books = []
  let reads = false
</script>

<input type="text" bind:value={books[index]} />
<input type="checkbox" bind:checked={reads} />
<p>The book is read: {reads}</p>
