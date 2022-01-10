<template>
  <div class="b-container">
    <div class="b-card">
      <div class="b-text">
        <div class="b-content">
          <h2 class="b-content__title">Encapsular estilos Vue.js 3</h2>
        </div>
        <h2>CSS y SCSS - No comparti estilos entre componentes</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'StylesNotShared',
};
</script>

<style scoped>
/* Añadir a la etiqueta style la palabra reservada "scoped" para no compartir estilos y clase ya utilizados. Tambien pueden reuserse y modificarlo segun nuestra necesidad */
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
  background-color: #416e588e;
  border: 5px solid ;
  box-shadow: 0px 0px 30px 3px rgba(0, 0, 0, 0.589);
  border-radius: 6rem;
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
  color: white;
  font-size: 1.5rem;
}

.b-content{
  border: none;
  border-bottom: 3px solid black;
}
</style>