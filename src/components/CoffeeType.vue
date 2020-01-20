<template>
  <b-col>
    <div class="coffee-types">
      <div v-bind:id="name" @click="selectCoffeeType" :class="{'active-coffee': isSelected}">
        <font-awesome-icon class="coffee-icon" icon="coffee" size="3x"/>
        <img :src="img">
      </div>
      <b-tooltip :target="name" :title="name"></b-tooltip>
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
.active-coffee {
  color: #654321;
}
.coffee-icon {
}
.coffee-icon:hover {
  color: #654321;
}
</style>
