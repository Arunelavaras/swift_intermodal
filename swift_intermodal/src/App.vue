<script lang="ts">
import Sidebar from '@/components/sidebar/Sidebar.vue'
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import { sidebarWidth } from '@/components/sidebar/state.js'
import SignIn from '@/views/SignIn.vue'
import { defineComponent } from 'vue';
export default defineComponent ({
  components: {Sidebar, Header,Footer,SignIn},
  setup() {
    return { sidebarWidth }
  },
  data(){
    return{
      currentRoutePath:this.$router.currentRoute,
      routePath:this.$route.path
    }
  }
})
</script>
<template>
  <Header/>
  <Footer/>
  <SignIn v-if="['logout'].indexOf(currentRoutePath.path)>0"/>
  <Sidebar v-if="routePath !== '/logout'"/>
  <!-- <Sidebar v-if="loggedIn"/>   -->
  <div :style="{ 'margin-left': sidebarWidth }">
    <router-view  />
  </div>
</template>
<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
