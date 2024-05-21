<template>
    <div class="child-container">
      <h3>Child Component</h3>
      <grandchild-component @grandchildEvent="handleGrandchildEvent">
        <template v-slot:default>
          <p>This is content from Child Component</p>
        </template>
      </grandchild-component>
    </div>
  </template>
  
  <script>
  import GrandchildComponent from './GrandchildComponent.vue';
  
  export default {
    name: 'ChildComponent',
    components: {
      GrandchildComponent
    },
    methods: {
      handleGrandchildEvent(data) {
        this.$emit('childEvent', data);
      }
    }
  };
  </script>
  
  <style scoped>
  .child-container {
    padding: 15px;
    border: 1px solid #ccc;
    border-radius: 10px;
    margin: 20px;
    background-color: #eef;
  }
  
  h3 {
    color: #2c3e50;
  }
  </style>
  