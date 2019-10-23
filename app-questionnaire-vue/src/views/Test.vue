<template>
  <div class="test">
    <img alt="Vue logo" src="../assets/logo.png">
    <FormTest msg="Welcome to the Test"/>
  </div>
</template>

<script>
// @ is an alias to /src
import FormTest from '@/components/FormTest.vue'

export default {
  name: 'test',
  components: {
    FormTest
  }
}
</script>
