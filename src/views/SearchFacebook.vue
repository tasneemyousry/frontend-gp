<template>
    <header>
      <img src="E:\college\level_4\Grad_Project\VUE_FRONT\src\assets\img\facebook.png" alt="Facebook" class="logo"/>
      <h1>Facebook </h1>
      
    </header>
    <fbSearchForm />
</template>
  
<script>
import fbSearchForm from '../components/fbSearchForm.vue';

export default {
    name: 'SearchFacebook',
    components: {
        fbSearchForm,
    }
  };
</script>
  
<style scoped>
  header {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px 0;
    background-color: #4267b2;
    color: white;
  }
  
  .logo {
    height: 40px;
    margin-right: 20px;
  }
</style>