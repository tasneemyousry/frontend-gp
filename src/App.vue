<template>
  <div id="app">
    <div class="d-flex">
      <nav class="border-right" id="sidebar-wrapper">
        <div class="sidebar-heading">Xtract</div>
        <div class="list-group mx-auto">
          <router-link class="list-group-item list-group-item-action" to="/">Services</router-link>
          <router-link class="list-group-item list-group-item-action" v-if="isAuthenticated"
            to="/history">History</router-link>
          <router-link class="list-group-item list-group-item-action" to="/about">About us</router-link>
        </div>
      </nav>
      <div id="page-content-wrapper" class="container-fluid">
        <div class="user">
          <div class="greeting">
            <h1>Welcome to Xtract</h1>
          </div>
          <div v-if="!isAuthenticated" class="user-btn">
            <router-link to="/login" class="user-btn-display btn-secondary">Login</router-link>
            <router-link to="/signup" class="user-btn-display btn-secondary">Sign Up</router-link>
          </div>
          <div v-else class="user-btn">
            <router-link to="/profile" class="user-btn-display btn-secondary">Profile</router-link>
            <button @click="logoutUser" class="logout-btn">Logout</button>
          </div>
        </div>
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex';

export default {
  name: 'App',
  computed: {
    ...mapState(['isAuthenticated']),
  },
  methods: {
    ...mapActions(['logout', 'setAuthenticated']),
    logoutUser() {
      this.logout(); // Call Vuex action to set isAuthenticated to false
      this.$router.push('/'); // Redirect to home page after logout
    },
  },
  created() {
    const token = localStorage.getItem('token');
    if (token) {
      this.setAuthenticated(true); 
    } else {
      this.setAuthenticated(false); 
    }
  },
};
</script>

<style>
.sidebar-heading {
  font-size: xx-large;
  text-align: center;
  margin-bottom: 5%;
  margin-top: 3%;
}

#sidebar-wrapper {
  background-image: linear-gradient(to bottom right, rgba(8, 60, 44, 0.7), rgba(8, 60, 44, 1));
  width: 250px;
  border-radius: 25px;
  position: fixed;
  margin-left: 1%;
  margin-top: 1%;
  left: 100;
  height: 96%;
  z-index: 1000;
}

#page-content-wrapper {
  margin-left: 260px;
  margin-top: 30px;
  width: calc(100% - 260px);
}

.list-group-item {
  background-color: #C5DBD0 !important;
  border-radius: 10px !important;
  margin-bottom: 6%;
  max-width: 80%;
  margin-left: auto;
  margin-right: auto;
  padding-left: 10px;
  padding-right: 10px;
  border: none !important;
}

.router-link-active {
  background-color: #083C2C !important;
  color: white !important;
}

.user {
  display: flex;
  justify-content: space-between;
  margin: auto;
  padding-bottom: 5%;
}

.greeting {
  max-width: 50%;
  text-align: center;
}

.user-btn {
  max-width: 50%;
  margin-right: 5%;
  margin-top: 1%;
  width: 200px;
  height: 35px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.user-btn-display,
.logout-btn {
  width: 100%;
  border-radius: 10px;
  border: 0;
  color: black;
  display: block;
  text-align: center;
  line-height: 35px;
}

.logout-btn {
  background-color: white;
  color: black;
  text-decoration: underline;
}
</style>
