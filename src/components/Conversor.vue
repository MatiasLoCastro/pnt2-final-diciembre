<template>

  <section class="src-components-conversor">
     <div class="jumbotron">
      <h2>Conversor De Temperatura</h2>
      <hr>
      <br>
        <label for="tempCelsius">{{ mensajeInput }}</label>
        <input type="number" v-model="tempCelsius" id="tempCelsius">
      <br>
      <div :class="{ 'blue-text': tempCelsius <= 0, 'red-text': tempCelsius >= 15, 'magenta-text': tempCelsius > 0 && tempCelsius < 15 }">{{ mensajeTempF }} <label >{{ farenheit }}</label></div> 
      <br>
      <div :class="{ 'blue-text': tempCelsius <= 0, 'red-text': tempCelsius >= 15, 'magenta-text': tempCelsius > 0 && tempCelsius < 15}">{{ mensajeTempK }} <label >{{ kelvin }}</label></div> 

    <p>1: C</p>
    <p>2: B</p>
    <p>3: C</p>
    <p>4: C</p>
    <p>5: B</p>
    </div>
  </section>

</template>

<script>

  export default  {
    name: 'src-components-conversor',
    props: [],
    mounted () {


    },
    data () {
      return {
      mensajeInput: 'Ingrese Temperatura °C',
      mensajeTempF: 'Conv Temperatura °F',
      mensajeTempK: 'Conv Temperatura °K',
      tempCelsius: 0,
      }
    },
    methods: {

    },
    computed: {

      kelvin: function() {
        return parseFloat(this.tempCelsius + 273.15);
      },

      farenheit: function() {
         return (this.tempCelsius * 9/5) + 32;
      }


    }
}


</script>

<style scoped lang="css">
  .jumbotron {
    background-color: white;
    color: #111;
    margin-left: 20px;
  }

  hr {
    background-color: #111;
  }

  h2 {
      margin-left: 20px;
    }

  .blue-text {
      color: blue;
    }

    .red-text {
      color: red;
    }

  .magenta-text {
    color: magenta;
  }
</style>
