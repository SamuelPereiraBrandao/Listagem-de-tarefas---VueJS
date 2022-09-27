<template>
    <div class="px-3 py-10 md:px-10">
        <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">

            <pre>{{$store.state.todos}}</pre>
            <TodoSpinner></TodoSpinner>
            <TodoFormAdd></TodoFormAdd>
            <TodoItems></TodoItems>
            <TodoEmpty></TodoEmpty>



        </div>
    </div>

</template>
<script>
import TodoSpinner from '@/components/TodoSpinner.vue'
import TodoFormAdd from './components/TodoFormAdd.vue';
import TodoItems from '@/components/TodoItems.vue'
import TodoEmpty from './components/TodoEmpty.vue'
import axios from 'axios'
export default {
    name: 'PrincipalVue',
    components: {
        TodoSpinner,
        TodoFormAdd,
        TodoItems,
        TodoEmpty
    },
    created() {
        axios.get('http://localhost:3000/todos')
        .then((response) => {
            this.$store.commit('storeTodos', response.data)
        })
    }
}
</script>

