<template>
  <div class="container">

    <div>
      <div v-if="$auth.loggedIn">
        <h1>Welcome {{$auth.user.name}}!</h1>
        <div>
          <button class="btn btn-warning" @click="logout()">Logout</button>
        </div>
      </div>
      <div v-if="!$auth.loggedIn">
        <nuxt-link to="/login">Login</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    async logout() {
      await this.$auth.logout()
      .then((response, context)=>{
        console.log(context)
      })
      .catch(error=>{
        alert(error)
      })
    }
  }
}
</script>

<style>
</style>
