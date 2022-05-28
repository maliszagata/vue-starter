<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="!authenticatedUsername">
      <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
      <login-form @login="logIn($event)" button-label="Wleć"></login-form>
      <login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
      <login-form @login="logIn($event)" ></login-form>
    </div>
    <div v-if="authenticatedUsername">
      <welcome-screen @logout="logOut($event)" :email="authenticatedUsername"></welcome-screen>
    </div>
    </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import WelcomeScreen from "./AuthPage";

export default {
  components: {WelcomeScreen, LoginForm},

  data() {
    return {
      authenticatedUsername: false
    };
  },

  methods: {
    logIn(email) {
      this.authenticatedUsername = email
    },

    logOut() {
      this.authenticatedUsername = false
    }
  }

}
</script>

<style>

</style>
