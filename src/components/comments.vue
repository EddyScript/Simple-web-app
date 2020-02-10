<template>

    <v-form class="px-auto mt-12"> 

        <v-container>

            <v-row>

                <v-col cols="5" sm="6" md="1">
                <v-text-field
                    label="Name"
                ></v-text-field>
                </v-col>

                <v-col cols="12" sm="6" md="10">
                <v-text-field
                    label="Comment"
                ></v-text-field>
                </v-col>

            </v-row>
        
        </v-container>

    </v-form>

</template>

<script>
export default {
    name: 'comments'

}
</script>

<style>

</style>