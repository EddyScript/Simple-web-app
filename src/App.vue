<template>

  <v-app>

    <!-- NavBar -->
    <navBar></navBar>

    <!-- Greetings -->
    <greetings></greetings>
      
    <!-- NameGame -->
    <namegame></namegame>
    
    <!-- Twitter card -->
    <twitterCard></twitterCard>

    <!-- PictureCards -->
    <pictureCards></pictureCards>
    
    <!-- Comments -->
    <comments></comments>

  </v-app>

</template>

<script>

import navBar from './components/nav'
import greetings from './components/greetings'
import namegame from './components/nameGame'
import twitterCard from './components/twitter'
import pictureCards from './components/pictureCards'
import comments from './components/comments'

export default {
  name: 'App',

  components: {
    navBar,
    greetings,
    namegame,
    twitterCard,
    pictureCards,
    comments
    
  },

  data: () => ({}),

  methods: {}

};
</script>