<script setup>
import { RouterLink } from 'vue-router'
const emits = defineEmits(['nav-link-click'])
</script>

<template>
    <div class="p-5 pt-1 flex flex-col gap-3 text-sm text-gray-700 dark:text-white">
        <div @click="$emit('nav-link-click')">
            <router-link to="/"
                class="flex items-center gap-3 transition p-2 rounded-md hover:bg-white hover:bg-opacity-50 dark:hover:bg-gray-600">
                <span class="material-symbols-rounded text-[#1C89FA] dark:text-white">home</span>
                <span class="font-medium mt-[0.15rem]">Home</span>
            </router-link>

            <router-link to="/about"
                class="flex items-center gap-3 transition p-2 rounded-md hover:bg-white hover:bg-opacity-50 dark:hover:bg-gray-600">
                <span class="material-symbols-rounded text-[#1C89FA] dark:text-white">info</span>
                <span class="font-medium mt-[0.15rem]">About</span>
            </router-link>

            <router-link to="/skills"
                class="flex items-center gap-3 transition p-2 rounded-md hover:bg-white hover:bg-opacity-50 dark:hover:bg-gray-600">
                <span class="material-symbols-rounded text-[#1C89FA] dark:text-white">leaderboard</span>
                <span class="font-medium">Skills</span>
            </router-link>

            <router-link to="/projects"
                class="flex items-center gap-3 transition p-2 rounded-md hover:bg-white hover:bg-opacity-50 dark:hover:bg-gray-600">
                <span class="material-symbols-rounded text-[#1C89FA] dark:text-white">folder</span>
                <span class="font-medium">Projects</span>
            </router-link>

            <router-link to="/contact"
                class="flex items-center gap-3 transition p-2 rounded-md hover:bg-white hover:bg-opacity-50 dark:hover:bg-gray-600">
                <span class="material-symbols-rounded text-[#1C89FA] dark:text-white">contact_page</span>
                <span class="font-medium mt-[0.15rem]">Contact</span>
            </router-link>
        </div>

        <hr class="my-3 border-gray-400">

        <p
            class="flex items-center gap-3 transition p-2 rounded-md hover:bg-white hover:bg-opacity-50 dark:hover:bg-gray-600 cursor-context-menu">
            <span class="material-symbols-rounded text-[#1C89FA] dark:text-white">handyman</span>
            <span class="font-medium">Tools</span>
        </p>

        <div class="pl-6 pt-2 flex flex-col gap-5">
            <div class="flex items-center flex-wrap gap-x-3 gap-y-2 cursor-context-menu">
                <img src="../assets/images/html.svg" alt="html" class="w-[1.3rem]">
                <span class="font-medium">HTML</span>
                <div class="bg-white w-full h-[0.35rem] rounded-full">
                    <div class="bg-[#1C89FA] dark:bg-[#FF4302] h-full w-[90%] rounded-full"></div>
                </div>
            </div>

            <div class="flex items-center flex-wrap gap-x-3 gap-y-2 cursor-context-menu">
                <img src="../assets/images/css.svg" alt="css" class="w-[1.3rem]">
                <span class="font-medium">CSS</span>
                <div class="bg-white w-full h-[0.35rem] rounded-full">
                    <div class="bg-[#1C89FA] dark:bg-[#FF4302] h-full w-[79%] rounded-full"></div>
                </div>
            </div>

            <div class="flex items-center flex-wrap gap-x-3 gap-y-2 cursor-context-menu">
                <img src="../assets/images/javascript.svg" alt="js" class="w-[1.2rem] ml-[0.12rem]">
                <span class="font-medium">JavaScript</span>
                <div class="bg-white w-full h-[0.35rem] rounded-full">
                    <div class="bg-[#1C89FA] dark:bg-[#FF4302] h-full w-[88%] rounded-full"></div>
                </div>
            </div>

            <div class="flex items-center flex-wrap gap-x-3 gap-y-2 cursor-context-menu">
                <img src="../assets/images/vue.svg" alt="vue" class="w-6">
                <span class="font-medium">Vue</span>
                <div class="bg-white w-full h-[0.35rem] rounded-full">
                    <div class="bg-[#1C89FA] dark:bg-[#FF4302] h-full w-[81%] rounded-full"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

a.router-link-exact-active {
    @apply bg-white bg-opacity-50 dark:bg-gray-600
}

</style>