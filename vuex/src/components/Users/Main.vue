<script>
import LkdButton from '../Button.vue'
export default {
  name: 'LkdUsers',
  components: {
    LkdButton
  },
  computed: {
    email () {
      return this.$store.state.user.email
    }
  }
}
</script>

<style lang="sass">
</style>

<template lang="html">
  <div>
    Email: {{email}}
    <lkd-button></lkd-button>
  </div>
</template>