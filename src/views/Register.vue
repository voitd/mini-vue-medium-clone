<template>
  <div class="auth-page">
    <div class="container page">
      <div class="row">
        <div class="col-md-6 offset-md-3 col-xs-12">
          <h1 class="text-xs-center">Sign up</h1>
          <p class="text-xs-center">
            <router-link :to="{ name: 'login' }">Need an account?</router-link>
          </p>
          VALIDATIONS ERROR
          <form @submit.prevent="onSubmit">
            <fieldset class="form-group">
              <input class="form-control" type="text" placeholder="Username" />
            </fieldset>
            <fieldset class="form-group">
              <input class="form-control" type="text" placeholder="Email" />
            </fieldset>
            <fieldset class="form-group">
              <input
                class="form-control"
                type="password"
                placeholder="Password"
              />
            </fieldset>
            <button class="btn btn-lg pull-xs-right" :disabled="isSubmitting">
              Sign Up
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'McvRegister',
  computed: {
    isSubmitting() {
      return this.$store.state.auth.isSubmitting
    },
  },
  methods: {
    onSubmit() {
      console.log('submited!')
      this.$store.dispatch('register')
    },
  },
}
</script>
