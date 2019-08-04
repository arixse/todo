<template>
    <v-flex>
        <v-form>
            <v-text-field label="title" required v-model="todoTitle"></v-text-field>
            <!-- <v-textarea label="description" v-model="todoDescription"></v-textarea> -->
            <v-btn color="success" right @click="addTodo">Add</v-btn>
        </v-form>
    </v-flex>
</template>

<script>
export default {
    name: "ToDoForm",
    data: () => ({
        todoTitle: "",
        todoDescription: ""
    }),
    methods: {
        addTodo() {
            if (this.todoTitle) {
                this.$_bus.$emit("addTodo", {
                    title: this.todoTitle,
                    description: this.todoDescription
                })
                this.todoTitle = ``
                this.todoDescription = ``
            }
        }
    }
}
</script>
