<template>
  <ul></ul>
</template>

<script>
export default {
  data() {
    return {
      storedRessources: [
        {
          id:'google',
          name: 'Google',
          description: 'Google is the main research engine of the planet',
          link: 'www.google.com'
        },
        {
          id:'vue-style-guide',
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
