<template>
  <div class="home">
    <h1>Category</h1>
    <v-sheet class="mx-auto">
      <v-slide-group v-model="model">
        <v-slide-item v-for="n in 15" :key="n" v-slot:default="{ active, toggle }">
          <v-card :elevation="active ? 8 : 4" flat tile outlined class="mr-2 my-2" height="100" width="100" @click="toggle">
            <v-row class="fill-height" align="center" justify="center">
              <img src="https://image.flaticon.com/icons/svg/1046/1046784.svg" height="70%" width="70%">
              <span class="teal--text">Breakfast</span>
            </v-row>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>
    <v-content>
      <router-view></router-view>
    </v-content>
  </div>
</template>

<script>
export default {
  name: 'Home',
  components: {
    //this.$router.push('/')
  },
  data: () => ({
    model: null,
  }),
}
</script>