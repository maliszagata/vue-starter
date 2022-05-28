<template>
  <div>
    <div> Witaj {{userNameToDisplay}} </div>
    <button @click="logOut()">Wyloguj</button>
    </div>
</template>

<script>
export default {
  props: ['email'],

  data() {
    return {
    }
  },

  computed: {
    userNameToDisplay() {
      return this.email || 'Nieznany użytkownik';
    }
  },

  methods: {
    logOut() {
      this.$emit('logout');
    },

  }
}
</script>