<template>
    <div>
        <TodoForm @newTaskparapadre="newTask($event)" />
        <hr />
        <button class="btn btn-warning btn-block" @click="removeAll">DELETE ALL</button>
        <hr />
      <table class="table">
        <thead class="container">
            <tr>
                <td>id</td>
                <td>todo</td>
                <td>eliminar</td>
            </tr>
        </thead>
        <tbody v-if="todos.length > 0">
            
                 <TodoItem v-for="(task,index) in todos" :key="index" :task="task" :index="index" @removeTodoparaelpadre="removeTodo($event)"/>
            
        </tbody>
        <tbody v-else>
<tr>
    <td colspan="3"> no hay TASKS</td>
</tr>
        </tbody>
      </table>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import TodoForm from '@/components/TodoForm.vue'
import TodoItem from '@/components/TodoItem.vue'

@Component({
    components : {
        TodoForm,TodoItem
    }
})

export default class TodoList extends Vue{
    todos: Array<string> = [];

    newTask (task:string) {
        this.todos.push(task);
    }

    removeTodo (index:number) {
        this.todos.splice(index,1);
    }

    removeAll () {
        this.todos = [];
    }
}
</script>
