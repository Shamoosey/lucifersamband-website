<template>
    <div>
      <div class="section">
        <!-- <img class="main-background-image" v-bind:src="require(`@/assets/background.jpg`)"/> -->
      </div>
      <div class="section">
      </div>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})

export default class Home extends Vue {
}
</script>

<style>
  .main-background-image {
    max-height: auto;
  }
</style>
