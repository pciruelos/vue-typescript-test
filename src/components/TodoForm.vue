<template>
<div class="container">
    
<form @submit.prevent="addTodo">
  <div class="mb-3">
    <label for="todo" class="form-label">enter task</label>
    <input type="text" class="form-control" id="todo" aria-describedby="emailHelp" v-model="todo">
   
  </div>
  
 
  <button type="submit" class="btn btn-primary" >Add</button>
</form>
</div>
    
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'


@Component

export default class TodoForm extends Vue{
    todo: string = '';

    addTodo (){
        this.$emit('newTaskparapadre', this.todo)
        this.todo = ''
    }
}
</script>
