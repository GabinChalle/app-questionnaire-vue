<template>
  <div class="admin">
    <img alt="Vue logo" src="../assets/logo.png">
    <FormAdmin/>
  </div>
</template>

<script>
// @ is an alias to /src
import FormAdmin from '@/components/FormAdmin.vue'

export default {
  name: 'admin',
  components: {
    FormAdmin
  }
}
</script>
