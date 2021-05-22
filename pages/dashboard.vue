<template>
  <div>
    <h1>This is your dashboard!</h1>
    User: {{$auth.user.name}} <br>
    <button class="btn btn-warning" @click="logout()">Logout</button>
  </div>
</template>

<script>
export default {
  middleware: 'auth',
  methods: {
    logout() {
      this.$auth.logout()
    }
  }
}
</script>
