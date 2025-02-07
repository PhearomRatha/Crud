<template>
    <div>
      <h2>Child Component</h2>
      <p>{{ message }}</p>
      <p>{{ shareedData}}</p>
      <p>{{counter}}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ChildComponent',
    inject: ['shareedData','message','counter'] 
  };
  </script>
  

  