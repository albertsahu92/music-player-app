<template>
<div class="pa-6">
  <h1> My Playlists</h1>
  <v-divider> </v-divider>

  <div>

    <v-list>
      <v-list-group
        v-for="item in items"
        :key="item.title"
        
        :prepend-icon="item.action"
        no-action
        
        
      >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item-content>
        </template>

        <v-list-item
          v-for="child in item.items"
          :key="child.title"
          link
        >
          <v-list-item-content>
            <v-list-item-title v-text="child.title"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-group>
    </v-list>
  

  </div>



</div>
</template>

<script>
 

  export default {
    name: 'Playlist',

    data () {
      return {
         items: [
        {
          action: 'mdi-playlist-play',
          active: true,
          items: [
            { title: 'Jazz Song-1' },
            { title: 'Jazz Song-2' },
            { title: 'Jazz Song-3' },
          ],
          title: 'Jazz',
        },
        {
          action: 'mdi-playlist-play',
          active: true,
          items: [
            { title: 'Pop Song-1' },
            { title: 'Pop Song-2' },
            { title: 'Pop Song-3' },
          ],
          title: 'Pop',
        },
        {
          action: 'mdi-playlist-play',
          active: true,
          items: [
            { title: 'Rock Song-1' },
            { title: 'Rock Song-2' },
            { title: 'Rock Song-3' },
          ],
          title: 'Rock',
        },
        {
          action: 'mdi-playlist-play',
          active: true,
          items: [
            { title: 'K-Pop Song-1' },
            { title: 'K-Pop Song-2' },
            { title: 'K-Pop Song-3' },
          ],
          title: 'K-Pop',
        },
        {
          action: 'mdi-playlist-play',
          active: true,
          items: [
            { title: 'J-Pop Song-1' },
            { title: 'J-Pop Song-2' },
            { title: 'J-Pop Song-3' },
          ],
          title: 'J-Pop',
        },
        
      ],

      }      
    },
  }
</script>
