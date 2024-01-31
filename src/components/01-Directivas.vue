<script setup>
    import { ref } from 'vue'

    const url = 'https://www.youtube.com'
    const mensaje = 'Hola'
    const paises = ['Argentina', 'Brasil', 'Colombia', 'Russia']
    const condicion = true
    const msg = ref('Mensaje predeterminado')
    const cambiarTexto = () => (msg.value = 'Texto cambiado')
</script>

<template>
  <div>
    <!-- v-bind: Sirve para crear atributos a un elemento el cual su valor sea algo proveniente de JS -->
    <a v-bind:href="url">Enlace</a>  <!-- Aca el valor de href hace referencia a la variable url -->

    <!-- v-model: Sirve para relacionar el valor de la constante mensaje con el valor del input -->
    <input type="text" v-model="mensaje" />  <!-- El valor del input va a ser Hola y a medida que se escribe el valor del input y de la constante cambian -->

    <!-- v-for: Sirve para iterar arrays u objetos (Es como un .map) -->
    <li v-for="pais in paises" :key="pais">{{ pais }}</li>  <!-- Se crea un li por cada elemento del array -->

    <!-- v-if, v-else: Sirve para mostrar el elemento dependiendo si la condicion es true o false -->
    <p v-if="condicion">Condicion true</p>  <!-- Si 'condicion' es true se muestra -->
    <p v-else>Condicion false</p>  <!-- Si 'condicion' es false se muestra -->

    <!-- v-show: Sirve para mostrar el elemento solo si la condicion es true, si no no muestra nada -->
    <p v-show="condicion">Mensaje con renderizado condicional</p>

    <!-- Eventos: Forma de poner eventos -->
    <button @click="cambiarTexto">Cambiar texto</button>
    <p>{{ msg }}</p>

    
  </div>
</template>



<style scoped></style>
