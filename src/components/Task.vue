<template>
  <div>
    <h2>Lista</h2>
    <ul>
      <li v-for="(tarea, index) in tareas" :key="index">
        {{ index + 1 }}: {{ tarea }}
        <span> <button @click="$emit('eliminacion',index)">Eliminar</button> </span>
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: "Task",
  props: {
    tareas: [],
  },

}
</script>

<style>
li {
  padding-bottom: 10px;
}
</style>