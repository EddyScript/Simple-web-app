<template>
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
    
</template>

<script>
export default {
    name: 'nameGame',

    data: () => ({

        list: [ "Vue Express Node.js MongoDB", 'Victor Exports Number Modules', 'Vanessa Enjoys Negotiating Money', 'Vipers Engulfs Nine Mice','Venom Escapes Near Metropolis','Very Enjoyable Night Music',"Violet Exposes Neptune's Mystery "],
        chosenName: '',
        
    }),
    methods: {

        picker: function() {
            var chosenNumber = Math.floor(Math.random() * this.list.length)
            this.chosenName = this.list[chosenNumber];
        }
    }
}
</script>

<style>

</style>