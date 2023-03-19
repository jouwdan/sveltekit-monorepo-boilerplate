<script lang="ts">
  let count = 0

  function handleClick() {
    count += 1
  }
</script>

<button type="button" class="btn variant-filled" on:click={handleClick}>
  <span>clicks: {count}</span>
</button>
