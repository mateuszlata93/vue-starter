<template>
  <div>
    <label>{{ buttonLabel }}</label>
    <input type="email" v-model="email">
    <button @click="enter()">Zaloguj się</button>
    <p v-if="isEmailValid == false">Wpisales pusty email</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      isHidden: false,
      isEmailValid: true
    }
  },
  methods: {
    enter() {
    if (this.email == '') {
      this.isEmailValid = false;
    } else {
      this.$emit('login', this.email);
    }
    }
  },
  props: {
    buttonLabel: String, // rodzic może ustawić stan hungry dziecka na true lub false
  }

}
</script>
