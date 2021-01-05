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
      <nav>
        <a :href="link" target="_blank">Go to {{ name }}</a>
      </nav>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
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
