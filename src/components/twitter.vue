<template>

  <div class="ma-6 mt-n4">

    <v-card
        class="mx-auto mt-3"
        color="#26c6da"
        dark
        max-width="400"
    >

        <v-card-title>
            <v-list-item-avatar color="grey darken-3">
                <v-img
                    class="elevation-6"
                    src= './../../public/eddy-twitter.jpg'
                >
                </v-img>
            </v-list-item-avatar>
            <span class="title font-weight-light">@SandwichPirate_</span>
        </v-card-title>

        <v-card-text class="headline font-weight-bold">
        "Nice webapp!"
        </v-card-text>

        <v-card-actions>
            <v-list-item class="grow">
                <v-row
                align="center"
                justify="end"
                >

                    <v-icon class="mr-1" color="pink lighten-1">mdi-heart</v-icon>
                    <span class="subheading mr-2">25.1k</span>
                    <span class="mr-1">·</span>
                    <v-icon class="mr-1">mdi-share-variant</v-icon>
                    <span class="subheading">45</span>

                </v-row>
            </v-list-item>
        </v-card-actions>

    </v-card>

  </div>

</template>

<script>
export default {
    name: 'twitterCard',
    
}
</script>

<style>

</style>