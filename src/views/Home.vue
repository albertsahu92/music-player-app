<template>
  <div class="pa-4">
    <h1> Recently Played</h1>
    <v-divider></v-divider>
   <v-slide-group
      v-model="model"
      center-active
      class="pa-2"
      active-class="indigo"
      show-arrows
    >
   
      <v-slide-item
        v-for="n in 16"
        :key="n"
        v-slot="{ active, toggle }"
      >
      <v-hover v-slot="{hover}">
        <v-card
          :color="active ? undefined : 'grey lighten-1'"
          class="ma-4"
          height="200"
          width="200"
          @click="toggle"
          :elevation="hover ? 12:2"
          :class="{'on-hover': hover}"
        >
     
          
          
            <v-scale-transition>
              <v-icon
                v-if="active"
                color="white"
                size="48"
                
              ></v-icon>
            </v-scale-transition>
          </v-row>
        </v-card>
      </v-hover>
      </v-slide-item>
    </v-slide-group>

  <v-expand-transition>
      <v-sheet
        v-if="model != null"
        height="200"
        tile
        
      >
        <v-col
          class="fill-height"
          align="center"
          justify="center"
        >
          <h3 class="title ma-3">
            Song - {{ model }}
          </h3>
          
          <v-btn v-for="(icon,index) in icons"
          :key="index"
          icon
          class = "ma-3"
          > 
            <v-icon> {{icon}} </v-icon>

          </v-btn>
          


        </v-col>
        
      </v-sheet>
    </v-expand-transition>


  <h1>Recently Added</h1>

  <v-divider> </v-divider>
  
    <v-list nav>
      <v-list-item-group
        v-model="model1"
        
        color="indigo"
      >
      <div v-for="(item, i) in items"
          :key="i">
        <v-list-item
          
        >
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
          </v-list-item-icon>
        <v-row>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
          <div>
          <v-btn v-for="(icon,index) in icons"
          :key="index"
          icon
          class = "ma-2"
          > 
            <v-icon
            > {{icon}} </v-icon>

          </v-btn>
          </div>
        </v-row>
          
        </v-list-item>
        <v-divider></v-divider>
        </div>
      </v-list-item-group>
      
      
      
    
    </v-list>


  </div>


</template>

<script>
  export default {
    name: 'Home',

    data: () => ({
      model:null,
      icons: ['mdi-rewind', 'mdi-play', 'mdi-fast-forward'],
      items: [
        {
          icon: 'mdi-heart-outline',
          text: 'Song-1',
        },
        {
          icon: 'mdi-heart-outline',
          text: 'Song-2',
        },
        {
          icon: 'mdi-heart-outline',
          text: 'Song-3',
        },
        {
          icon: 'mdi-heart-outline',
          text: 'Song-4',
        },
        {
          icon: 'mdi-heart-outline',
          text: 'Song-5',
        },
      ], model1:0,
      transparent: 'rgba(255, 255, 255, 0)',
    }),
  }
</script>


<style scoped> 

.show-btns {
  color: rgba(255, 255, 255, 1) !important;
}

</style>
