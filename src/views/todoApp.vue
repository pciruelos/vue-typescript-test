<template>
    <div>
    <h1>Hello</h1>
<TodoList/>
    </div>
    
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import TodoList from '@/components/TodoList.vue'

@Component({
    components: {
        TodoList
    }
})

export default class TodoApp extends Vue{
    
}
</script>
