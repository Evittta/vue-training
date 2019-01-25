<template>
  <div>
    <h3>New quote</h3>
    <slot></slot>
    <button @click="counter++">Increase</button>
    <p>{{ counter }}</p>
  </div>
</template>

<script>
  export default {
    data: function() {
      return {
        counter: 0
      }
    },
    destroyed() {
      console.log('Destryed');
    },
    deactivated() {
      console.log('deactivated');
    },
    activated() {
      console.log('activated');
    }
  }
</script>

<style scoped></style>
