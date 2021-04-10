<template>
  <div>
    <h1>Tareas a realizar</h1>
    <section>
      <label>Tarea</label>
      <input v-model="nuevaTarea" type="text" placeholder="Ingresa nueva tarea" size="15" maxlength="40"/>
      <button @click="AgregarTarea()">Añade</button>
    </section>

    <Tareas :arrLista="tareas" />
  </div>
</template>

<script>
import Tareas from "./components/Tareas.vue";

export default {
  name: "App",
  data() {
    return {
      tareas: [
        { tarea: "Pagar internet" },
        { tarea: "Comprar pan" },
        { tarea: "Pagar Netflix" },
      ],
      nuevaTarea: "",
    };
  },
  methods: {
    AgregarTarea() {
      if (this.nuevaTarea === "") return;
      this.tareas.push({ tarea: this.nuevaTarea });
      this.nuevaTarea = "";
    },
  },
  components: {
    Tareas,
  },
};
</script>

<style lang="scss">
div {
  font-family: "Roboto", sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1,
h2 {
  color: gray;
  margin-top: 2rem;
}

label,
li {
  font-weight: 500;
}

label {
  font-size: large;
}

input,
button {
  margin-left: 0.5rem;
}

button {
  background-color: white;
  border: solid 1px gray;
  border-radius: 5px;
}
</style>
