<template>
  <div>
    <p>User detail:</p>
    <p>UUUUUUUU</p>
    <p>User name: {{ myName }}</p>
    <p>Eman: {{ reverseName() }}</p>
    <p>Age : {{ userAge }} </p>
    <button @click="resetName">Reset name</button>
    <button @click="resetFn()">Reset name Fn</button>
  </div>
</template>

<script>
  import { eventBus } from '../../main';

  export default {
    props: {
      myName: {
        type: String,
        default: 'GGGGGGGG'
      },
      resetFn: Function,
      userAge: Number
    },
    methods: {
      reverseName() {
        return this.myName.split('').reverse().join('');
      },
      resetName() {
        this.myName = 'Ololololol';
        this.$emit('nameWasReset', this.myName);
      }
    },
    created() {
      eventBus.$on('changedAge', age => this.userAge = age)
    }
  }
</script>

<style scoped>
  div {
    height: 100%;
    background: green;
    color: white;
  }
</style>
