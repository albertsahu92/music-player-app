<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
    >
     <v-avatar
      color="indigo"
      size="100"
      class="ml-5 mt-3"
    >
      <span class="white--text headline">TU</span>
    </v-avatar>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Test User
          </v-list-item-title>
          <v-list-item-subtitle>
            testuser@blackmail.com
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
    <v-list>
      <v-list-item
          v-for="item in sideMenu"
          :key="item.title"
          :to ="item.to"
          link
        >

          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    </v-navigation-drawer>

    



    <v-app-bar app elevate-on-scroll>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Music Player</v-toolbar-title>
      
      <v-spacer></v-spacer>


      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null,
    sideMenu: [
      { title: 'Home', icon: 'mdi-home-circle', to: '/' },
      { title: 'Playlists', icon: 'mdi-playlist-play', to: '/playlist' },
      { title: 'Songs ', icon: 'mdi-music-box', to:'/songs' },
      { title: 'About', icon: 'mdi-help-box', to:'/about'},
      
    ], right: null })
  }
</script>
