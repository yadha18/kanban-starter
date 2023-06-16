<template>
    <div class="uk-card uk-card-default uk-card-body" id="todo-col" @click="setActiveCol(col.id)">
        <h3>{{ col.name }}</h3>
        <Task v-for="task in col.tasks" :key="task.id" :task="task"/>
    </div>
</template>
<script>
import Task from './Task.vue';
import { store } from '../store';
export default {
    name: 'BoardColumn',
    props:['col'],
    components: {
        Task,
    },
    methods: {
        setActiveCol(colId){
            store.setActiveColumn(colId)
        }
    }
}
</script>