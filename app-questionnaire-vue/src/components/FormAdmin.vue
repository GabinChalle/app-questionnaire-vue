<template>
    <div class="admin">
        <form method="POST" @submit.prevent="false">
            <label for="pwd">Entrer votre mot de passe : </label>
            <input type="password" v-model="pwd" name="pwd">
            <button type="submit" @click.stop.prevent="submit()"> Access to </button>
        </form>
    </div>
</template>

<script>
export default {
  name: 'FormAdmin',
  data () {
    return {
      pwd: null
    }
  },
  methods: {
    submit () {
      this.$router.push('/about?pwd=' + this.pwd)
    }
  }
}
</script>
