<template>
  <b-col>
    <div class="coffee-content">
      {{name}}
      <b-row>
        <b-col>
          Caffein Content
          <p>{{caffein}}</p>
        </b-col>
        <b-col>
          Calories
          <p>{{calories}}</p>
        </b-col>
        <b-col>
          Calories per oz
          <p>{{caloriesperoz}}</p>
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

.coffee-content {
  background-color: rgba(76, 175, 80, 0.9);
  height: 100%;
}

</style>
