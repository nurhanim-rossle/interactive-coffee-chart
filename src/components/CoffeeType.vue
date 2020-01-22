<template>
  <b-col>
    <div class="coffee-types">
      <div v-bind:id="name" @click="selectCoffeeType" :class="{'active-coffee': isSelected}">
        <img :src="img">
      </div>
    </div>
  </b-col>
</template>

<script>

// import CoffeeContent from './CoffeeContent.vue'

export default {
  name: 'CoffeeType',
  props: {
    name: String,
    selectedCoffee: String,
    img: String
  },
  data: function () {
    return {
    }
  },
  computed: {
    isSelected() {
      return this.name === this.selectedCoffee
    }
  },
  methods: {
    selectCoffeeType() {
      this.$emit('selected', this.name)
      this.selected = true
    }
  }
}
</script>

<style scoped>

</style>
