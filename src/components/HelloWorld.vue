<template>
  <div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
div {
  @apply p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4;
}
</style>
