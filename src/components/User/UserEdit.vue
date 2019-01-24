<template>
  <div>
    <p>User edit</p>
    <p>User age: {{ userAge }} </p>
    <button @click="editAge">Edit age</button>
  </div>
</template>

<script>
  import { eventBus } from '../../main.js';

  export default {
    props: ['userAge'],
    methods: {
      editAge() {
        this.userAge = 21;
        // this.$emit('changedAge', this.userAge);
        // eventBus.$emit('changedAge', this.userAge);
        eventBus.changeAge(this.userAge);
      }
    }
  }
</script>

<style scoped>
  div {
    height: 100%;
    background: red;
    color: white;
  }
</style>

