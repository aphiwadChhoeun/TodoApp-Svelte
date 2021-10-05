<script lang="ts">
  import type { Task } from "./Task";
  export let tasks: Array<Task>;

  function onClick(index) {
    tasks[index].status = !tasks[index].status;
  }
</script>

<div class="task_list_container">
  <ul>
    {#each tasks as task, i}
      <li
        on:click={() => onClick(i)}
        class={task.status ? "active" : "inactive"}
      >
        {task.text}
      </li>
    {/each}
  </ul>
</div>

<style>
  ul > li {
    font-size: 2rem;
    cursor: pointer;
  }

  ul > li.inactive {
    text-decoration: line-through;
  }
</style>
