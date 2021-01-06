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
          ref="titleInput"
        />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          placeholder="What does this resource gives?"
          rows="3"
          ref="descriptionInput"
        />
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input
          type="url"
          name="link"
          id="link"
          placeholder="Link"
          ref="linkInput"
        />
      </div>
      <base-button @click.prevent="addResource" type="submit">Add</base-button>
    </form>
  </base-card>
</template>

<script>
export default {
  methods: {
    addResource() {
      const resource = {
        id: new Date().toUTCString(),
        title: this.$refs.titleInput.value,
        description: this.$refs.descriptionInput.value,
        link: this.$refs.linkInput.value
      };
      console.log(resource.title)
      this.addNewResource(resource)
    }
  },
  inject:['addNewResource']
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
