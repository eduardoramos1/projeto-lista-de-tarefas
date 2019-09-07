<template>
    <div class="task-grid">
        <template v-if='tasks.length'>
            <Task v-for='(task, i) in tasks' :key="task.name" 
               @taskDeleted="$emit('taskDeleted', i)" :task="task"
               @taskStateChange="$emit('taskStateChange', i)"></Task>
        </template>
         <div v-else> Não há tarefas pendentes =) </div>
    </div>
</template>

<script>
import Task from './Task'

export default {
    components: { Task },
    props: {
        tasks: {
            type: Array,
            required: true
        }
    }
}
</script>

<style>
    .task-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;

    }

</style>