<template>
  <v-card class="mx-auto pa-4 mt-4" width="100%" max-width="500" dir="rtl">
    <div class="text-center mb-4">
      <span style="color: orangered"> ورود به حساب کاربری </span>
    </div>
      <v-text-field
        v-model="userName"
        :class="usernameValidation"
        class="mb-4"
        clearable
        label="نام کاربری یا شماره همراه"
        type="text"
        dir="ltr"
      ></v-text-field>
      <v-text-field
        v-model="psssword"
        class="mb-4"
        clearable
        label="رمز ورود"
        type="password"
        dir="ltr"
      ></v-text-field>
      <!-- :disabled="userName && password ? true : false" -->
      <v-btn
        color="success"
        size="large"
        @click="authentication"
      >
        ورود
      </v-btn>
  </v-card>

</template>




<script>
import { mapState, mapStores } from "pinia";
import { loginStore } from "@/stores";
// import { loginStore } from "@/stores/index";

export default {
    data (){
        return{
            userName : "",
            psssword : "",
            usernameValidFormat : false,
        }
    },
    computed:{
      //computed is a online searcher
        ...mapStores(loginStore),
        // ...mapState(loginStore, ["token"]),
        usernameValidation(){
          if (this.userName.length >= 8) {
            return "valid"
        } else {
            return "invalid"
        }
        }
    },
    mounted() {
     // this.authentication()
    },
    methods:{
      authentication() {
        console.log("Eetnene")
        if(this.userName.length > 0 && this.psssword.length > 0) {
                  console.log("Eetnene2")

          //If the backend response is 200
          const token = "tokenLogin-localStorage"
          this.loginStore.login(token)
          console.log("**********",this.loginStore.isAuthenticated);
        }
      }
    }
}
</script>
<style>
.valid{
    color: green
}
.invalid{
    color: red
}


</style>