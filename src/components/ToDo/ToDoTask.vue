<template>
    <div class="task p-3">
        <div>{{ task }}</div>
        <button class="btn btn-danger" @click='removeTask'>X</button>
    </div>
</template>

<script>
export default {
    name: 'ToDoTask',
    props: ['task', 'removeTask'],
}
</script>

<style>
    .task {
        margin: 20px 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
        border: 1px solid #eee;
    }
</style>