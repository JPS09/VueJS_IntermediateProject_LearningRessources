<template>
  <base-card>
    <base-button @click="tabSelect('stored-resources')"
      >Stored Resources</base-button
    >
    <base-button @click="tabSelect('add-resource')"
      >Create a Resource</base-button
    >
    <component :is="selectedTab"></component>
  </base-card>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
  components: {
    StoredResources,
    AddResource
  },
  data() {
    return {
      selectedTab: 'stored-resources'
    };
  },
  methods: {
    tabSelect(tab) {
      this.selectedTab = tab;
    }
  }
};
</script>
