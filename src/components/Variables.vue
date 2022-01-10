<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <h2>Declaración de variables en Vue.js 2 y 3</h2>
        <h2>Coches - Obtención de datos en variables</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Color: {{ color[1] }}</p>
        <p>Precio: {{ price }}$</p>
        <p>Potencia: {{ power }}CV</p>
        <p>Descripcion: {{ message.title }}, {{ message.text }}</p>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'Variables',
  components: {},
  props: {},
  //Ambas formas de declarar variables muestran el mismo resultado 

  //Con Options API -->

  /* data(){
    return{
      brand: "BMW",
      model: "M3",
      color: ["Negro", "Blanco", "Rojo"],
      price: 25000,
      power: 240,
      message: {
        title: "Me lo quitan de las manos chacho",
        text: "los quilometros son reales, nada de estafar a los payos."
      }
    };
  }, */

  //Con Composition API -->

  setup(props, context){
    const brand = "BMW";
    const model = "M3";
    const color = ["Negro", "Blanco", "Rojo"];
    const price = 25000;
    const power = 240;
    const message = {
      title: "Me lo quitan de las manos chacho",
      text:  "los quilometros son reales, nada de estafar a los payos."
    }
    return {
      brand,
      model,
      color,
      price,
      power,
      message
    };
  },
};
</script>


<style>

.b-container {
  width: 100%;
  min-height: 40vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2rem;
}

.b-card {
  width: 40rem;
  background-color: #41b883;
  border: 3px solid black;
  box-shadow: 0px 0px 27px 9px rgba(0, 0, 0, 0.137);
  border-radius: 3rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
}

.b-text {
  margin: 0 2rem 0 2rem;
  text-align: center;
}

@media (max-width: 576px) {
  .b-text {
    margin: 0;
  }
}

h2 {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  color: rgb(2, 2, 2);
  font-size: 1.5rem;
}
</style>