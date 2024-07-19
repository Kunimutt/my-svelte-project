<script lang="ts">
    import type { TodoType } from '../types/todo.type';
    export let todos: TodoType[];

    $: totalTodos = todos.length;
    $: completedTodos = todos.filter((todo: TodoType) => todo.completed).length;

    let headingEl: HTMLElement;

    export function focus() {
        // shorter version: export const focus = () => headingEl.focus()
        headingEl.focus();
    }
</script>

<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
<h2 id="list-heading" bind:this={headingEl} tabindex={-1}>
    {completedTodos} out of {totalTodos} items completed
</h2>
