<template>
  <div id="navbar">
      <v-app-bar
        color="deep-purple accent-4"
        dense        
      >
        <v-toolbar-title>Lucifersam band</v-toolbar-title>
        <v-spacer></v-spacer>
        
        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-menu
          left
          bottom
        >
        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            @click="() => {}"
          >
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      </v-app-bar>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator"

@Component({
  components: {
  }
})

export default class Navbar extends Vue {

}
</script>

<style>
</style>
