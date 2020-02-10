<template>
  <div class="ma-6 mt-12" id="greetingCard">
      <v-card width="400" class="mx-auto mt-12">
        <v-card-title>
          <h3 v-if = "isMorning()" class="mx-auto font-weight-regular">Rise and shine, lazy bones!</h3>

          <h3 v-else-if = "isAfternoon()"  class="mx-auto font-weight-regular">Goodevening chaps!</h3>

          <h3 v-else-if = "isNight()" class="mx-auto font-weight-regular">Boa Noite!</h3>
        </v-card-title>

        <v-card-title>
          <p class="mx-auto"></p>
        </v-card-title>
        
        <v-card-actions>
                <v-btn 
                class="mx-auto" 
                v-on:click= "alert1" 
                color="cyan accent-3 white--text font-weight-regular">
                  Click me!
                </v-btn>
        </v-card-actions>
      </v-card>
    </div>
</template>

<script>
export default {
    name: 'greetings',
    
    methods: {
        isMorning() {
            return new Date().getHours() < 12 ? true : false
        },
        isAfternoon() {
            return new Date().getHours() < 19 ? true : false
        },
        isNight() {
            return new Date().getHours() < 24 ? true : false
        },

        alert1: function () {
            function greet1() {
                alert('Where are you going? Stay here!')
            }
              greet1()
        }
    }
}

</script>

<style>

</style>