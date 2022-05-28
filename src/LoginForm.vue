<template>
  <div>
    <label>Zaloguj się e-mailem</label>
    <input type="email" v-model="email" @keyup.enter = "enter()">
    <button @click="enter()">{{ buttonLabel }}</button>
  </div>
</template>

<script>
export default {
  props: ['buttonLabel'],

  data() {
    return {
      email: '',
    }
  },

  mounted() {
    if (!this.buttonLabel) {
      this.buttonLabel = 'Zaloguj się';
    }
  },



  methods: {
    enter() {
      this.$emit('login', this.email);
    },

  }
}
</script>