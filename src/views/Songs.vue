<template>
<div class="pa-6">
  <h1> Song Lists </h1>
  <v-divider></v-divider>
  <v-list>
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

          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
          
        </v-list-item>
        <v-divider></v-divider>
        </div>
      </v-list-item-group>
      
    
    </v-list>


  </div>

  
</div>
</template>

<script>
export default {
    name: 'Songs',
   data : () => ({ items: [
        {
          icon: 'mdi-play-circle',
          text: 'Song-1',
        },
        {
          icon: 'mdi-play-circle',
          text: 'Song-2',
        },
        {
          icon: 'mdi-play-circle',
          text: 'Song-3',
        },
        {
          icon: 'mdi-play-circle',
          text: 'Song-4',
        },
        {
          icon: 'mdi-play-circle',
          text: 'Song-5',
        },
      ], model1:1

    })
  }
</script>
