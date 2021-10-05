<script lang="ts">
  import type { Task } from "./Task";
  import TodoInput from "./TodoInput.svelte";
  import TaskList from "./TaskList.svelte";

  let task: Task;
  let taskList: Array<Task> = [];

  function onTextChanged(event) {
    if (event.detail.length > 0) {
      task = {
        text: event.detail,
        status: true,
      };
      taskList = [...taskList, task];
    }
  }
</script>

<div class="todo_list_container">
  <TodoInput on:onTextChanged={onTextChanged} />
  <TaskList tasks={taskList} />
</div>

<style>
  .todo_list_container {
    width: 90vw;
    margin: 0 auto;
    margin-top: 1rem;
    padding: 2rem;
    min-height: 400px;
    box-sizing: border-box;

    /* From https://css.glass */
    background: rgba(255, 255, 255, 0.17);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    border: 1px solid rgba(255, 255, 255, 0.3);
  }

  @media only screen and (min-width: 768px) {
    .todo_list_container {
      width: 40vw;
      margin-top: 4rem;
    }
  }
</style>
