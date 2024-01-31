<script setup>
    import {ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted} from 'vue'
    
    const mensaje = ref('Mensaje Inicial')
    const mensajeExtra = ref('Mensaje despues de montar el componente')
    const mostrarMensaje = ref(true)
    function actualizarComponente() {
        mensaje.value = 'Mensaje actualizado'
        mostrarMensaje.value = !mostrarMensaje.value
    }
    function desmontarComponente() {
        mostrarMensaje.value = false
    }

    // Se ejecuta antes de que se monte el componente
    onBeforeMount(() => {
        console.log('Componente antes de montarse')
    })

    // Se ejecuta cuando se monte el componente
    onMounted(() => {
        console.log('Componente montado')
    })


    // Se ejecuta antes de actualizar el componente
    onBeforeUpdate(() => {
        console.log('Componente antes de actualizarse')
    })

    // Se ejecuta cuando se actualiza el componente
    onUpdated(() => {
        console.log('Componente actualizado')
    })

    // Se ejecuta antes de desmontarse el componente
    onBeforeUnmount(() => {
        console.log('Componente antes de desmontarse')
    })

    // Se ejecuta cuando se desmonta el componente
    onUnmounted(() => {
        console.log('Componente desmontado')
    })

</script>


<template>
    <div>
        <p>{{ mensaje }}</p>
        <p v-if="mostrarMensaje">{{ mensajeExtra }}</p>
        <button @click="actualizarComponente">Actualizar Componente</button>
        <button @click="desmontarComponente">Desmontar Componente</button>
    </div>
</template>


<style lang="scss" scoped>

</style>