<script>
  import {addTodo} from "../stores/todoStores.js"
  let todo = '';
  const handleSumbit = () => {
    addTodo(todo);
    todo = '';
    console.log("submitting");
  }
</script>
<main>
    <h1 class="title">Todos</h1>
    <section class="todos">
        <form on:submit|preventDefault={handleSumbit}>
            <!-- svelte-ignore a11y-autofocus -->
            <input 
                id="new-todo"
                class="new-todo"
                placeholder="What needs to be done?"
                type="text"
                autofocus
                bind:value={todo}
                />
        </form>
    </section>
</main>
<style>
    .title {
      font-size: var(--font-80);
      font-weight: inherit;
      text-align: center;
      color: var(--color-title);
    }
    .todos {
      --width: 500px;
      --todos-bg: hsl(0 0% 98%);
      --todos-text: hsl(220 20% 14%);
      width: var(--width);
      color: var(--todos-text);
      background-color: var(--todos-bg);
      border-radius: var(--radius-base);
      border: 1px solid var(--color-gray-90);
      box-shadow: 0 0 4px var(--shadow-1);
    }
    .new-todo {
      width: 100%;
      padding: var(--spacing-16);
      padding-left: 60px;
      font-size: var(--font-24);
      border: none;
      border-bottom: 1px solid var(--shadow-1);
    }
  </style>
  