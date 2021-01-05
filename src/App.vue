<template>
  <base-item
    v-for="ressource in storedRessources"
    :key="ressource.id"
    :name="ressource.name"
    :id="ressource.id"
    :description="ressource.description"
    :link="ressource.link"
  ></base-item>
</template>

<script>
import BaseItem from './components/BaseItem.vue';
export default {
  components: {
    BaseItem
  },
  data() {
    return {
      storedRessources: [
        {
          id: 'google',
          name: 'Google',
          description: 'Google is the main research engine of the planet',
          link: 'www.google.com'
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
