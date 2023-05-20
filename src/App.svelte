<script>
  import '$root/style/global.css'
  import Todos from '$root/components/Todos.svelte'
  import Todo from '$root/components/Todo.svelte'
  import {todos} from '$root/stores/todoStores.js'
    import { each } from 'svelte/internal';
</script>
<main>
<Todos />
{#each $todos as todo}
  <Todo todo={todo} index={todo.id}/>
{/each}
</main>