<template>
  <div class="my-app">
    <h1>Hello  {{email}} !</h1>
    <!-- <label>Login with email</label>
     <input type="email" v-model="email">
     <div>This is your email length: {{email.length}}</div>
     <div v-if="email.length < 10">Your address is too short!</div>
     <div v-if="!email.includes('@')">Your address does not contain @</div>
     <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
     <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
     <button @click="alertMyEmail()">Display my email address in alert</button>-->
<!--
    <LoginForm v-if="email.length == 0" @login="(username) => logMeIn(username)" buttonLabel="to jest label"></LoginForm>
-->

    <LoginForm v-if="email.length == 0" @login="(username) => logMeIn(username)" button-label="Wejdź"></LoginForm>
    <LoginForm v-if="email.length == 0" @login="(username) => logMeIn(username)" button-label="Wleć"></LoginForm>
    <LoginForm v-if="email.length == 0" @login="(username) => logMeIn(username)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></LoginForm>

    <p v-if="this.email.length > 0"> Zalogowany jako {{email}}</p>
    <button v-if="email.length > 0" @click="logMeOut()">Wyloguj</button>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn(username) {
      this.email = username;
    },
    logMeOut(){
      this.email = '';
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
