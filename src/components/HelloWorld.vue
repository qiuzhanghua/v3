<template>
  <div>
    <h1>{{ msg }}</h1>
    <h2>{{ count }}</h2>
  </div>
  <span v-once>
    {{ message }}
  </span>
  <br />
  <label for="message">请输入:</label>
  <input id="message" v-model="message" />
  <br />
  <button @click="reverseMessage">反转 Message</button>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
      message: "You loaded this page on " + new Date().toLocaleString(),
    };
  },
  mounted() {
    setInterval(() => {
      this.count++;
    }, 1000);
    console.log("mounted!");
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split("").reverse().join("");
    },
  },
  created() {
    console.log("created!");
  },
  unmounted() {
    console.log("unmounted!");
  },
  beforeUpdate() {
    console.log("beforeUpdate!");
  },
};
</script>

<style scoped>
div {
  @apply p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4;
}
</style>
