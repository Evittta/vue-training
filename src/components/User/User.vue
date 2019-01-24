<template>
  <div>
    <p>I'm awesome User component</p>
    <p>User name: {{ name }}</p>
    <p>User age: {{ age }}</p>
    <button @click="changeName">Change name</button>
    <div class="details">
      <app-user-detail
        :myName="name"
        @nameWasReset="name = $event"
        :resetFn="resetName"
        :userAge="age"
        >
      </app-user-detail>
      <app-user-edit
        :userAge="age"
      ></app-user-edit>
    </div>
  </div>
</template>

<script>
import UserDetail from './UserDetail'
import UserEdit from './UserEdit'
  export default {
    data: function() {
      return {
        name: 'Evita',
        age: 22,
      }
    },
    methods: {
      changeName() {
        this.name = 'Vita';
      },
      resetName() {
        this.name ='Evita';
      }
    },
    components: {
      appUserDetail: UserDetail,
      appUserEdit: UserEdit
    }
  }
</script>

<style scoped>
  div {
    height: 300px;
    width: 100%;
  }
  .details {
    display: flex;
  }
</style>

