<template>
    <v-app>
        <h3 class="display-4 font-weight-light main-title">ToDoList</h3>
        <v-flex xs5 offset-xs3>
            <to-do-form></to-do-form>
        </v-flex>
        <v-container>
            <to-do-list />
        </v-container>
    </v-app>
</template>

<script>
import ToDoList from "./components/ToDoList"
import ToDoForm from "./components/ToDoForm"
export default {
    name: "App",
    components: {
        ToDoList,
        ToDoForm
    },
    data() {
        return {
            //
        }
    }
}
</script>
<style lang="stylus">
.main-title {
    text-align: center;
    padding: 40px 0;
}
</style>

