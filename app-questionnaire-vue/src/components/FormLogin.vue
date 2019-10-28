<template>
    <form @submit.prevent="false">
        <label for="firstname">Firstname : </label>
        <input type="text" name="firstname" v-model="gcuserFirstname" placeholder="Enter your Firstname..." required>

        <label for="lastname">Lastname : </label>
        <input type="text" name="lastname" v-model="gcuserLastname" placeholder="Enter your Lastname..." required>

        <label for="society">Society : </label>
        <input type="text" name="society" v-model="gcsocietyName" placeholder="Enter the Society name..." required>

        <button type="submit" @click.stop.prevent="login()"> Commencer le test </button>
    </form>
</template>

<script>
import PouchDB from 'pouchdb'
var db = new PouchDB('gc_user') // créer la bdd
db.replicate.to('http://localhost:5984/gc_user') // relie la bdd
export default {
  name: 'FormLogin',
  data () {
    return {
      gcuserLastname: '',
      gcuserFirstname: '',
      gcsocietyName: ''
    }
  },
  methods: {
    login () {
      if (
        this.gcuserFirstname !== '' &&
        this.gcuserLastname !== '' &&
        this.gcsocietyName !== ''
      ) {
        var vm = this
        var user = { // creer un obj user
          _id: Math.random().toString(36).substr(2, 9),
          firstname: vm.gcuserFirstname,
          lastName: vm.gcuserLastname,
          socityName: vm.gcsocietyName
        }
        db.put(user).then(function (doc) { // ajout l'user dans la bdd
          console.log(doc)// retourne le doc avec ce qu'on a inserer dans la bdd
          vm.$router.push(
            '/test?gcuserFirstname=' +
            vm.gcuserFirstname +
            '&gcuserLastname=' +
            vm.gcuserLastname +
            '&gcsocietyName=' +
            vm.gcsocietyName
          )
          db.replicate.to('http://localhost:5984/gc_user') //   actualise
        })
      } else {
        console.log('Please put your first/last name and your society name.')
      }
    }
  }
}
</script>
