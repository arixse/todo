<template>
    <v-flex>
        <v-form>
            <v-text-field
                label="title"
                required
            ></v-text-field>
            <v-textarea
                label="description"
            >

            </v-textarea>
            <v-btn
            color="success"
            right>
                Add
            </v-btn>
        </v-form>
    </v-flex>
</template>

<script>
export default {
    name:"ToDoForm",
    data:()=>({

    })
}
</script>
