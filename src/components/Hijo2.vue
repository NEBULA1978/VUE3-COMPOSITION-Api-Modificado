<template>
    <div>
        <h1>Hijo2:</h1>
        <h2>{{ canal }}</h2>
        <button @click="modificar">Cambiar</button>
        <button @click="restaurar">Restaurar Nombre</button>
    </div>
</template>

<script setup>
import { inject } from 'vue';

const canal = inject('miCanal');
let nombreAnterior = null;

const modificar = () => {
    // Solo almacenar el valor anterior si aún no se ha almacenado
    if (nombreAnterior === null) {
        nombreAnterior = canal.value;
        canal.value = 'html6';
    }
};

const restaurar = () => {
    if (nombreAnterior !== null) {
        canal.value = nombreAnterior;
        nombreAnterior = null; // Restablecer el valor anterior
    }
};
</script>

<style scoped></style>
