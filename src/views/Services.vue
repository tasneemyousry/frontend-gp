<!-- src/views/Services.vue -->
<template>
  <div class="container">
    <div class="services">
      <div class="search-twitter">
        <router-link to="/searchTwitter" custom v-slot="{ navigate }">
          <button class="search-twitter-display" @click="navigate">
            Twitter Search
            <img src="../assets/img/twitter.png">
          </button>
        </router-link>
      </div>
      <div class="search-facebook">
        <button class="search-facebook-display">Facebook Search</button>
      </div>
      <div class="search-profile">
        <router-link to="/searchProfile" custom v-slot="{ navigate }">
          <button class="search-profile-display" @click="navigate">
            Cross platform profile search
          </button>
        </router-link>
      </div>
      <div class="search-linkedin">
        <router-link to="/searchLinkedin" custom v-slot="{ navigate }">
          <button class="search-linkedin-display" @click="navigate">
            Linkedin Search
            <img src="../assets/img/linkedin.png">
          </button>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Services',
};
</script>

<style scoped>
.container {
  margin-top: 20px;
}
.services {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 20px;
  padding: 20px;
}
.search-twitter,
.search-facebook,
.search-profile {
  display:flex;
  height:100px;
}
.search-twitter-display {
  display:flex;
  align-items:center;
  width:80%;
  border-radius: 10px;
  border: 0;
  background-image: radial-gradient(#000000 0%, #111010, #3c4441 100%);
  color: white;
  text-align: left;
  padding-left:20px;
  font-size: 20px;
  cursor: pointer;
}
.search-twitter-display img {
    margin-left: 80px; 
    width: 50px;
    height: 50px;
}
.search-facebook-display {
  width:80%;
  border-radius: 10px;
  border: 0;
}

.search-profile-display {
  width:80%;
  border-radius: 10px;
  border: 0;
}

.search-linkedin-display {
  display:flex;
  align-items:center;
  width:80%;
  border-radius: 10px;
  border: 0;
  background-image: radial-gradient( #0077B5, #00A0DC 100%);
  color: white;
  text-align: left;
  padding-left:20px;
  font-size: 20px;
  cursor: pointer;
  height: 100px
}
.search-linkedin-display img {
    margin-left: 80px; 
    width: 50px;
    height: 50px;
}
</style>
