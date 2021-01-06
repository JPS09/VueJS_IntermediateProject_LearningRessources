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
      <base-button @click.prevent="checkInput" type="submit">Add</base-button>
    </form>
  </base-card>
  <base-dialog v-if="isInputInvalid" title="Invalid Input" @close="closeError">
    <template #message>
      <p v-if="isTitleEmpty">Please enter a title</p>
      <p v-else-if="isDescriptionEmpty">Please enter a description</p>
      <p v-else-if="isLinkEmpty">Please enter a link</p>
    </template>
    <template #action>
      <base-button @click="closeError">Understood</base-button>
    </template>
  </base-dialog>
</template>

<script>
export default {
  data() {
    return {
      isInputInvalid: false,
      isTitleEmpty: false,
      isDescriptionEmpty: false,
      isLinkEmpty: false
    };
  },
  methods: {
    checkInput() {
      if (this.$refs.titleInput.value.trim() === '') {
        this.isInputInvalid = true;
        this.isTitleEmpty = true;
      } else if (this.$refs.descriptionInput.value.trim() === '') {
        this.isInputInvalid = true;
        this.isDescriptionEmpty = true;
      } else if (this.$refs.linkInput.value.trim() === '') {
        this.isInputInvalid = true;
        this.isLinkEmpty = true;
      } else {
        this.addResource();
      }
    },
    addResource() {
      const resource = {
        id: new Date().toUTCString(),
        title: this.$refs.titleInput.value,
        description: this.$refs.descriptionInput.value,
        link: this.$refs.linkInput.value
      };
      console.log('oh');
      this.cleanInput();
      this.addNewResource(resource);
    },
    closeError() {
      (this.isInputInvalid = false),
        (this.isTitleEmpty = false),
        (this.isDescriptionEmpty = false),
        (this.isLinkEmpty = false);
    },
    cleanInput() {
      this.$refs.titleInput.value = '';
      this.$refs.descriptionInput.value = '';
      this.$refs.linkInput.value = '';
    }
  },
  inject: ['addNewResource']
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
