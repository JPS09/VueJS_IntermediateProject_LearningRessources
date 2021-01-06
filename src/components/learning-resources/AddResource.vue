<template>
  <h2>Add a resource</h2>
  <base-card>
    <form>
      <div class="form-control">
        <label for="title">Resource Title</label>
        <input
          type="text"
          id="title"
          name="title"
          placeholder="Enter the resource name"
        />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          type="text"
          id="description"
          name="description"
          placeholder="What does this resource gives?"
          rows="3"
        />
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input type="url" name="link" id="link" placeholder="Link" />
      </div>
      <base-button @click.prevent type="submit">Add</base-button>
    </form>
  </base-card>
</template>

<script>
export default {
  data() {
    return {
      titleInput: '',
      descriptionInput: '',
      linkInput: ''
    };
  },
  methods: {
    addResource() {
      const resource = {
        id: new Date().toUTCString(),
        title: this.titleInput,
        description: this.descriptionInput,
        link: this.linkInput
      };
      this.$emit('add-resource', resource);
    }
  }
};
</script>
<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
