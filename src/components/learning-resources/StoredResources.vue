<template>
  <ul>
    <base-item
      v-for="resource in resources"
      :key="resource.id"
      :name="resource.name"
      :description="resource.description"
      :link="resource.link"
    ></base-item>
  </ul>
</template>

<script>
import BaseItem from './BaseResource.vue';
export default {
  components: {
    BaseItem
  },
  props: {
    resources: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
  ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
