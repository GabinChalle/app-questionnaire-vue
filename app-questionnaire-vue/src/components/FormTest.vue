<template>
    <div class="questionnaire">
      <h1>{{msg}}</h1>
      <p> {{ test[i].question }} </p>
      <div v-for="option in test[i].options" :key="option">
        <b-form-checkbox v-model="option.reponse_user" :value="true">
          {{option.intitule}}
        </b-form-checkbox>
      </div>
      <p> v-model : {{ test[0].options[0].reponse_user }} </p>
      <p> v-model : {{ test[0].options[1].reponse_user }} </p>
      <p> v-model : {{ test[0].options[2].reponse_user }} </p>
      <p> v-model : {{ test[1].options[0].reponse_user }} </p>
      <p> v-model : {{ test[1].options[1].reponse_user }} </p>
      <p> v-model : {{ test[1].options[2].reponse_user }} </p>
      <p> v-model : {{ test[2].options[0].reponse_user }} </p>
      <p> v-model : {{ test[2].options[1].reponse_user }} </p>
      <p> v-model : {{ test[2].options[2].reponse_user }} </p>
      <br/>
    </div>
</template>

<script>
import test from '../assets/questionnaire.json'
console.log(test)
export default {
  data () {
    return {
      test: test.test
    }
  },
  name: 'FormTest',
  props: {
    msg: String,
    i: Number
  },
  methods: {
    check: function () {
      console.log('BONJOUR')
    }
  }
}
</script>
