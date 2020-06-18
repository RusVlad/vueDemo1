<template>
  <div>
    <h2>Counter</h2>
    <div class="counter">
      <p class="counter-number">{{ counter }}</p>
      <button class="btn" @click="increment">Increment</button>
      <button class="btn" @click="reset">Reset</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    msg: String
  },
  data() {
    return {
      counter: 0
    };
  },
  methods: {
    increment() {
      this.counter++;
    },
    reset() {
      this.counter = 0;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.counter {
  background-color: lightgray;
  padding: 10px;
  max-width: 480px;
  width: 100%;
  margin: 20px auto;
}

.counter-number {
  font-size: 24px;
}

.btn {
  margin: 0 10px;
}
</style>
