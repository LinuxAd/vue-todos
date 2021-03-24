<template>
<div class=todos-list>
        <h1 class="text-left p-3">{{ title }}</h1>
        <ul id="todos" buttons="none" class="list-group-flush">
            <form id="form-todos">
                <div class="container-fluid">
                    <todo
                    v-for="t in todos"
                    :key="t.id"
                    :todo="{
                        id: t.id,
                        text: t.text,
                        done: t.done,
                        }"
                    >
                    </todo>
                    <p class="info"></p>
                </div>
            </form>
        </ul>
    </div>
</template>

<script>
import todo from '@/components/todo.vue'
const DefaultTodos = [
    {
        id: 0,
        text: "Take out the bins",
        done: false,
    },
    {
        id: 1,
        text: "Write extra items for todo list",
        done: false,
    },
    {
        id: 2,
        text: "Code todo app",
        done: true,
    },
    {},
]
export default {
    name: 'TodoList',
    data() {
        return {
            selectedTodo: undefined,
            message: '',
            todos: DefaultTodos,
        }
    },
    components: {
        todo
    },
    props: {
      title: {
          type: String,
          default: 'Today',
      }  
    }
}
</script>
<style scoped>
ul {
    margin: 0px;
    padding: 0px;
}

#todos {
    list-style-type: none;
}

#form-todos {
    margin: 10px;
}

.todos small {
    text-align: left;
}
</style>