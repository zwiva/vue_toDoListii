<template>
  <div id="app">
    <div class="input_main">
      <h1 style="text-align:center;">Crea una nueva tarea</h1>
      <label>Tarea </label>
      <input
        type="text"
        placeholder="Ingresa una nueva tarea"
        v-model="newTask"
      />
      <button @click="addTask">Crear</button>
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
    tasks: ["pagar el netflix (texto de prueba)", "ir al super (texto de prueba)"],
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
.input_main, .input_list {
  background-color: white;
  min-width: 60%;
  border-radius: 3rem;
  padding: 2rem;
  margin: 2rem; 
}
</style>
