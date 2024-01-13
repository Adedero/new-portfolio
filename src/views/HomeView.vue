<script setup>
import HeroView from './HeroView.vue';
import AboutView from './AboutView.vue';
import SkillsView from './SkillsView.vue';
</script>

<template>
    <section id="home" class="pt-16 h-[100dvh] w-full bg-inherit pb-5 px-5 md:px-10 md:flex md:items-center md:justify-between lg:px-32 overflow-y-scroll">
        <HeroView />
    </section>

    <section id="about" class="pt-16 px-5 pb-5 md:px-5 h-[100dvh] bg-[var(--light)] dark:bg-[var(--dark)] overflow-y-roll md:grid md:grid-cols-2 md:gap-x-1 lg:px-32">
        <AboutView />
    </section>

    <section id="skills" class="pt-16 px-5 pb-5 h-[100dvh] bg-[var(--light)] dark:bg-[var(--dark)] overflow-y-scroll md:hidden">
        <SkillsView />
    </section>

    <section id="contact" class="h-[100dvh] bg-red-500"></section>
</template>

<style scoped>
#home, #about, #skills, #contact {
    scroll-snap-align: center;
}
</style>
