<template>
  <base-item
    v-for="resource in storedResources"
    :key="resource.id"
    :name="resource.name"
    :description="resource.description"
    :link="resource.link"
  ></base-item>
</template>

<script>
import BaseItem from './components/base-components/BaseItem.vue';
export default {
  components: {
    BaseItem
  },
  data() {
    return {
      storedResources: [
        {
          id: 'google',
          name: 'Google',
          description: 'Google is the main research engine of the planet',
          link: 'https://www.google.com'
        },
        {
          id: 'vue-style-guide',
          name: 'Vue Style Guide',
          description:
            'Informations to keep your VueJS code as beautiful as possible',
          link: 'https://v3.vuejs.org/style-guide/'
        }
      ]
    };
  }
};
</script>
