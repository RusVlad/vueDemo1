<template>
  <div class="hello">
    <h2 v-show="shouldShow">{{ message }}</h2>
    <input v-model="message" type="text">
    <br>
    <button class="btn" @click="shouldShow = !shouldShow">Toggle message</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    value: String
  },
  data() {
    return {
      shouldShow: true
    };
  },
  computed: {
    message: {
      get() {
        return this.value;
      },
      set(val) {
        this.$emit("input", val);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  max-width: 960px;
  margin: 0 auto;
  text-align: left;
}

h2 {
  word-break: break-word;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.btn {
  margin-top: 20px;
}
</style>
