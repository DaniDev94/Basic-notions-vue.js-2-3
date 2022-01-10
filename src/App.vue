<template>
  <h1>Test Vue.js 3</h1>
  <Variables />
  <Loops />
  <Conditionals />
  <EventsOptions />
  <EventsComposition />
  <BindingOptions />
  <BindingComposition />
  <!-- En la declaracion de la prop ponemos dos puntos (:) para indicarle que es una variable, si se lo quitamos le estariamos pasando un string -->
  <PropsVariables :power="powerCar" />
  <!-- Le pasamos la prop que almacena la funcion para enviarla tambien declarando la prop con dos puntos para indicarle que es una función -->
  <PropsFunction :power="powerCar" :upPower="upPowerCar" />

  <!-- Le pasamos la funcion de disminuir con "Custom event:emit" en vez de props (mismo comportamiento) -->
  <EventEmit :power="powerCar" @downPower="downPowerCar" />
  <StylesNotShared />
</template>

<script>
import Variables from "./components/Variables.vue";
import Loops from "./components/Loops.vue";
import Conditionals from "./components/Conditionals.vue";
import EventsOptions from "./components/Events/EventsOptions.vue"
import EventsComposition from "./components/Events/EventsComposition.vue"
import BindingOptions from "./components/Binding/BindingOptions.vue"
import BindingComposition from "./components/Binding/BindingComposition.vue"
import PropsVariables from "./components/Props/PropsVariables.vue"
import PropsFunction from "./components/Props/PropsFunction.vue"
import EventEmit from "./components/Props/EventEmit.vue"
import StylesNotShared from "./components/StylesNotShared.vue"

//Hook que nos permite entre otras muchas cosas declarar variables con un comportaminto reactivo
import { ref } from "vue"


export default {
  name: 'App',
  components: {
    Variables,
    Loops,
    Conditionals,
    EventsOptions,
    EventsComposition,
    BindingOptions,
    BindingComposition,
    PropsVariables,
    PropsFunction,
    EventEmit,
    StylesNotShared,
  },
  setup() {
    //Declaramos la variable que vamos a enviar por props. En este caso app es el padre y el componente PropsVariables/Function los hijos ( que se encarga de renderizarlo )

    //Inicializamos el valor con ref para modificar su estado
    let powerCar = ref(120);

    //Declaramos la funcion que vamos a enviar por props con el aumento de la variable power con la funcion ref() para cambiar el estado accediendo a su valor
    const upPowerCar = () => {
      powerCar.value++
    }

    //Creamos la función para disminuir la potencia, la usaremos para el custom event:emit.
    //Al user el hook ref() accedemos al contenido con '.value'
    const downPowerCar = () => {
      powerCar.value--
    }

    //Exportamos funciones o variables
    return {
      powerCar,
      upPowerCar,
      downPowerCar,
    }
  }
};
</script>

<style>
h1{
  font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  color: #f8f8f8;
  text-shadow: 0px 3px 4px black;
  font-size: 4rem;
  text-align: center;
  border-bottom: 3px solid black;
  padding: 1rem 0 2.5rem 0;
  margin-top: 0;
}

</style>