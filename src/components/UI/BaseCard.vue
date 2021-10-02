<template>
  <div>
    <slot></slot>
  </div>
</template>

<style scoped>
div {
    position: relative;
  min-width: 200px;
  border-radius: 0.5rem;
  padding: 1.5rem 1rem;
  margin: 0 1rem 1rem 1rem;
  border: 1px solid #eaeaea;
  background-color: #fff;
  z-index: 2;
}
.plus {
  position: relative;
  border-radius: .5rem .5rem 0 0;
  top: 2.9rem;
  padding: .5rem;
  margin: 1rem 1.75rem;
  height: 24px;
  z-index: 1;
}
</style>
