<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="logIn === false ">Zaloguj się e-mailem
      <input type="text" v-model="email" @keyup.enter="enter()"></div>
    <div v-else-if="logIn === true "> Witaj {{email}}</div>
    <button @click="enter()">Wchodzę</button>
    <button @click="logOut()">Wyloguj</button>
  </div>
</template>

<script>
import "milligram";


export default {
  data() {
    return {
      email: '',
      logIn: false
    };
  },

  methods: {
    enter() {
      this.logIn = true
    },

    logOut() {
      this.logIn = false
      this.email = ''
    }
  }

}
</script>

<style>

</style>
