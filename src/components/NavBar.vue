<script setup>
import { useRouter } from 'vue-router';

const router = useRouter()

const props = defineProps({
    isOpen: Boolean
})

const emoits = defineEmits([ 'close-nav' ])

const classList = "transition h-60 w-36 text-right overflow-y-scroll bg-white bg-opacity-50 backdrop-blur-[200px] shadow-lg fixed right-4 top-16 -z-10 opacity-0 dark:bg-gray-800 dark:bg-opacity-60 dark:backdrop-blur-[200px] rounded-lg flex flex-col justify-between p-6 text-slate-800 dark:text-[var(--light)] dark:font-light"

const showNav = "transition opacity-100 z-20"

function goTo(path, id = "") {
    router.push(path)
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' })
}

</script>


<template>
    <nav :class="[classList, isOpen ? showNav : '']">
        <a class="nav-link" href="#home" @click="goTo('/', 'home'), $emit('close-nav')">Home</a>

        <a class="nav-link" href="#about" @click="goTo('/', 'about'), $emit('close-nav')">About</a>

        <a class="nav-link" href="#projects" @click="goTo('/projects'), $emit('close-nav')">Projects</a>

        <a class="nav-link" href="#contact" @click="goTo('/', 'contact'), $emit('close-nav')">Contact</a>
    </nav>

    <div :class="['fixed w-[100dvw] h-[100dvh] opacity-0 -z-10 top-0', isOpen ? 'transition opacity-100 z-10' : '']" @click="$emit('close-nav')"></div>

</template>

<style scoped>
.nav-link {
    transition: .3s;
}

.nav-link:hover {
    @apply font-bold -translate-x-3
}
</style>