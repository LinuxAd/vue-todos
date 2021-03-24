<template>
    <div class="row m-3">
        <div class="col-0.1">
        </div>
        <div class="col-0.1">
            <input type="checkbox">
        </div>
            <input
            class="todo-text border-0 col"
            @blur="loseFocus"
            v-model=textToDisplay
            type="text">
        <div class="col-0.1">
        </div>
    </div>
</template>

<script>
export default {
    name: 'todo',
    props: {
        todo: {
            type: Object,
            required: true,
            default: function () {
                return {
                    id: 0,
                    text: "Something todo",
                    done: false,
                }
            }
        },
    },
    methods: {
        loseFocus: function() {
            this.isFocus = false
            console.log(`value of text is ${this.textToDisplay}`)
        }
    },
    emits: ['set-text:todo.text'],
    computed: {
        textToDisplay:
        {
            get() {
                return this.todo.text
            },
            set(value) {
                this.todo.text = value
                this.$emit('set-text',value)
            }
        }
    },
}
</script>