<template>
    <div>
        {{ mensaje }}
    </div>
</template>

<script setup>
    const {mensaje} = defineProps(['mensaje'])
</script>