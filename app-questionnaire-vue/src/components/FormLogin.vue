<template>
    <form @submit.prevent="false">
        <label for="firstname">Firstname : </label>
        <input type="text" name="firstname" v-model="firstname" placeholder="Enter your Firstname..." required>

        <label for="lastname">Lastname : </label>
        <input type="text" name="lastname" v-model="lastname" placeholder="Enter your Lastname..." required>

        <label for="society">Society : </label>
        <input type="text" name="society" v-model="society" placeholder="Enter the Society name..." required>

        <button type="submit" @click.stop.prevent="submit()"> Commencer le test </button>
    </form>
</template>

<script>
export default {
  name: 'FormLogin',
  data () {
    return {
      firstname: null,
      lastname: null,
      society: null
    }
  },
  methods: {
    submit () {
      this.$router.push('/test?firstname=' + this.firstname + '&lastname=' + this.lastname + '&society=' + this.society)
    }
  }
}
</script>
