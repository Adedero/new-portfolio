<script setup>
import { ref, onMounted } from "vue";
import { RouterView } from "vue-router";
import Console from '@/components/Console.vue';
import NavBar from "./components/NavBar.vue";
import DarkModeButton from '@/components/DarkModeButton.vue';
import SocialIcons from "./components/SocialIcons.vue";

const console = ref(null)
const main = ref(null)
let isOpen = ref(false)
let overlayOpen = ref(false)

function skip() {
  console.value.remove()
} 

onMounted(() => {
    setTimeout(() => {
      main.value.scrollIntoView({ behavior: 'smooth' })
    }, 12000);

    setTimeout(skip, 13000);

    window.addEventListener('resize', function(){
      if (window.innerHeight >= 1024) isOpen.value = true;
      else isOpen.value = false, overlayOpen.value = false;
    })
})
</script>

<template>
<main class="flex flex-col gap-6 lg:p-2  lg:overflow-y-scroll">
    <section ref="console" class="bg-[#2F3544] font-[Akurrat]">
      <Console @on-skip="skip" />
    </section>

    <section ref="main" id="main" class="lg:flex">
      <NavBar :isOpen="isOpen" @close="isOpen = false, overlayOpen=false" @nav-link-click="isOpen = false, overlayOpen = false" />

      <div id="overlay" :style="overlayOpen? 'opacity:1; z-index:10;': ''" class="fixed w-[100dvw] h-[100dvh] opacity-0 -z-10" @click="isOpen=false, overlayOpen=false"></div>

      <div class="bg-[#efefef] dark:bg-slate-800 h-full lg:z-80 lg:shadow-lg lg:shadow-gray-900 grow">
        <header class="text-gray-700 dark:text-white p-5 flex items-center justify-between">
          <span class="material-symbols-rounded font-bold cursor-pointer select-none lg:hidden" @click="isOpen=true, overlayOpen=true">menu</span>
          
          <div class="flex items-center gap-2 lg:w-full lg:justify-between">
            <p class="text-xl cursor-context-menu -mt-1">Adedero
            </p>
            <span class="border-l-2 border-l-gray-400 h-5 lg:hidden"></span>
            <div class="flex items-center gap-2">
              <SocialIcons />
              <span class="border-l-2 border-l-gray-400 h-5"></span>
              <DarkModeButton />
            </div>
          </div>
          
        </header>

        <div class="px-5">
          <hr class="border-gray-400">
        </div>

        <div class="views flex flex-col items-center gap-10 py-5 overflow-y-scroll">
          <RouterView />
        </div>
      </div>     
    </section>
  </main>
</template>
<style scoped>
main {
  height: 100dvh;
}

section {
  min-height: 100%;
  border-radius: 10px;
  overflow-y: scroll;
}

#overlay {
  transition: opacity .3s ease;
  background: #fc00ff;
  background: -webkit-linear-gradient(to bottom, #00dbde6a, #fc00ff6a);
  background: linear-gradient(to bottom, #00dade6a, #fb00ff6a);
}

.views {
  min-height: calc(100dvh - 7rem);
  height: calc(100dvh - 5rem);
}

@media screen and (min-width: 1024px) {
  main {
    background: #fc00ff;
    background: -webkit-linear-gradient(to bottom, #00dbde, #fc00ff);
    background: linear-gradient(to bottom, #00dbde, #fc00ff);
  }
  .views {
    height: calc(100dvh - 7rem);
  }
}

</style>
