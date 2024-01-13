<script setup>
import HeroView from './HeroView.vue';

</script>

<template>
    <section id="home" class="pt-16 h-[100dvh] bg-inherit pb-5 px-5 md:px-10 md:flex md:items-center md:justify-between fixed w-full top-0 z-[-1] overflow-y-scroll ">
        <HeroView />
    </section>
    <section id="about" class="h-[100dvh] mt-[100dvh] z-[999] bg-red-500"></section>
    <section id="contact" class="h-[100dvh]"></section>
</template>

<style scoped>

</style>
