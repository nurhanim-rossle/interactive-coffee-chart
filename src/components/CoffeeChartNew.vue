<template>
  <div>
    <!-- <button @click="$refs.myVueperSlides[`${autoPlaying ? 'pause' : 'resume'}Autoplay`]();autoPlaying = !autoPlaying">
      {{ autoPlaying ? 'Pause' : 'Resume' }}
    </button>
    <button @click="pauseOnHover = !pauseOnHover">Pause on mouseover</button>
    <code>Currently {{ internalAutoPlaying ? 'playing' : 'paused' }}</code> -->

    <vueper-slides fade
      ref="myVueperSlides"
      fixed-height="100vh"
      class="no-shadow"
      :arrows="false"
      :touchable="false"
      prevent-y-scroll>
      <vueper-slide
       v-for="(slide, i) in slides" :key="i"
        >
        <template v-slot:content=""> 
          <div class="vueperslide__content-wrapper" :style="`background-image: url(${slide.image})`">
            <b-row align-v="center" class="caffein-info">
              <b-col>
                Caffein
                <h2>{{slide.caffein}}</h2>
              </b-col>
              <b-col>
                Calories
                <h2>{{slide.calories}}</h2>
              </b-col>
              <b-col>
                Calories per oz
                <h2>{{slide.caloriesperoz}}</h2>
              </b-col>
            </b-row>
            <p>
              <img :src="slide.img" />
            </p>
            <h1>{{ slide.title }}</h1><br/>
            <p>{{ slide.content }} one two three</p><br/><br/>
            <p>Documentation @<a href="https://antoniandre.github.io/vueper-slides">antoniandre.github.io/vueper-slides</a></p>
          </div>
      </template>
      click click click
    </vueper-slide>
    </vueper-slides>
  </div>
</template>

<script>

import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

export default {
  name: 'CoffeeChartNew',
  components: { VueperSlides, VueperSlide },
  props: {
    colors: String
  },
  data: () => ({
    pauseOnHover: true,
    autoPlaying: false,
    internalAutoPlaying: false,
    arrows: false,
    slides: [
      {
        title: 'Mountain 1',
        content: 'Slide 1 content.',
        image: 'https://images.pexels.com/photos/355241/pexels-photo-355241.jpeg?&w=1800',
        caffein: '80',
        calories: '190',
        caloriesperoz: '10',
        img : require('@/assets/images/espresso.png')
      },
      {
        title: 'Mountain 2',
        content: 'Slide 2 content.',
        image: 'https://images.pexels.com/photos/355241/pexels-photo-355241.jpeg?&w=1800',
        caffein: '70',
        calories: '150',
        caloriesperoz: '20',
        img : require('@/assets/images/americano.png')
      },
      {
        title: 'Mountain 3',
        content: 'Slide 3 content.',
        image: 'https://images.pexels.com/photos/355241/pexels-photo-355241.jpeg?&w=1800',
        caffein: '55',
        calories: '195',
        caloriesperoz: '15',
        img : require('@/assets/images/latte.png')
      },
      {
        title: 'Cappuccino',
        content: 'Slide 3 content.',
        image: 'https://images.pexels.com/photos/355241/pexels-photo-355241.jpeg?&w=1800',
        caffein: '82',
        calories: '192',
        caloriesperoz: '12',
        img : require('@/assets/images/cappuccino.png')
      }
    ]
  })
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.vueperslide {
}
.vueperslide__title {
  font-size: 7em;
  opacity: 0.6;
}

/*p {
  position: absolute;
  top: 5px;
  right: 5px;
  z-index: 10;
}*/

html {
  font: 12px Tahoma, Geneva, sans-serif;
}

* {
  margin: 0;
  padding: 0;
  color: #fff;
}

.vueperslide__content-wrapper {
  transition: 5s
}

.caffein-info {
  width: 100%;
}

</style>
