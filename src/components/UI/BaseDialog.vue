<template>
  <div>
    <dialog open>
      <h2>Missing Information</h2>
      <slot name="error">An input is empty</slot>
      <slot name="button">OK</slot>
    </dialog>
  </div>
</template>

<style scoped>
dialog{
  position:fixed;
  margin: auto;
  top: 50vh;
  left: 0%;
  width: 25vw;
  height: max-content;
}
</style>
