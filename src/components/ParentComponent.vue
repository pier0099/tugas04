<template>
    <div class="parent-container">
      <h2>Parent Component</h2>
      <child-component @childEvent="handleChildEvent">
        <template v-slot:default>
          <p>This is content from Parent Component</p>
        </template>
      </child-component>
      <p class="child-data">Data from child component: {{ childData }}</p>
    </div>
  </template>
  
  <script>
  import ChildComponent from './ChildComponent.vue';
  
  export default {
    name: 'ParentComponent',
    components: {
      ChildComponent
    },
    data() {
      return {
        childData: ''
      };
    },
    methods: {
      handleChildEvent(data) {
        this.childData = data;
      }
    }
  };
  </script>
  
  <style scoped>
  .parent-container {
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 10px;
    margin: 20px;
    background-color: #f9f9f9;
  }
  
  h2 {
    color: #2c3e50;
  }
  
  .child-data {
    margin-top: 10px;
    color: #555;
  }
  </style>
  