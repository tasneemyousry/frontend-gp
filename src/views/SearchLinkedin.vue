<!-- src/views/Search.vue -->
<template>
    <div class="container">
      <h1 class="mt-4">
        <img src="../assets/img/linkedin.png" height="100px" width="100px">
        Linkedin
      </h1>
      <SearchFormLinkedin />
    </div>
  </template>
  
  <script>
  import SearchFormLinkedin from '../components/SearchFormLinkedin.vue';
  
  export default {
    name: 'SearchLinkedin',
    components: {
      SearchFormLinkedin,
    },
  };
  </script>
  
  <style scoped>
  .container {
    margin-top: 20px;
    background-color: white;
  }
  .mt-4 {
    text-align: center;
    color:#006292
  }
  </style>
  