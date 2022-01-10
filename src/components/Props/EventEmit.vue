<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <div class="b-content">
          <h2 class="b-content__title">Custom Event:Emit Vue.js 3</h2>
        </div>
        <h2>Coches - Event:Emit Composition API</h2>
        <p>Marca: {{ brand }}</p>
        <p>Modelo: {{ model }}</p>
        <p>Potencia: {{ power }} CV</p>
        <button @click="downPowerEmit">➖ CV</button>
        <span> ➡️ Custom event: Emit</span>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "EventEmit",
  components: {},
  props: {
    power: {
      type: Number,
      default: 90,
    },
    upPower: Function,
  },
  //Objeto emits:{} similar al obejeto props:{} se puede emplear para definir los eventos que un componente puede puede emitir a su padre, en este caso lo utilizamos para recibir la función que aloja App.js el cual envia el evento mediante Custom event:emit
  emits: ["downPower"],

  //Para utilizar el custom event:emit empleamos la variable context del parametro de setup()
  setup(props, context) {
    const brand = "Toyota";
    const model = "Supra";

    //Muestra en la función expose, de momento no tiene datos --> console.log(context)

    //Declaramos una nueva función para disminuir la potencia donde usaremos el context y el emits para traer la funcion de App.js
    //Para utilizar el context y traer la info de emits empleamos --> context.emit("nombre declarado en emits, este caso aloja la función de App.js downPowerCar()")
    const downPowerEmit = () => {
      context.emit("downPower");
    };

    return {
      brand,
      model,
      downPowerEmit,
    };
  },
};
</script>


<style lang="scss">
// Para usar scss añadir en la etiqueta style el lenguaje especifico --> lang="scss" o vacio para usar css
p {
  font-size: 1.02rem;
}

// Con scss y BEM
.b-content{
  border: 1px solid white;
  border-radius: 3rem;
  &__title{
    margin: 0.2rem;
    color:rgb(30, 68, 38);
    letter-spacing: 0.2rem;
  }
}
</style>