<template>
  <b-col>
    <div class="coffee-content">
      <b-row class="coffee-content-row h-100" align-v="center">
        <b-col class="coffee-name">
          <div class="diamond transform">
            <div class="text">
              <h2 class="title">{{name}}</h2>
            </div>
          </div>
        </b-col>
        <b-col>
          Caffein
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
  .diamond {
    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    margin: auto;
    width: 180px;
    height: 180px;
    overflow: hidden;
    border: #ffffff 1px solid;
    margin-left: 50px;
  }

  h2 {
    padding: 0px;
    margin: 0px;
  }

  .title {
    padding-top: 65px;
  }

  .transform {
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    transform: rotate(45deg);
  }

  .text {
    width: 100%;
    height: 100%;
    text-align: center;
    -webkit-transform: rotate(-45deg);
    -moz-transform: rotate(-45deg);
    -o-transform: rotate(-45deg);
    -ms-transform: rotate(-45deg);
    transform: rotate(-45deg);
  }

.fade-enter-active, .fade-leave-active {
  transition: opacity 1s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

</style>
