<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="!isLoggedIn">
      <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
      <login-form @login="logIn($event)" button-label="Wleć"></login-form>
      <login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
      <login-form @login="logIn($event)"  button-label=""></login-form>
    </div>
    <div v-else="isLoggedIn"> Witaj {{isLoggedIn}}
      <button @click="logOut()">Wyloguj</button>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},

  data() {
    return {
      isLoggedIn: false
    };
  },

  methods: {
    logIn(email) {
      this.isLoggedIn = email
    },

    logOut() {
      this.isLoggedIn = false
    }
  }

}
</script>

<style>

</style>
