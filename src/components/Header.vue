<template>
    <header class="header" role="banner">
        <div v-if="routerPath=== '/logout'"  class="logo">
            <img src="../assets/images/static_swift.svg" alt="" width="150" />
        </div>
        <span v-if="routerPath !== '/logout'" class="uNameHeader">Pradeesh Balachandran</span>
        <div class="avatar" v-if="routerPath !== '/logout'">
            <Nav/>
        </div>
       
<!--     
        <v-dropdown id="dropdown" class="avatar">
            <v-avatar>
      <img
        src="https://cdn.vuetifyjs.com/images/john.jpg"
        alt="John" 
      /> </v-avatar>
            <template #dropdown>
                <v-dropdown-menu>
                    <v-dropdown-item v-on:click="loginPopup">Profile</v-dropdown-item>
                    <v-dropdown-item v-on:click="logout">Logout</v-dropdown-item>
                </v-dropdown-menu>
            </template>
        </v-dropdown> -->
       
       
    </header>
</template>

<script lang="ts">
import Nav from './Nav.vue'
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'HeaderNew',
    data(){
        return{
            routerPath:this.$route.path
        }
    },
    components:{
        Nav
    }
})
</script>
<style scoped>
.header {
    position: fixed;
    height: 60px;
    top: 0;
    width: 100%;
    background: white;
    border-bottom: 3px solid #ffcc00;
    font-family: "Open Sans Condensed", Helvetica, Arial, sans-serif;
    font-weight: 700;
    text-transform: uppercase;

}

.logo{
    float:left;
    margin:5px;
}

.avatar {
    float: right;
    /* margin: 18px;
    right: 20px; */
}
.uNameHeader{
    float: right;
    position: fixed;
    right: 130px;
    top:20px;
    font-family:Avenir,Helventica, Arial, Sans-serif ;
    color: #18468D;
    font-size: 16px;
    text-transform: none;
}

</style>
