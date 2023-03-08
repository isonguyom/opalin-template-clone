<script setup>
import { RouterView } from 'vue-router'
import { reactive} from 'vue'
import Navbar from './components/Navbar.vue';
import Login from './views/Login.vue';
import Signup from './views/Signup.vue';

const state = reactive({ loginIsActive: false, signupIsActive: false })
const body = document.body
function toggleLoginModal() {
  state.loginIsActive = !state.loginIsActive
  body.classList.toggle('modal_active')
}

function toggleSignupModal() {
  state.signupIsActive = !state.signupIsActive
  body.classList.toggle('modal_active')
}

</script>

<template>
  <header>

    <Navbar @open-login="toggleLoginModal" @open-signup="toggleSignupModal" :color="$route.meta.color"></Navbar>
  </header>

  <Login :isActive="state.loginIsActive" @close-modal="toggleLoginModal"></Login>
  <Signup :isActive="state.signupIsActive" @close-modal="toggleSignupModal"></Signup>
  <RouterView />
</template>

<style>
body.modal_active {
  height: 100vh;
  overflow: hidden;
}
</style>
