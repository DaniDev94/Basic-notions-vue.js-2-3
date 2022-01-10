<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Binding Vue.js 3</h2>
        <h2>Coches - Binding Composition API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}CV</p>
        <button @click="upPower">➕ CV</button>
        <button @click="downPower(10)">➖ CV</button>
      </div>
    </div>
  </div>
</template>


<script>
//Importamos la funcion ref() para poder realizar el binding en composition Api
import { ref } from "vue";

export default {
  name: "BindingComposition",
  components: {},
  props: {},

  setup(props, context) {
    const brand = "Audi";
    const model = "A3";
    //Inicializamos la variable con ref y le pasamos el valor
    let power = ref(50);

    const upPower = () => {
      //Una vez inicializada la variable con ref, accedemos a su valor con '.value'
      console.log(power.value + 5)
      //Ahumentamos la potencia accediendo a su valor
      power.value++
    };

    const downPower = (newPower) => {
      power.value = power.value - newPower;
    };

   //La funciones se exportan igual que las variables
    return {
      brand,
      model,
      power,
      upPower,
      downPower,
    };
  },
};
</script>


<style>
</style>