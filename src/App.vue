<template>
  <div id="app">
    <h1>TODO APP</h1>
    <div class="container">
      <app-new @emitList="createdList"></app-new>
      <app-todo-grid :list="list" @emitDelete="deleted"></app-todo-grid>
    </div>
    
  </div>
</template>

<script>
import New from './components/New.vue'
import TodoGrid from './components/TodoGrid.vue'

export default {
  name: 'App',
  data() {
    return {
      list: []
    }
  },
  methods: {
    // newList coming from New.vue (not need to do anything, its auto since we used $emit)
    createdList(newList) {
      this.list.push(newList)
    },
    deleted(j) {
      this.list.splice(j, 1)
    }
  },
  components: {
    appNew: New,
    appTodoGrid: TodoGrid
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
