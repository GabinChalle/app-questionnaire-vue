<template>
  <div class="test">
    <img alt="Vue logo" src="../assets/logo.png">
    <FormTest msg="Welcome to the Test" :i=i />
    <input v-on:click="previous" type="submit" value="Précédent">
    <input v-on:click="next" type="submit" value="Suivant">
  </div>
</template>

<script>
// @ is an alias to /src
import FormTest from '@/components/FormTest.vue'

export default {
  name: 'test',
  data () {
    return {
      i: 0
    }
  },
  components: {
    FormTest
  },
  methods: {
    next: function () {
      this.i = this.i + 1
    },
    previous: function () {
      this.i = this.i - 1
    }
  }
}
</script>
