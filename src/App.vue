<template>
  <the-header title="Good places to learn"></the-header>
  <the-resources></the-resources>
</template>

<script>
import TheResources from './components/learning-resources/TheResources';
export default {
  components: {
    TheResources
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
  },
  provide() {
    return {
      resources: this.storedResources
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
