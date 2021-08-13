<template>
  <div id="app">
    <div class="input_main" style="text-align: center">
      <h2>Crea una nueva tarea</h2>
      <section class="input_section">
        <label>Tarea </label>
        <input
          type="text"
          placeholder="Ingresa una nueva tarea"
          v-model="newTask"
        />
        <button @click="addTask">Agregar</button>
      </section>
    </div>

    <div class="input_list">
      <h2>Lista</h2>
      <ul>
        <li v-for="(task, index) of tasks" :key="index">
          {{ task }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

// const addTask = () => {
//   tasks.push(newTask)
// }

export default {
  name: "App",
  data: () => ({
    tasks: [
      "pagar el netflix (texto de prueba)",
      "ir al super (texto de prueba)",
    ],
    newTask: "",
  }),
  methods: {
    addTask() {
      this.tasks.push(this.newTask);
      this.newTask = "";
    },
  },
};
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.input_main,
.input_list {
  background-color: white;
  width: 70%;
  max-width: 400px;
  border-radius: 3rem;
  padding: 2rem;
  margin: 1.5rem;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);
}
.input_section {
  padding-bottom: 1rem;
}
button {
  background-color: dodgerblue;
  padding: 0.75rem;
  margin: 0.5rem;
  border-radius: 0.5rem;
  border: none;
  color: white;
  font-weight: 600;
  background-image: linear-gradient(to top,  rgb(151, 198, 245) 0%,rgb(9, 112, 216) 100%);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);
}
button:hover {
  background-image: linear-gradient(to right, rgb(9, 112, 216) 0%, rgb(151, 198, 245) 100%);
  background-position: right center;
}
.input_list li {
  list-style-type: disclosure-closed;
}
</style>
