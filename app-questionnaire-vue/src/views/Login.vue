<template>
  <div class="login">
    <img alt="Vue logo" src="../assets/logo.png">
    <FormLogin msg="Welcome to Your App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import FormLogin from '@/components/FormLogin.vue'

export default {
  name: 'login',
  components: {
    FormLogin
  }
}
</script>
