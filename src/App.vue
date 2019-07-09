<template>
    <v-app>
        <h3 class="display-2 font-weight-light main-title">ToDoList</h3>
        <v-flex xs5 offset-xs3>
            <to-do-form></to-do-form>
        </v-flex>
        <to-do-list />
    </v-app>
</template>

<script>
import ToDoList from "./components/ToDoList"
import ToDoForm from "./components/ToDoForm"
import Vue from "vue"
Vue.prototype.$_bus = new Vue()//create a event bus
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

