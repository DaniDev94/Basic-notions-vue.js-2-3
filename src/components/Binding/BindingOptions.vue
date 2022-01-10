<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Binding Vue.js 2</h2>
        <h2>Coches - Binding Options API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}CV</p>
        <!-- Le añadimos el valor del parametro en la invocación de la función en el evento. Podemos añadir todo tipo de datos a las funciones -->
        <button @click="upPower(10)">➕ CV</button>
        <button @click="downPower">➖ CV</button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "BindingOptions",
  components: {},
  props: {},

  data() {
    return {
      brand: "Seat",
      model: "Leon FR",
      power: 90,
    };
  },
  // En methods posicionamos las funciones que añadiremos al template(renderizado)
  // Podemos añadir parametros a la funcion que ejecutara el evento y tambien emplearlo en el binding

  //Binding --> Su funcionamiento radica en asociar las variables a un elemento del DOM y cada vez que esta cambia también lo hará el elemento o lo que es lo mismo, binding es vincular
  methods: {
    upPower(newPower) {
      this.power = this.power + newPower
    },
    downPower() {
      this.power--;
    },
  },
};
</script>


<style>
</style>