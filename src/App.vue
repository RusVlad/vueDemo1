<template>
  <div id="app">
    <div class="container">
      <img alt="Vue logo" class="logo" src="./assets/logo.png">
      <h1>Welcome to your Vue app</h1>
      <HelloWorld v-model="welcomeMsg" />
      <div class="components">
        <Counter />
        <Todo />
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Counter from './components/Counter.vue'
import Todo from './components/Todo.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Counter,
    Todo
  },
  data() {
    return {
      welcomeMsg: "V-model example. Write something here..."
    };
  }
}
</script>

<style>
@import "./assets/css/main.css";

.components {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
}

.logo {
  max-height: 100px;
}
</style>
