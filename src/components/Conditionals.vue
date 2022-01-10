<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Condicionales Vue.js 3</h2>
        <h2>Coches - Directiva v-if, v-else-if</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>

        <h3>Con v-if</h3>
        <h2>Potencias Urbanas: menores a 280 CV</h2>
        <!-- Añadimos el v-for en el template para que no rederice nada, pero haga el buecle y la condicion en lo que queramos renderizar -->
        <template v-for="(power, index) in powers" :key="index">
          <span v-if="power < 280"> {{ power }}, </span>
        </template>
        <h2>Potencias Competición: mayores de 260 CV</h2>
        <template v-for="(power, index) in powers" :key="index">
          <span v-if="power >= 280"> {{ power }}, </span>
        </template>

        <h3>Con v-if, v-else-if y v-else</h3>
        <template v-for="(power, index) in powers" :key="index">
          <p v-if="power < 260">Urbano: {{ power }}</p>
          <p v-else-if="power === 280 || power === 260">Hibrido: {{ power }}</p>
          <p v-else-if="power === 460 || power === 480">Super: {{ power }}</p>
          <p v-else>Competicion: {{ power }}</p>
        </template>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Conditionals',
  components: {},
  props: {},
  setup(props, context) {
    const brand = "BMW";
    const model = "I8 Spider";
    const powers = [60, 80, 160, 180, 260, 280, 360, 380, 460, 480];

    return {
      brand,
      model,
      powers,
    };
  },
};
</script>

<style>
h3 {
  border-bottom: 2px solid black;
  margin-top: 2rem;
}

p {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  font-size: 1.2rem;
  font-weight: 500;
}
</style>