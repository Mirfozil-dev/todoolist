<template>
  <div id="app">
    <form-component :query="query" @onInput="onInput" @onSave="addTask"/>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <button @click="deleteTask(index)">delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
import formComponent from './components/formComponent'

export default {
  name: 'App',
  components: {
    formComponent
  },
  data() {
    return {
      query: '',
      tasks: []
    }
  },
  methods: {
    onInput(query) {
      this.query = query
    },
    addTask() {
      this.tasks.push(this.query)
      this.query = ''
      console.log(this.tasks)
    },
    deleteTask(index) {
      this.tasks.splice(index, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
