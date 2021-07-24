<template>
  <div id="navbar-wrapper">
    <v-app-bar class="navbar-main">
      <v-app-bar-nav-icon @click="drawer = true" class="navbar-main-menuicon"></v-app-bar-nav-icon>
      <v-toolbar-title ><v-btn text :href="'/'" class="navbar-main-title">LuciferSamBand</v-btn></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon href="https://www.instagram.com/lucifersamband/" target="_blank">
        <v-icon class="navbar-main-socialicon">mdi-instagram</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer :overlay-opacity=".5" v-model="drawer" temporary class="navbar-drawer">
      <v-list nav>
        <v-list-item-group v-for="data in navData" :key="data">
          <v-list-item :href="`#${data.redirect}`">
            <v-list-item-title>{{data.title}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"
import { Interfaces } from "../interfaces"

@Component({
  components: {
  }
})

export default class Navbar extends Vue {
  drawer:boolean = false

  navData:Interfaces.NavBarItem [] = [
    {
      title: "Music",
      icon: "mdi-music",
      redirect: "spotify-artist"
    },
    {
      title: "About",
      icon: "mdi-information-outline",
      redirect: ""
    }
  ]
}
</script>

<style>
  .navbar-main{
    background-color: transparent !important;
    box-shadow: none !important;
    padding: 10px;
    margin-bottom: 10px;
  }
  .navbar-drawer{
    margin: 10px;
    border-radius: 5px;
    /* background-color: transparent !important; */
    box-shadow: none !important;
  }
  .navbar-main-title {
    color: white !important;
  }
  .navbar-main-title:hover {
    color: white !important;
  }
  .navbar-main-menuicon{
    color: white !important;
  }
  .navbar-main-socialicon{
    color: white !important;
  }
</style>
