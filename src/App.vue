<template>
  <div>
    <h1>Padre:</h1>
    <HijoVue :nombre="nombre" :edad="edad" @modificar="cambiarValor" />
    <HijoVue2 />
    <button @click="mostrarApp2">Mostrar/ocultar App2</button>
    <App2 v-if="mostrarComponenteApp2" />
  </div>
</template>

<script setup>
import { provide, ref } from "vue";
import HijoVue from "./components/Hijo.vue";
import HijoVue2 from "./components/Hijo2.vue";
import App2 from "./components/App2.vue";

const cambiarValor = (valor1, valor2) => {
  nombre.value = valor1;
  edad.value = valor2;
};
const nombre = ref('Jab');
const edad = ref(18);
const canal = ref("soyjab");
provide('miCanal', canal);

const mostrarComponenteApp2 = ref(false);

const mostrarApp2 = () => {
  mostrarComponenteApp2.value = !mostrarComponenteApp2.value;
};
</script>

<style scoped></style>
