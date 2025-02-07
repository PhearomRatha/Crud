<template>
    <div>
      <h2>Child Component</h2>
      <p>Name: {{ user.name }}</p>
      <p>Age: {{ user.age }}</p>
      {{  counterInject }}
    </div>
  </template>
  
  <script>
  export default {
    name: 'ChildComponent',
    inject: ['user',' counterInject'], 
  };
  </script>
  