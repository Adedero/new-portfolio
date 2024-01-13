<script setup>
import { useRouter } from 'vue-router';

const router = useRouter()

function goTo(path, id = "") {
    router.push(path)
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
    <nav class="flex items-center gap-10">
        <a class="nav-link relative" href="#home" @click="goTo('/', 'home'), $emit('close-nav')">Home</a>

        <a class="nav-link relative" href="#about" @click="goTo('/', 'about'), $emit('close-nav')">About</a>

        <a class="nav-link relative" href="#projects" @click="goTo('/projects'), $emit('close-nav')">Projects</a>

        <a class="nav-link relative" href="#contact" @click="goTo('/', 'contact'), $emit('close-nav')">Contact</a>
    </nav>
</template>

<style scoped>
.nav-link::before {
    @apply content-[""] absolute w-0 h-[2px] -bottom-1 bg-slate-700 dark:bg-[var(--light)] transition-all
}

.nav-link:hover:before {
    @apply w-full transition-all
}
</style>