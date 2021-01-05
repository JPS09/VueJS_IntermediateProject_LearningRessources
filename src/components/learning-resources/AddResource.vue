<template>
  <h2>Add a resource</h2>
  <form>
    <label for="name">Resource Title</label>
    <input type="text" name="name" placeholder="Enter the resource name" />
    <label for="description">Description</label>
    <input
      type="text"
      name="description"
      placeholder="What does this resource gives?"
    />
    <label for="link">Link</label>
    <input type="text" name="link" placeholder="Link" />
    <button @click.prevent></button>
  </form>
</template>
