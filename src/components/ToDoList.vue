<template>
    <v-layout row>
        <v-flex>
            <v-list subheader three-line>
                <v-list-tile>
                    <v-list-tile-content @click.prevent="notifications = !notifications">
                        <v-list-tile-title>Notifications</v-list-tile-title>
                        <v-list-tile-sub-title>Notify me about updates to apps or games that I downloaded</v-list-tile-sub-title>
                    </v-list-tile-content>
                    <v-list-tile-action>
                        <v-checkbox v-model="notifications"></v-checkbox>
                    </v-list-tile-action>
                </v-list-tile>
            </v-list>
        </v-flex>
    </v-layout>
</template>

<script>
export default {
    data: () => ({
        notifications: false,
        sound: true,
        widgets: false
    })
}
</script>

<style>
</style>
