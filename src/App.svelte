<script lang="ts">
  import "@fortawesome/fontawesome-free/css/all.css";
  import TodoList from "./lib/TodoList.svelte";
</script>

<main>
  <TodoList />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  .logo {
    width: 6rem;
  }
</style>
