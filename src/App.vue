<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'
const menuIsOpen = ref(false)
onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>

<template>
  <header>
    <button
    aria-controls="mainNav"
    aria-expanded="true"
    class="rounded-xl  bg-red-300 px-5 py-2 mx-2 my-5"
    @pointerdown="menuIsOpen = !menuIsOpen"
  >
    menu
  </button>
  <Transition
      class="transition-transform duration-1000"
      enter-from-class="-translate-x-full"
      enter-to-class="translate-x-0"
      leave-active-class="-translate-x-full"
    >
      <nav id="mainNav" v-show="menuIsOpen" class="bg-pink-50 w-14 mx-4">
        <ul>
          <li><a href="#">item 1</a></li>
          <li><a href="#">item 2</a></li>
          <li><a href="#">item 3</a></li>
        </ul>
      </nav>
    </Transition>
    <RouterLink to="/" class="mx-2">Accordéon</RouterLink>
    <RouterLink to="/boucle" class="mx-2">Boucle</RouterLink>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
