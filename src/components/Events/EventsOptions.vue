<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Eventos Vue.js 2</h2>
        <h2>Coches - Eventos Options API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}CV</p>
        <!-- Le añadimos el valor del parametro en la invocación de la función en el evento. Podemos añadir todo tipo de datos a las funciones -->
        <button @click="upPower(550)">➕ CV</button>
        <button @click="downPower">➖ CV</button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "EventsOptions",
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
  // Podemos añadir parametros a la funcion que ejecutara el evento
  methods: {
    upPower(newPower) {
      alert("Esto es la prueba de aumentar potencia en Options Api. " + `Nueva potencia superior ${newPower}CV`);
    },
    downPower() {
      alert("Esto es la prueba de disminuir potencia en Options Api");
    },
  },
};
</script>


<style>
</style>