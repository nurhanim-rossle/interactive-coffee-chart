<template>
  <div class="hello">
    <b-container fluid style="padding: 0; margin: 0;">
<!--       <transition name="fade">
        <div class="overlay-bg" v-show="showContent">
          <div class="overlay">
            <div>
              <coffee-content :name="selectedCoffee" :caffein="caffeinContent" :calories="caloriesContent" :caloriesperoz="caloriesperozContent">
              </coffee-content>
            </div>
          </div>
        </div>
      </transition> -->
      <transition name="fade">
        
              <coffee-content  v-show="showContent" :name="selectedCoffee" :caffein="caffeinContent" :calories="caloriesContent" :caloriesperoz="caloriesperozContent">
              </coffee-content>
      </transition>
      
      <div>
        <font-awesome-icon icon="mug-hot" size="5x"/>
        <h1>{{ msg }}</h1>
        <b-container>
          <b-row class="coffees">
            <coffee-type v-for="CoffeeType in CoffeeTypes" :key="CoffeeType.type" :name="CoffeeType.type" :img="CoffeeType.img" @selected="selectCoffee" :selected-coffee="selectedCoffee" :style=" showContent ? selectedCoffee === CoffeeType.type ? 'opacity : 1' : 'opacity : 0.2' : 'opacity: 1' ">
            </coffee-type>
          </b-row>
        </b-container>
      </div>
    </b-container>
  </div>
</template>

<script>
import CoffeeType from './CoffeeType.vue'
import CoffeeContent from './CoffeeContent.vue'

export default {
  name: 'CoffeeChart',
  props: {
    msg: String,
  },
  components: {
    'coffee-type' : CoffeeType,
    'coffee-content' : CoffeeContent
  },
  data() {
    return {
      CoffeeTypes: [
        {
          type: 'Espresso',
          caffein: '80',
          calories: '190',
          caloriesperoz: '10',
          img : require('@/assets/images/espresso.png')
        },
        {
          type: 'Americano',
          caffein: '70',
          calories: '150',
          caloriesperoz: '20',
          img: require('@/assets/images/americano.png')
        },
        {
          type: 'Latte',
          caffein: '55',
          calories: '195',
          caloriesperoz: '15',
          img: require('@/assets/images/latte.png')
        },
        {
          type: 'Cappuccino',
          caffein: '82',
          calories: '192',
          caloriesperoz: '12',
          img: require('@/assets/images/cappuccino.png')
        }
      ],
      selectedCoffee: null,
      caffeinContent: null,
      caloriesContent: null,
      caloriesperozContent: null,
      showContent: false
    }
  },
  computed: {
    selectCoffeeContent() {
      let coffeeContents = []

      for (let i = 0; i < this.CoffeeTypes.length; i++) {
        if(this.CoffeeTypes[i].type === this.selectedCoffee) {
          coffeeContents.push(this.CoffeeTypes[i].caffein)
          coffeeContents.push(this.CoffeeTypes[i].calories)
          coffeeContents.push(this.CoffeeTypes[i].caloriesperoz)
        }
      }
      return coffeeContents
    }
  },
  methods: {
    selectCoffee(CoffeeType) {
      this.selectedCoffee = CoffeeType
      this.caffeinContent = this.selectCoffeeContent[0]
      this.caloriesContent = this.selectCoffeeContent[1]
      this.caloriesperozContent = this.selectCoffeeContent[2]
      this.showContent = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  padding: 0 !important;
  margin: 0px !important;
}
h1 {
  font-family: 'Caveat', cursive, Helvetica, Arial, sans-serif;
  font-size: 4em;
}

.coffees {
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  bottom: 30px;
}

.fade-enter{
        opacity: 0;
    }
    .fade-enter-active{
        transition: opacity 1s;
    }
    .fade-leave{
        /* opacity: 1; */
    }
    .fade-leave-active{
        transition: opacity 1s;
        opacity: 0;
    }

</style>
