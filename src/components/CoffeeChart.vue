<template>
  <div class="hello">
    <b-container fluid>
      <div class="overlay">
        <div class="h-100" align-v="center">
          <coffee-content class="coffee-content-template" v-show="showContent" :name="selectedCoffee" :caffein="caffeinContent" :calories="caloriesContent" :caloriesperoz="caloriesperozContent">
          </coffee-content>
        </div>
      </div>

      <div>
        <font-awesome-icon icon="mug-hot" size="8x"/>
        <h1>{{ msg }}</h1>
        <b-container>
          <b-row >
            <coffee-type v-for="CoffeeType in CoffeeTypes" :key="CoffeeType.type" :name="CoffeeType.type" :img="CoffeeType.img" @click="overlayToggle()" @selected="selectCoffee" :selected-coffee="selectedCoffee">
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
          img : 'espresso.png'
        },
        {
          type: 'Americano',
          caffein: '70',
          calories: '150',
          caloriesperoz: '20',
          img: 'americano.png'
        },
        {
          type: 'Latte',
          caffein: '55',
          calories: '195',
          caloriesperoz: '15',
          img: 'latte.png'
        },
        {
          type: 'Cappuccino',
          caffein: '82',
          calories: '192',
          caloriesperoz: '12',
          img: 'cappuccino.png'
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

h1 {
  font-family: 'Caveat', cursive, Helvetica, Arial, sans-serif;
  font-size: 4em;
}

.overlay {
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: auto;
}

.coffees {
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  bottom: 60px;
}
</style>
