<template>
  <v-app class="overflow">
    <Navbar />
    <Slider />
    <v-content class="primary--text">
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
import Navbar from './components/Navbar';
import Slider from './components/Slider';
export default {
  name: 'App',

  components: {
    Navbar, Slider
  },

  data: () => ({
    //
  }),
};
</script>
<style>
.overflow {
  overflow-x: hidden;
  overflow-y: scroll;
}
</style>