<script>
import { mapActions } from 'vuex'
export default {
  name: 'LkdButton',
  methods: {
    changeUserData () {
      const payload = {
        name: 'Outro usuário',
        email: 'outro.usuario@gmail.com',
        level: 'user'
      }
      this.changeUser(payload)
    },
    ...mapActions(['changeUser'])
  },
  computed: {
    hasUser () {
      return this.$store.state.user.name !== ''
    }
  }
}
</script>

<style lang="sass" scoped>
button
  border: 1px solid #333
  cursor: pointer
  background-color: #fff
  color: #333
  padding: 15px
  margin: 15px 0
</style>

<template lang="html">
  <div>
    <button :disabled="!hasUser" @click="changeUserData">Mudar dados do usuário</button>
  </div>
</template>
