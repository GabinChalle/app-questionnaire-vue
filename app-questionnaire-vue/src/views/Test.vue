<template>
  <div class="test">
    <img alt="Vue logo" src="../assets/logo.png">
    <b-form>
      <FormTest msg="Questionnaire : " :i=i />
      <input v-on:click="previous" type="submit" value="Précédent">
      <input v-on:click="next" type="submit" value="Suivant" :hidden="fin" >
      <input v-on:click="onSubmit" type="submit" value="Terminer" :hidden="!fin" >
    </b-form>
  </div>
</template>

<script>
// @ is an alias to /src
import FormTest from '@/components/FormTest.vue'
import test from '@/assets/questionnaire.json'

export default {
  name: 'test',
  data () {
    return {
      i: 0,
      fin: false
    }
  },
  computed: {
    test () {
      return test.nbQuestions
    }
  },
  components: {
    FormTest
  },
  methods: {
    next: function () {
      if (this.i < test['nbQuestions'] - 1) {
        this.i = this.i + 1
      } else {
        this.fin = true
      }
    },
    previous: function () {
      if (this.i > 0) {
        this.i = this.i - 1
        this.fin = false
      } else {
        this.i = this.i
      }
    },
    onSubmit: function () {
      console.log('bonjour')
    }
  }
}
</script>
