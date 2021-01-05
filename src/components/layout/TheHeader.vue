<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    }
  }
};
</script>

<style scoped>
header {
  background-color: rgb(179, 119, 10);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
