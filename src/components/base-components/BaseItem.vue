<template>
  <ul>
    <li>
      <div>
        <header>
          <h3>{{ name }}</h3>
          <button>Delete</button>
        </header>
      </div>
      <p>{{ description }}</p>
      <a :href="link" target="_blank">{{ link }}</a>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    }
  }
};
</script>
