<template>
    <section>
      <slot></slot>
    </section>
  </template>
  
  <script>
  export default {
    name: 'Section'
  };
  </script>
  
  <style scoped>
  section {
    padding: 2rem;
    background-color: #fff;
  }
  </style>
  