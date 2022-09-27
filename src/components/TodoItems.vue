<template>
    <TodoItem v-for="todo in $store.state.todos" :key="todo.id">

    </TodoItem>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'
export default {
    name: 'TodoItems',
    components: {
        TodoItem,

    }
}
</script>