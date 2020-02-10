<template>
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

</template>

<script>
export default {
    name: 'pictureCards',

    data: () => ({

        cards: [
        { title: 'Rambo the Mangy mutt', src: 'https://lh3.googleusercontent.com/Nd_4xnQiWDs_H-wX0cK797PvDbcSK1V5S_wYGruB5WnRvp_d1qmtFj3NUW3iI2HuZxII2QSgp8q8gS8vauHaq9ckt6IvoTiLVMgBNK6vNTxHS2G3bR21CLadzbkkTUfJGZVMD2RVTfDEjgwgHZOpdriSZJ9pQIyhB1mHQDyFtF1B0kMN8iMOqIuApW4Pohh4t6aXj0k5SN4-yHF3sjkVFXb-6u5Xxk8iO-C7lWq9TeYc5estXB-G3XrzMRqoNLOz_n-LBtRVxKwK7VSFLIAV_s7biC_3XDtIYRujbQPvaRxPmb4GqIgi8EfbXNjCuV8Jmgaq1xtKvGLWWA401eUZ-YL2qlYF-bCKksidz7Jpn0THnzs_Hn7Ky_m99rQG7PvZDgcjPnDdH_7AYkzumSsDwpwFyYKjU3MHX2BG5RxHlIj8uJIsvRjeRU-SsonblyN7FzyBzvfKFJ3e0eMZyi-rZ_Bt0T2MQavUtMWsDMkdh0yuVc9_EmJQc_CZ-pGcrJZXCYjyUXbTTcg_O_7GnSxFbfxT5MRUUWANPKPxvQxH0U-Xyf1clCdp1RyrejqSd4dQhHKPwQIV0t7bZa-8W9oI2FI4KC_ENrrrmtZc-Id1KX0IqtEmopPOvN10ddMz-r13P9j2TxkkiWyS5om_LW9QiXI1UYbD91OmW_Ll43DWvjbUQMqj0AJwIMs=w756-h1007-no', flex: 12 },
        ],
        like1: 0,
        
    }),
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
}
</script>

<style>

</style>