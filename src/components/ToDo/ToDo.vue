<template>
    <div class="container mt-5">
        <h1>Bonjour</h1>
        <form v-on:submit.prevent='addTask()' action="#">
            <div class="form-group">
                <label for="task">Tâche à ajouter</label>
                <input class="form-control" type="text" id="task" v-model='input' />
            </div>
            <input type="submit" value="Ajouter" />
        </form>
        <div>
            <todo-task v-bind:key='index' v-for="(task, index) in tasks" v-bind:task='task' v-bind:id="index" v-bind:removeTask="removeTask"></todo-task>
        </div>
        <!-- <component v-bind:is="component"></component> -->
    </div>
</template>

<script>

import ToDoTask from './ToDoTask'

export default {
    name: 'ToDo',
    data() {
        return {
            input: '',
            tasks: ["manger", "boire", "dormir"],
        }
    },
    methods: {
        addTask: function() {
            this.tasks.push(this.input)
            this.input = ''
        },
        removeTask: function(e) {
            this.tasks.splice(e.target.parentNode.id, 1)
        }
    },
    components: {
        'todo-task': ToDoTask
    }
}
</script>

<style>

</style>
