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
        />
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input type="text" name="link" id="link" placeholder="Link" />
      </div>
      <button @click.prevent>Add</button>
    </form>
  </base-card>
</template>

<style scoped>
form {

}
</style>
