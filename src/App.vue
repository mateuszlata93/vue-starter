<template>
  <div class="my-app">
    <h1>Hello  {{email}}$!</h1>
    <label>Login with email</label>
    <input type="email" v-model="email">
    <div v-if="email.length < 10">This is your email length: {{email.length}}</div>
    <div v-if="email.length < 10">Your address is too short!</div>
    <div v-if="!email.includes('@')">Your address does not contain @</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <button @click="alertMyEmail()">Display my email address in alert</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: 'test',
      password: 'test'
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    }
  }
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
