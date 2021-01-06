<template>
  <base-card>
    <base-button
      @click="tabSelect('stored-resources')"
      :mode="storedButtonHighlight"
      >Stored Resources</base-button
    >
    <base-button @click="tabSelect('add-resource')" :mode="addButtonHighlight"
      >Create a Resource</base-button
    >
    <keep-alive>
      <component :is="selectedTab"></component>
    </keep-alive>
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
      selectedTab: 'stored-resources',
      storedResources: [
        {
          id: 'google',
          title: 'Google',
          description: 'Google is the main research engine of the planet',
          link: 'https://www.google.com'
        },
        {
          id: 'vue-style-guide',
          title: 'Vue Style Guide',
          description:
            'Informations to keep your VueJS code as beautiful as possible',
          link: 'https://v3.vuejs.org/style-guide/'
        }
      ]
    };
  },
  provide() {
    return {
      resources: this.storedResources,
      addNewResource: this.addAResource
    };
  },
  methods: {
    tabSelect(tab) {
      this.selectedTab = tab;
    },
    addAResource(resource) {
      console.log(resource);
      this.storedResources.unshift(resource);
      this.selectedTab = 'stored-resources';
    }
  },
  computed: {
    storedButtonHighlight() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },

    addButtonHighlight() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    }
  }
};
</script>
