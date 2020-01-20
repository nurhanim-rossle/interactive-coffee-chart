<template>
  <b-col>
    <div class="coffee-content">
      <h1>{{name}}</h1>
      <b-row class="coffee-content-row h-100" align-v="center">
        <b-col>
          Caffein Content
          <h2>{{caffein}}</h2>
        </b-col>
        <b-col>
          Calories
          <h2>{{calories}}</h2>
        </b-col>
        <b-col>
          Calories per oz
          <h2>{{caloriesperoz}}</h2>
        </b-col>
      </b-row>
    </div>
  </b-col>
</template>

<script>
export default {
  name: 'CoffeeContent',
  props: {
    name: String,
    caffein: String,
    calories: String,
    caloriesperoz: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .coffee-content-row {
  }
</style>
