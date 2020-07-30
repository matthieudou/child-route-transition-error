<template>
  <div class="w-full rounded shadow-sm bg-white p-20">
    <div>
      Component: <code class="inline-block rounded p-1 bg-gray-200">index/me.vue</code>
    </div>
    <div class="mt-8">
      This child route has no transitions defined. Therefore, it should not be transitionned
    </div>

    <div class="-mx-4 mt-12 flex items-center">
      <nuxt-link class="rounded bg-blue-500 text-white hover:bg-blue-400 mx-4 p-4" to="/">
        Go to index
      </nuxt-link>

      <nuxt-link class="rounded bg-blue-500 text-white hover:bg-blue-400 mx-4 p-4" to="/about">
        Go to about
      </nuxt-link>
    </div>
  </div>
</template>

<script>
  export default {

  }
</script>
