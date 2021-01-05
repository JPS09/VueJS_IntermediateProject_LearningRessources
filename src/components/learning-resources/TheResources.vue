<template>
  <base-card>
    <base-button @click="tabSelect('stored-resources')" :mode='storedButtonHighlight'
      >Stored Resources</base-button
    >
    <base-button @click="tabSelect('add-resource')" :mode='addButtonHighlight'
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
  },
  computed:{
    storedButtonHighlight(){
      return this.selectedTab === 'stored-resources' ? null : 'flat'
    },

    addButtonHighlight(){
      return this.selectedTab === 'add-resource' ? null : 'flat'
    }
  }
};
</script>
