<template>
    <a @click="toggleMenu" class="circle">
        <img class="user-pic" src="@/assets/images/user.jpg" alt="user-pic">
    </a>
    <!-- <img src="@/assets/images/user.jpg" class="user-pic" @click="toggleMenu"> -->
    <div class="sub-menu-wrap" id="subMenu">
        <div class="sub-menu">
            <!-- <div class="user-info">
                <img src="@/assets/images/user.png">
                <h3>Pradeesh</h3>
            </div>
            <hr> -->
            <a class="sub-menu-link">
                <img src="@/assets/images/profile.png">
                <p>Edit Profile</p>
            </a>
            <a class="sub-menu-link">
                <img src="@/assets/images/setting.png">
                <p>Settings</p>
            </a>
            <a class="sub-menu-link" @click="signinClick">
                <img src="@/assets/images/help.png">
                <p>Sign In</p>
            </a>
            <a class="sub-menu-link" @click="signoutClick">
                <img src="@/assets/images/logout.png">
                <p>Sign Out</p>
            </a>
        </div>
    </div>
</template>

<script setup lang="ts">
 import { useMsal } from '../ad-auth-api/useMsal';
 import { loginRequest } from "../authConfig";
import { defineComponent } from 'vue';

 const { instance } = useMsal();

 function toggleMenu() {
            let subMenu: any = document.getElementById("subMenu");
            subMenu.classList.toggle("open-menu");
        }
      function  signinClick(){
              instance.loginPopup(loginRequest);
        }
      function  signoutClick() {
            // this.$router.push('/signin')
            instance.logoutPopup({                
                mainWindowRedirectUri: "/logout"                
             });
        }

// export default defineComponent({
//     name: 'NavPage',
//     methods: {
//         toggleMenu() {
//             let subMenu: any = document.getElementById("subMenu");
//             subMenu.classList.toggle("open-menu");
//         },
//         signinClick(){
//             //  instance.loginPopup(loginRequest);
//         },
//         signoutClick() {
//             // this.$router.push('/signin')
//             // instance.logoutPopup({
//             //     mainWindowRedirectUri: "/"
//             // });
//         }
//     }
// })
 </script>

 
<style scoped>
.user-pic {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    /* margin-left: 30px;
    margin-top: 3px; */
}

.sub-menu-wrap {
    /* position: absolute; */
    top: 100%;
    right: 10%;
    width: 180px;
    max-height: 0px;
    overflow: hidden;
    transition: max-height 0.5s;
    background: #F5F5F5;
    border-radius: 25px;
    margin-right: 3px;
    z-index: -1;
}

.sub-menu-wrap.open-menu {
    max-height: 300px;
}

.sub-menu {
    background: #fff;
    /* padding: 20px; */
    margin: 10px;
    text-align: left !important;
    text-transform: none !important;
    font-weight: 200 !important;
    cursor: pointer;
    background: #F5F5F5;
}

.sub-menu hr {
    border: 0;
    height: 1px;
    width: 100%;
    background: #ccc;
    margin: 15px 0 10px;
}

.user-info {
    display: flex;
    align-items: center;
}

.user-info h3 {
    font-weight: 500;
}

.user-info img {
    width: 60px;
    border-radius: 50%;
    margin-right: 15px;
}

.sub-menu-link {
    display: flex;
    align-items: center;
    text-decoration: none;
    color: #525252;
    margin: 12px 0;
}

.sub-menu-link p {
    width: 100%;
}

.sub-menu-link:hover p {
    font-weight: 600;
}

.sub-menu-link img {
    width: 40px;
    background: #e5e5e5;
    border-radius: 50%;
    padding: 8px;
    margin-right: 15px;
}

.sub-menu-link span {
    font-size: 22px;
    transition: transform 0.5s;
}

.sub-menu-link:hover span {
    transform: translateX(5px);
}

::-moz-selection {
    background: rgba(0, 0, 0, 0.1);
}

::selection {
    background: rgba(0, 0, 0, 0.1);
}

a {
    color: RoyalBlue;
    font-weight: normal;
    text-decoration: none;
}

a:hover {
    color: CornflowerBlue;
}

/* Circle Avatar Styles */

.circle {
    line-height: 0;
    /* remove line-height */
    display: inline-block;
    /* circle wraps image */
    /* margin: 5px; */
    border: 4px solid rgba(200, 200, 200, 0.4);
    border-radius: 50%;
    /* relative value */
    /*box-shadow: 0px 0px 5px rgba(0,0,0,0.4);*/
    transition: linear 0.25s;
    height: 58px;
    width: 58px;
}

.circle img {
    border-radius: 50%;
}

.circle:hover {
    transition: ease-out 0.2s;
    border: 4px solid rgba(0, 0, 0, 0.2);
    -webkit-transition: ease-out 0.2s;
}

a.circle {
    color: transparent;
}

/* IE fix: removes blue border */
</style>