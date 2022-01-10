<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Recorrer arrays y objetos (Loops) Vue.js 3</h2>
        <h2>Coches - Directiva v-for</h2>
        <!-- Pasando una key única o el indice, los dos puntos indican que es dinamico, que puede cambiar, de esta manera si se produce algun cambio puede sabe cual ha sido -->
        <h3>Con Key única</h3>
        <div v-for="carK in allCarsKey" :key="carK">
          <p>{{ carK }}</p>
        </div>
        <h3>Con Index</h3>
        <div v-for="(carI, index) in allCarsIndex" :key="index">
          <p>{{index}}: {{ carI }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Loops',
  components: {},
  props: {},
  setup(props, context) {
    const allCarsKey = ["BMW M3", "Audi A5", "Toyota GT86", "Seat Leon FR"];
    const allCarsIndex = ["BMW M6", "Audi A3", "Toyota Yaris", "Seat Ibiza FR"];

    return {
      allCarsKey,
      allCarsIndex,
    };
  },
};
</script>


<style>
</style>