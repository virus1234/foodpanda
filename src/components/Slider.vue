<template>
  <v-carousel continuous interval="5000" height="auto" cycle hide-delimiter-background show-arrows-on-hover>
    <v-carousel-item v-for="(slide, i) in slides" :key="i">
      <v-sheet :color="colors[i]" max-height="400">
        <v-row class="fill-height" style="overflow: hidden;" align="center" justify="center">
          <v-img :src="items[i]" aspect-ratio="1.78"></v-img>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>
<script>
  export default {
    data () {
      return {
        sliderSize: 0,
        items: [
          { src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg', },
          { src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg', },
          { src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg', },
          { src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg', },
        ],
        colors: [ 'indigo', 'warning', 'pink darken-2', 'red lighten-1', ],
        slides: [ 'First', 'Second', 'Third', 'Fourth', ],
      }
    },
    created() {
      if(window.innerWidth < 600) {
        this.sliderSize = 2.11
      } else {
        this.sliderSize = 1.78
        console.log(this.sliderSize)
      }
    },
  }
</script>