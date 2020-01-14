<template>
  <v-app>
    <!-- navBar -->
    <div>
      <v-app-bar
        color="pink accent-1 white--text"
      >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Kenia</v-toolbar-title>

      </v-app-bar>
    </div>
    <!-- Greetings -->
    <div class="ma-6 mt-12" id="greetingCard">
      <v-card width="400" class="mx-auto mt-12">
        <v-card-title>
          <h3 v-if = "isMorning()" class="mx-auto font-weight-regular">Buenos dias</h3>

          <h3 v-else-if = "isAfternoon()"  class="mx-auto font-weight-regular">Buenas tardes</h3>

          <h3 v-else-if = "isNight()" class="mx-auto font-weight-regular">Buenas noches</h3>
        </v-card-title>

        <v-card-title>
          <p class="mx-auto"></p>
        </v-card-title>
        
        <v-card-actions>
                <v-btn class="mx-auto" v-on:click= "alert1" color="pink lighten-1 white--text font-weight-regular">Click me!</v-btn>
        </v-card-actions>
      </v-card>
    </div>
    
    <!-- NameGame -->
    <div class="ma-6 mt-n4">
      <v-card width="400" class="mx-auto mt-3">
        <v-card-title>
          <h3 class="mx-auto font-weight-regular">Los nombres de Kenia</h3>
        </v-card-title>
        
        <v-card-title>
            <p class="mx-auto font-weight-regular">{{ chosenName }}</p>
        </v-card-title>

        <v-card-actions>
          <v-btn class="mx-auto" @click= "picker" color="pink lighten-1 white--text font-weight-regular">Tus Nombres</v-btn>
        </v-card-actions>
      </v-card>
    </div>
     <!-- Twitter card -->
     <div class="ma-6 mt-n4">
     <v-card
    class="mx-auto mt-3"
    color="#26c6da"
    dark
    max-width="400"
  >
    <v-card-title>
      <v-icon
        large
        left
      >
        mdi-twitter
      </v-icon>
      <span class="title font-weight-light">Twitter</span>
    </v-card-title>

    <v-card-text class="headline font-weight-bold">
      "Nice webapp!"
    </v-card-text>

    <v-card-actions>
      <v-list-item class="grow">
        <v-list-item-avatar color="grey darken-3">
          <v-img
            class="elevation-6"
            src="../public/eddy-twitter.jpg"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>@SandwichPirate_</v-list-item-title>
        </v-list-item-content>

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
  <!-- PictureCards -->
    <div class="ma-12 mt-n4">
     <v-card
    class="mx-auto"
    max-width="500"
  >
    <v-container fluid>
      <v-row dense>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="card.flex"
        >
          <v-card>
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="300px"
            >
            <v-card-title v-text="card.title"></v-card-title>
            </v-img>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn icon v-on:click= "like1 ++">
                <v-icon color="pink lighten-1">mdi-heart</v-icon>
                {{ like1 }}
              </v-btn>
            </v-card-actions>

          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
    </div>

  </v-app>
</template>

<script>

export default {
  name: 'App',
  components: {},

  data: () => ({
        day1: 'Dia uno 😥 ',
        day2: 'Dia dos, aun no me acostumbro 😟',
        day3: 'Dia tres, I miss you 🥺',
        day4: 'Dia cuatro, cuan aburrido es estar sin ti 😒',
        day5: 'Dia cinco, ya mero regresas!😏',
        list: ['Mi amor','Cosita', 'Cosa bella','Hermosa','Preciosa','Princesa','Chiky 🍪','Mi ardilla 🐿','Corazon','Baby','Mi vida','Mi mejor amiga','Mi Cielo','Mujer mas hermosa del mundo','Mi futuro','Mi Felicidad','Flaka','Ojos de miel','Mi enojona','Perfecta','Mi corazon de melon'],
        chosenName: '',
        cards: [
        { title: '', src: 'https://lh3.googleusercontent.com/Ri8eD5C-v6DyUW3TyD6Ajp4gkyyqUbuIx_hQvuOS0-9uZPRZiqZFhBwh625qsDX3_Rm8HPmPIfnUqWLOiCMEGAIV34OwBqRCp0T3KQKIMBp93_J_bsl5R5iinCdB8EWxYxJKb1iZ3XjD1urv8o8R7zRT-iq3PQAandcP5c6DUUjGtsOkdyQkCISV2zbRF4lT9zpaGN43sqpTPaVT3qyLPIpi3URTldTF0o7Gw5Y2dGQIBSSILhgKWTR-wF8368YQcwXe1GyauNInDevQTywVyjfBl48BOAAFde8p-wdx4MKzlKCNXzpvQG2OGZcM76XjYgg41CK0UxtOx9uYooADCt1ThAvXtVcOrZfnbRxBoj9E5hG-8ix1EpWsFzPqjz-qCMHmAb6bf7_nr9wZ30dWlIIZ5CRj5y70-vAPMUrcvY0y9TLfdwOgvdgnLnoOUnrUJP7iCJMJ6vNJoeRGYjZG7lL7dOJQjhgA-pWR23FjIytB-xuLlVUddHlBOGI2O7KcMrwgzyLpMRG8j9aAb6TGXvFAyHtEQ1JdNKxpd3btUjo4luhIev1TwiA1Nj80dc9XZlNhoupZwIsBmDURDqUpZ5i_WfVSQ4Yxy4t9PXoeefy33frgRYgmbwdWrugo3F9gxSuYGhO4BhdpxxyKyQeN2ldvbhT-vt_eMYAV3jVbOyWyu8QgtgdkbCI=w375-h500-no', flex: 12 },
        ],
        like1: 0,
  }),
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
                alert('')
            }
            function redirect1() {
                window.location.href = "https://www.youtube.com/watch?v=-2n03Ufzni8";
            }
            greet1()
            redirect1()
        },
        picker: function() {
            var chosenNumber = Math.floor(Math.random() * this.list.length)
            this.chosenName = this.list[chosenNumber];
        }
    },
    mounted() {
      if (localStorage.like1) {
        this.like1 = localStorage.like1;
      }
    },
    watch: {
      like1(newLike) {
        localStorage.like1 = newLike ;
      }
    }
};
</script>