<script setup>
import AboutHeader from '@/components/AboutHeader.vue';
import AboutBody from '@/components/AboutBody.vue';
</script>

<template>
    <main class="p-1 w-full h-full lg:p-0">
         <AboutHeader />

         <section class="about-body p-5 flex justify-center bg-gray-200">
            <AboutBody />
         </section>
    </main>
   
</template>

<style scoped>
.about-body {
    height: calc(100dvh - 15rem);
    overflow-y: scroll;
}

@media screen and (min-width: 1024px) {
    .about-body {
        height: calc(100dvh - 16.5rem);
    }
}
</style>
