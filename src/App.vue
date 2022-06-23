<template>
  <div class="container">
    <div>
      <h2>Crea una nueva tarea</h2>
      <span>Tarea </span>
      <input type="text" v-model="task" @keyup.enter="addTask" placeholder="Ingrese una nueva tarea">
      <button @click="addTask">Crear</button>
      <Task :tareas= "tareas" @eliminacion="eliminar" />
    </div>
  </div>
</template>

<script>

import Task from "@/components/Task";

export default {
  name: 'App',
  components: {Task},
  data() {
    return {
      task: '',
      tareas: []
    }
  },
  methods: {
    addTask() {
      if (this.task !== '') {
        this.tareas.push(this.task)
        this.task = ''
      }
    },
    eliminar(index) {
      console.log(index)
      this.tareas.splice(index, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}

.container {
  display: flex;
  justify-content: center;
}

span {
  font-weight: bold;
}

button {
  margin-left: 5px;
}

li {
  margin-left: 30%;
  text-align: justify;
}

</style>
