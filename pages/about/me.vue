<template>
  <div class="w-full rounded shadow-sm bg-white p-20">
    <div>
      Component: <code class="inline-block rounded p-1 bg-gray-200">about/me.vue</code>
    </div>
    <div class="mt-8">
      This child route has no transitions defined. Therefore, it should not be transitionned
    </div>
    <div class="-mx-4 mt-12 flex items-center">
      <nuxt-link class="rounded bg-blue-500 text-white hover:bg-blue-400 mx-4 p-4" to="/">
        Go to index
      </nuxt-link>

      <nuxt-link class="rounded bg-blue-500 text-white hover:bg-blue-400 mx-4 p-4" to="/about">
        Go to about/index
      </nuxt-link>
    </div>
  </div>
</template>

<script>
  import { gsap } from 'gsap'

  export default {
    transition:{
      enter (el, done) {
        console.warn('entering about/me.vue page')
        gsap.timeline({ onComplete: done, defaults: { ease: 'back.inOut(3)', duration: 0.5 } })
          .from(el, {
            position: 'absolute',
            y: 20,
            autoAlpha: 0,
            scale: 1.03,
            transformOrigin: 'top center'
          })
          .set(el, { clearProps: true })
      },
      leave (el, done) {
        console.warn('leaving about/me.vue page')
        gsap.timeline({ onComplete: done, defaults: { ease: 'back.inOut(3)', duration: 0.5 } })
          .to(el, {
            position: 'absolute',
            y: -20,
            autoAlpha: 0,
            scale: 0.97,
            transformOrigin: 'top center'
          })
          .set(el, { clearProps: true })
      },
      css: false,
      mode: 'out-in'
    }
  }
</script>

<style>
.test-enter-active {
  transition: all 1s ease-in-out;
}

.test-enter {
  opacity: 0;
  transform: translateY(10px);
}

.test-leave-active {
  transition: all 1s ease-in-out;
}

.test-leave-to {
  opacity: 0;
  transform: translateY(10px);
}
</style>
