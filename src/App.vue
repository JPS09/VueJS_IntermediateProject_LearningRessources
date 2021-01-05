<template>
  <the-header title='Good places to learn'></the-header>
  <stored-resources :resources="storedResources"> </stored-resources>
</template>

<script>
import StoredResources from './components/learning-resources/StoredResources.vue';
export default {
  components: {
    StoredResources
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

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
