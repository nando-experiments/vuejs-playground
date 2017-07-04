<script>
import LkdUsers from './components/Users/Main.vue'
import { mapState, mapActions } from 'vuex'
export default {
  name: 'app',
  mounted () {
    const payload = {
      name: 'Fernando Moreira',
      email: 'nandomoreira.me@gmail.com',
      level: 'admin'
    }
    setTimeout(() => this.changeUser(payload), 3000)
  },
  methods: {
    ...mapActions(['changeUser'])
  },
  components: {
    LkdUsers
  },
  computed: {
    ...mapState({
      user: state => {
        const { name, email } = state.user
        return `O usuário logado é ${name} <${email}>`
      }
    })
  }
}
</script>

<style lang="sass">
html
  box-sizing: border-box

*, *::before, *::after
  margin: 0
  padding: 0
  box-sizing: inherit

html, body
  font-family: Arial, Helvetica, sans-serif

body
  padding: 3rem 1rem
</style>

<template lang="html">
  <div>
    <h1>Hello Vuex</h1>
    <p>{{user}}</p>
    <lkd-users></lkd-users>
  </div>
</template>
