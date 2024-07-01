<!-- src/views/Search.vue -->
<template>
  <div class="container">
    <h1 class="mt-4">
      <img src="../assets/img/twitter.png" height="100px" width="100px">
      Twitter
    </h1>
    <SearchForm />
  </div>
</template>

<script>
import SearchForm from '../components/SearchForm.vue';

export default {
  name: 'SearchTwitter',
  components: {
    SearchForm,
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
}
</style>
