<template>
  <div class="container">
    <div class="row">
      <div class="col-md-4 offset-md-4 mt-5">
        <div class="card">
          <div class="card-header">
            <h5>User Login</h5>
          </div>
          <div class="card-body">
            <form action="#" @submit.prevent="login()">
                <div class="form-group">
                  <input type="email" v-model="credentials.email" class="form-control" placeholder="Email">
                </div>
                <div class="form-group">
                  <input type="password" v-model="credentials.password" class="form-control" placeholder="Password">
                </div>
                <div class="from-group">
                  <button class="btn btn-primary" type="submit">
                    Login
                  </button>
                </div>
            </form>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      credentials: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    async login() {
      await this.$auth.loginWith('laravelSanctum',{
        data: this.credentials
      })
      .then((response, context) => {
        console.log(context)
      })
      .catch(error=>{
        alert(error)
      })
    }
  }
}
</script>
