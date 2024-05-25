<template>
  <section>
    <slot></slot>
  </section>
</template>

<script>
export default {
  name: 'BaseSection'
};
</script>

<style scoped>
section {
  padding: 2rem;
  background-color: #fff;
}
</style>
