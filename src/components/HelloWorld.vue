<template>
  <div>
    <h1>{{ msg }}</h1>
    <h2>{{ count }}</h2>
  </div>
  <span v-bind:title="message">
    鼠标悬停几秒钟查看此处动态绑定的提示信息！
  </span>
  <input v-model="message" />
  <button v-on:click="reverseMessage">反转 Message</button>
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
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split("").reverse().join("");
    },
  },
};
</script>

<style scoped>
div {
  @apply p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4;
}
</style>
