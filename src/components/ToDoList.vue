<template>
    <v-container>
        <v-radio-group row v-model="filter">
            <v-radio label="all" value="all"></v-radio>
            <v-radio label="done" value="done"></v-radio>
            <v-radio label="undo" value="undo"></v-radio>
        </v-radio-group>
        <v-layout row>
            <v-flex>
                <v-list subheader three-line>
                    <template v-for="(todo,index) in todos">
                        <v-divider :key="index"></v-divider>
                        <v-list-tile :key="index">
                            <v-list-tile-action>
                                <v-checkbox v-model="todo.completed"></v-checkbox>
                            </v-list-tile-action>
                            <v-list-tile-content>
                                <v-list-tile-title>{{todo.title}}</v-list-tile-title>
                                <v-list-tile-sub-title>{{todo.description||"暂无"}}</v-list-tile-sub-title>
                            </v-list-tile-content>
                            <v-list-tile-action>
                                <v-btn icon ripple>
                                    <v-icon color="grey lighten-1" @click="deleteTodo(index)">delete</v-icon>
                                </v-btn>
                            </v-list-tile-action>
                        </v-list-tile>
                    </template>
                </v-list>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data: () => ({
        todosList: [],
        filter: "all"
    }),
    methods: {
        deleteTodo(index) {
            this.todosList.splice(index, 1)
        }
    },
    mounted() {
        this.$_bus.$on("addTodo", todo => {
            if (todo) {
                this.todosList.push({
                    ...todo,
                    completed: false
                })
            }
        })
    },
    computed: {
        todos() {
            if (this.filter == `undo`) {
                return this.todosList.filter(item => !item.completed)
            } else if (this.filter == `done`) {
                return this.todosList.filter(item => item.completed)
            }
            return [...this.todosList]
        }
    }
}
</script>

<style>
</style>
