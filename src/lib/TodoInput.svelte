<script lang="ts">
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  let text = "";

  function onEntered() {
    dispatch("onTextChanged", text);
    text = "";
  }
</script>

<div class="input_container">
  <input
    type="text"
    bind:value={text}
    on:keypress={(e) => e.key === "Enter" && onEntered()}
  />
  <button on:click={onEntered}><i class="fas fa-plus" /></button>
</div>

<style>
  .input_container {
    --radius: 0.5rem;
    --border-color: #63B4B8;
    --back-color: #316B83;
    --fore-color: #8CA1A5;

    width: 100%;
    display: flex;
  }

  .input_container input {
    flex: 1;
    width: 100%;
    height: 100%;
    font-size: 2rem;
    box-sizing: border-box;
    border-radius: var(--radius) 0 0 var(--radius);
    border: 1px solid var(--border-color);
    border-right: none;
    padding: 1rem;
    outline: none;
  }

  .input_container input:focus,
  .input_container input:focus-visible {
  }

  .input_container button {
    height: 100%;
    cursor: pointer;
    font-size: 2rem;
    padding: 1rem 2rem;
    border: 1px solid var(--border-color);
    border-left: none;
    border-radius: 0 var(--radius) var(--radius) 0;
    background-color: var(--back-color);
    color: var(--fore-color);
  }

  .input_container button:hover {
      filter: brightness(1.1);
  }
</style>
