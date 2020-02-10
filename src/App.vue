<template>
  <v-app>
    <!-- navBar -->
    <div>
      <v-app-bar
        color="cyan accent-3 white--text"
      >

        <v-toolbar-title>Simple Web-app</v-toolbar-title>

      </v-app-bar>
    </div>
    <!-- Greetings -->
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
    
    <!-- NameGame -->
    <div class="ma-6 mt-n4">
      <v-card width="400" class="mx-auto mt-3">

        <v-card-title>
          <h3 class="mx-auto font-weight-regular">What's a VENM Stack?</h3>
        </v-card-title>
        
            <v-card-title>
                <p class="mx-auto font-weight-regular">{{ chosenName }}</p>
            </v-card-title>

        <v-card-actions>
          <v-btn 
          class="mx-auto" 
          @click= "picker" 
          color="cyan accent-3 white--text font-weight-regular">
          VENM
          </v-btn>
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
      <v-list-item-avatar
       color="grey darken-3"
       >
          <v-img
            class="elevation-6"
            src="../public/eddy-twitter.jpg"
          ></v-img>
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
  <!-- PictureCards -->
    <div class="ma-12 mt-n1">
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

        list: ['Vue Express Node.js MongoDB', 'Victor Exports Number Modules', 'Vanessa Enjoys Negotiating Money'],
        chosenName: '',
        cards: [
        { title: 'Rambo the Mangy mutt', src: 'https://lh3.googleusercontent.com/Nd_4xnQiWDs_H-wX0cK797PvDbcSK1V5S_wYGruB5WnRvp_d1qmtFj3NUW3iI2HuZxII2QSgp8q8gS8vauHaq9ckt6IvoTiLVMgBNK6vNTxHS2G3bR21CLadzbkkTUfJGZVMD2RVTfDEjgwgHZOpdriSZJ9pQIyhB1mHQDyFtF1B0kMN8iMOqIuApW4Pohh4t6aXj0k5SN4-yHF3sjkVFXb-6u5Xxk8iO-C7lWq9TeYc5estXB-G3XrzMRqoNLOz_n-LBtRVxKwK7VSFLIAV_s7biC_3XDtIYRujbQPvaRxPmb4GqIgi8EfbXNjCuV8Jmgaq1xtKvGLWWA401eUZ-YL2qlYF-bCKksidz7Jpn0THnzs_Hn7Ky_m99rQG7PvZDgcjPnDdH_7AYkzumSsDwpwFyYKjU3MHX2BG5RxHlIj8uJIsvRjeRU-SsonblyN7FzyBzvfKFJ3e0eMZyi-rZ_Bt0T2MQavUtMWsDMkdh0yuVc9_EmJQc_CZ-pGcrJZXCYjyUXbTTcg_O_7GnSxFbfxT5MRUUWANPKPxvQxH0U-Xyf1clCdp1RyrejqSd4dQhHKPwQIV0t7bZa-8W9oI2FI4KC_ENrrrmtZc-Id1KX0IqtEmopPOvN10ddMz-r13P9j2TxkkiWyS5om_LW9QiXI1UYbD91OmW_Ll43DWvjbUQMqj0AJwIMs=w756-h1007-no', flex: 12 },
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
                alert('Where are you going? Stay here!')
            }
              greet1()
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