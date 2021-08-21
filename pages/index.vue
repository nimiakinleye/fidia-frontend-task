<template>
  <div id="login-page">
    <div class="flex flex-col h-full items-center justify-center">
      <div class="">
        <div><img src="~assets/logo.svg" alt="" /></div>
        <div class="form_group">
          <div>
            <h3 class="text-xl text-gray-500 font-semibold">
              Sign in to your account
            </h3>
          </div>
          <div>
            <form autocomplete="off" @submit.prevent="toDashboard" class="form" action="">
              <div class="input">
                <label for="">Email</label>
                <input type="text" placeholder="jane.doe@gmail.com" />
              </div>
              <div class="input">
                <label for="password" class="flex justify-between items-center"
                  >Password<span class="text-sm text-indigo-500"
                    >Forgot your password?</span
                  ></label
                >
                <div class="password_input">
                  <input :type="passwordType"/>
                  <svg
                  @click="togglePassword"
                    width="16"
                    height="17"
                    viewBox="0 0 16 17"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M8 14.968C3.582 14.968 0 10.282 0 8.96802C0 7.65402 3.582 2.96802 8 2.96802C12.418 2.96802 16 7.65402 16 8.96802C16 10.282 12.418 14.968 8 14.968ZM8 12.968C9.06087 12.968 10.0783 12.5466 10.8284 11.7964C11.5786 11.0463 12 10.0289 12 8.96802C12 7.90715 11.5786 6.88974 10.8284 6.13959C10.0783 5.38944 9.06087 4.96802 8 4.96802C6.93913 4.96802 5.92172 5.38944 5.17157 6.13959C4.42143 6.88974 4 7.90715 4 8.96802C4 10.0289 4.42143 11.0463 5.17157 11.7964C5.92172 12.5466 6.93913 12.968 8 12.968ZM8 10.968C7.46957 10.968 6.96086 10.7573 6.58579 10.3822C6.21071 10.0072 6 9.49845 6 8.96802C6 8.43758 6.21071 7.92888 6.58579 7.5538C6.96086 7.17873 7.46957 6.96802 8 6.96802C8.53043 6.96802 9.03914 7.17873 9.41421 7.5538C9.78929 7.92888 10 8.43758 10 8.96802C10 9.49845 9.78929 10.0072 9.41421 10.3822C9.03914 10.7573 8.53043 10.968 8 10.968Z"
                      fill="#A3ACB9"
                    />
                  </svg>
                </div>
              </div>
              <div class="checkbox">
                <input type="checkbox" />
                <label for="">Stay signed in for a week</label>
              </div>
              <button class="continue_button">Continue</button>
            </form>
            <div>
              <p class="text-indigo-500 text-center my-4">
                Use single sign-on (SSO) instead
              </p>
            </div>
          </div>
        </div>
        <div class="">
          <div class="mt-4 mb-2">
            <p>
              Don't have an account?
              <nuxt-link class="text-indigo-500" to="/">Sign up</nuxt-link>
            </p>
          </div>
          <div class="login_nav">
            <p>
              © Stripe<nuxt-link to="/">Contact</nuxt-link
              ><nuxt-link to="/">Privacy and Terms</nuxt-link>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      passwordType: 'password'
    }
  },
  methods: {
    toDashboard() {
      this.$router.push('/dashboard')
    },
    togglePassword () {
      if(this.passwordType === 'password') {
        this.passwordType = 'text'
      }
      else if (this.passwordType === 'text') {
        this.passwordType = 'password'
      }
    }
  },
}
</script>

<style>
html {
  @apply text-sm;
  box-sizing: border-box;
}
</style>
<style scoped>
#login-page {
  background-image: url('~assets/stripe_background.svg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  height: 100vh;
}

.form_group {
  @apply p-8
  shadow-xl
  rounded-md
  bg-white;
}

.form {
  @apply max-w-full
  md:w-80;
}

.input {
  @apply flex
  flex-col
  my-4;
}

.input input:focus,
.input input:active {
  outline: none;
}

label {
  @apply text-sm;
}

input {
  @apply 
  my-1
  w-full;
}

.password_input, .input > input {
  @apply border-2
  border-gray-300
  px-3
  rounded-md;
}

.input > input {
  @apply p-3 
}

.input .password_input input {
  @apply border-0
  py-2
}

.password_input {
  @apply flex
  items-center
}

.checkbox {
  @apply flex
  items-center
  my-4;
}

input[type='checkbox'] {
  @apply w-4
  mr-2;
}

.continue_button {
  @apply w-full
  bg-indigo-500
  text-white
  p-1
  py-3
  rounded-md;
}

.login_nav {
  @apply font-semibold
  text-gray-500
  flex
  divide-x
  divide-gray-500;
}

.login_nav a {
  @apply ml-2;
}
</style>
