<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Props variables Vue.js 3</h2>
        <h2>Coches - Props Composition API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <!-- Le pasamos la el nombre de la prop como si fuera una variable para añadirla el template -->
        <p>Potencia: {{ power }} ➡️ Prop Variable</p>
        <span>App.vue es el padre (emisor) y PropsVariables.vue el hijo (receptor)</span>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "PropsVariables",
  components: {},
  // Declaramos la prop en el componente que la va a recibir, asignando un valor por defecto en el caso de que no recibiera nada muestre dicho contenido por defecto. Definir siempre el tipo y un valor por defecto.
  props: {
    power: {
      type: Number,
      default: 10,
    },
  },

  //En este caso app es el padre y el componente Props el hijo ( que se encarga de renderizarlo )

  // Pasamos la prop como parametro en setup para poder trabajar con los datos, si asi no necesitaramos. 
  setup(props) {
    const brand = "Bmw";
    const model = "M4";

  // Muestra el contenido limpio de la prop en consola --> console.log(props.power)

    return {
      brand,
      model,
    };
  },
};
</script>


<style>
</style>