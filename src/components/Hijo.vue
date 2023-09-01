<template>
    <div>
        <h1>Hijo:</h1>
        <h2>Te llamas {{ nombre }} y tienes {{ edad }} años.</h2>
        <button @click="enviar">Cambiar Valores</button>
        <button @click="restaurar">Restaurar Valores</button>
    </div>
</template>

<script setup>
import { defineProps, ref } from 'vue';

const nombre = ref('');
const edad = ref(0);
const nombreOriginal = ref('');
const edadOriginal = ref(0);

const { nombre: nombreProp, edad: edadProp } = defineProps(['nombre', 'edad']);

nombre.value = nombreProp;
edad.value = edadProp;

const enviar = () => {
    nombreOriginal.value = nombre.value;
    edadOriginal.value = edad.value;
    nombre.value = 'Vue';
    edad.value = 9;
};

const restaurar = () => {
    if (nombreOriginal.value !== '' && edadOriginal.value !== 0) {
        nombre.value = nombreOriginal.value;
        edad.value = edadOriginal.value;
    }
};
</script>

<style scoped></style>
