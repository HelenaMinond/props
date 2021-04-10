<template>
  <div>
    <h2>Lista</h2>
    <section v-if="arrLista && arrLista.length == 0">
      <p>Lista de tareas</p>
    </section>
    <section>
      <ul>
        <li v-for="nuevaTareaLista in arrLista" :key="nuevaTareaLista">
          {{ nuevaTareaLista.tarea }}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "Tareas",
  props: {
    arrLista: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style></style>
