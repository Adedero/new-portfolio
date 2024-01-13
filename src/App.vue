<script setup>
import { ref } from "vue";
import { RouterView } from 'vue-router';
import AppHeader from '@/components/AppHeader.vue'
import NavBar from "./components/NavBar.vue";

let isOpen = ref(false)

</script>

<template>
  <main class="h-full w-full relative bg-[var(--light)] dark:bg-[var(--dark)] text-[var(--text)] dark:text-[var(--light)] z-[1]">

    <AppHeader @open-nav="isOpen = !isOpen" />

    <div class="md:hidden">
      <NavBar :isOpen ="isOpen" @close-nav="isOpen = false"/>
    </div>

    <section class="h-full overflow-y-scroll"> 
      <RouterView />
    </section>
  </main>
</template>

<style scoped>
main::before {
  @apply hidden dark:md:block content-[""] absolute w-40 h-40 rounded-full bg-blue-500 top-32 left-20 opacity-20 filter blur-[60px] 
}

main:after {
  @apply hidden dark:md:block content-[""] absolute w-40 h-40 rounded-full -z-10 bg-red-500 bottom-32 right-20 opacity-20 filter blur-[60px] 
}

</style>
