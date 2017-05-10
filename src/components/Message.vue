<template>
  <div>
    <h1>{{ message }}</h1>
    <app-input :msg="message" @messageChange="message = $event"></app-input>
    <p>Message ID {{ $route.params.messageId }}</p>
    <button @click="goHome">Go Home</button>
  </div>

</template>


<script>
import Input from './Input'
export default {
  watch: {
    '$route' (to, from) {
      alert(to.params.messageId)
    }
  },
  created () {
    alert(this.$route.params.messageId)
  },
  data () {
    return {
      message: 'This is a great Message'

    }
  },
  components: {
    'app-input': Input
  },
  methods: {
    goHome () {
      this.$router.push('/')
    }
  }
}
</script>


<style>

</style>
