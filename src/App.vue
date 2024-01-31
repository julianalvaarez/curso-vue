<script setup>
  import Props from '@/components/02-Props.vue'
  import Directivas from '@/components/01-Directivas.vue'
  import LyfeCycle from '@/components/03-Lyfe-Cycle.vue'

  const props = 'Hola enviado por props'
</script>

<template>
  <Directivas />
  <Props :mensaje="props" />
  <LyfeCycle />
</template>

<style scoped></style>
