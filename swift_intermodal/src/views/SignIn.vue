<template>
  
  <div class="signIn_Container">
    <v-container class="vContainer">
    <h3>Please enter the credentials</h3>
    <v-alert dense outlined type="error" v-if="false">
      {{ errorMsg }}
    </v-alert>
    <v-form ref="form"  lazy-validation>
      <v-text-field v-model="userName" label="Username" required></v-text-field>
      <v-text-field v-model="password" type="password" label="password" required></v-text-field>
      <v-btn color="warning" @click="onSubmit">
        Login
      </v-btn>
    </v-form>
  </v-container>
  </div>

</template>  
<script  lang="ts">
import { defineComponent } from 'vue';
export default defineComponent ({
  name: 'SignIn',
  components: {
  },
  data() {
    return {
      userName: '',
      password: '',
      errorMsg: '',
      alertShow: false,
    }
  },
  methods: {
    onSubmit(e:any) {
      e.preventDefault()
      if (!this.userName && !this.password) {
        this.errorMsg = "Please enter username and password"
        this.alertShow = true
        return
      }
      if (!this.userName) {
        this.errorMsg = "Please enter username"
        this.alertShow = true
        return
      }
      if (!this.password) {
        this.errorMsg = "Please enter password"
        this.alertShow = true
        return
      }
      this.$router.push({
        path: '/',
        query: { uname: this.userName }
      });
    }
  },
})
</script>
    
<style>
.signIn_Container {
  padding-top: 150px !important;
  width:75% !important;
}
.vContainer{
  width:50% !important;
}
</style>
    