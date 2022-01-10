<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Props Funciones Vue.js 3</h2>
        <h2>Coches - Props Composition API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }} CV</p>
        <button @click="newUpPowerCar">➕ CV</button
        ><span> ➡️ Prop function in function</span>
        <hr />
        <!-- Le pasamos directamente la funcion que recibimos por prop -->
        <button @click="upPower">➕ CV</button
        ><span> ➡️ Prop only function</span>
        <p>
          App.vue es el padre (emisor) y PropsFunction.vue el hijo (receptor)
        </p>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "PropsFunction",
  components: {},
  //En las funciones, le pasamos directamente el tipo a la prop sin darle valor por defecto ni alojando el tipo en la key type
  props: {
    power: {
      type: Number,
      default: 90,
    },
    //Nos traemos la funcion de App.js en prop
    upPower: Function,
  },

  // Pasamos la prop como parametro en setup para poder trabajar con los datos, si asi no necesitaramos.
  setup(props) {
    const brand = "Toyota";
    const model = "Supra";
    //Muestra el nombre de la función que recibe --> console.log(props)

    /*
     * Dos formas de recibir las funciones por props:
     *
     * 1- Invocandola en una nueva función
     * 2- Pasandole directamente la función que recibimos por props
     *
     */
    const newUpPowerCar = () => {
      props.upPower();
    };

    //Exportamos la funcion
    return {
      brand,
      model,
      newUpPowerCar,
    };
  },
};
</script>


<style>
p {
  font-size: 1.02rem;
}
</style>