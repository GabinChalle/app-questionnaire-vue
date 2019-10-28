<template>
    <div class="questionnaire">
      <h1>{{msg}}</h1>
      <form>
        <p v-if="test[i] !== null"> {{ test[i]["question"] }} </p>
        <input type="checkbox" name="option"> {{ test[i]["option1"] }}
        <input type="checkbox" name="option"> {{ test[i]["option2"] }}
        <input type="checkbox" name="option"> {{ test[i]["option3"] }}
        <br/>
      </form>
    </div>
</template>

<script>
import test from '../assets/questionnaire.json'
console.log(test)
export default {
  name: 'FormTest',
  computed: {
    test () {
      return test.test.map((item) => {
        return item
      })
    }
  },
  props: {
    msg: String,
    i: Number
  }
}
</script>
