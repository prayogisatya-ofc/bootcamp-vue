<script>
import { RouterLink } from 'vue-router'

export default {
  data() {
    return {
      form : {
        email: '',
        password: ''
      }
    }
  },
};
</script>

<template>
  <main>
    <div class="relative overflow-hidden bg-white">
      <div class="mx-auto max-w-7xl">
        <div
          class="flex flex-col items-center w-full min-h-screen pt-6 sm:justify-center sm:pt-0"
        >
          <div class="w-full p-5 mx-auto sm:max-w-md">
            <h2 class="mb-20 text-5xl font-bold text-center">Welcome Back</h2>
            <form>
              <div class="mb-4">
                <label class="block mb-1" for="email">Email Address</label>
                <input
                  v-model="form.email"
                  placeholder="Type your email"
                  id="email"
                  type="text"
                  name="email"
                  class="block w-full py-3 mt-2 border border-gray-300 rounded-full shadow-sm px-7 focus:border-indigo-300 focus:outline-none focus:ring focus:ring-indigo-200 focus:ring-opacity-50 disabled:bg-gray-100"
                />
              </div>
              <div class="mb-4">
                <label class="block mb-1" for="password">Password</label>
                <input
                  v-model="form.password"
                  placeholder="Type your password"
                  id="password"
                  type="password"
                  name="password"
                  class="block w-full py-3 mt-2 border border-gray-300 rounded-full shadow-sm px-7 focus:border-indigo-300 focus:outline-none focus:ring focus:ring-indigo-200 focus:ring-opacity-50 disabled:bg-gray-100"
                />
              </div>
              <div class="mt-6">
                <button
                  type="button"
                  class="inline-flex items-center justify-center w-full px-8 py-3 text-base font-medium text-white bg-indigo-600 border border-transparent rounded-full hover:bg-indigo-700 md:py-2 md:text-lg md:px-10 hover:shadow"
                >
                  Sign In
                </button>
                <RouterLink
                  to="/register"
                  class="inline-flex items-center justify-center w-full px-8 py-3 mt-2 text-base font-medium text-black bg-gray-200 border border-transparent rounded-full hover:bg-gray-300 md:py-2 md:text-lg md:px-10 hover:shadow"
                >
                  Create New Account
                </RouterLink>
              </div>
            </form>
          </div>
          <div class="w-full mx-auto mt-20 sm:max-w-2xl">
            <img src="@/assets/img/brand-logo.svg" alt="" class="w-full px-10 md:px-0" />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
