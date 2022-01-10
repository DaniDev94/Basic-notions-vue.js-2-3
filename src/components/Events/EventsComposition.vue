<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Eventos Vue.js 3</h2>
        <h2>Coches - Eventos Composition API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }}CV</p>
        <button @click="upPower">➕ CV</button>
        <button @click="downPower(50)">➖ CV</button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "EventsComposition",
  components: {},
  props: {},

  setup(props, context) {
    const brand = "Audi";
    const model = "A3";
    const power = 90;

    const upPower = () => {
      alert("Esto es la prueba de aumentar potencia en Composition Api.");
    };

    const downPower = (newPower) => {
      alert("Esto es la prueba de disminuir potencia en Composition Api. " + `Nueva potencia inferior ${newPower}CV`);
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