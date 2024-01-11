<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
        <div class="w-24 max-w-12 overflow-hidden">
            <img src="../assets/images/chat.svg" alt="chat_icon">
        </div>
        <div class="text text-gray-700 dark:text-white text-sm lg:text-base">
            <h1 class="">Hi, there!</h1>
            <p>I'm <b class="text-[#1C89FA] dark:text-white">Adedero Cosmos</b>, a front-end developer dedicated to making your designs a picture perfect reality. If you can think it, I can build it!</p>

            <div class="mt-2 text-sm font-bold flex items-center gap-5">
                <RouterLink to="/contact">
                    <button type="button" class="bg-[#1C89FA] hover:bg-blue-600 transition-colors py-2 px-3 rounded-md text-white">Hire me</button>
                </RouterLink>

                <RouterLink to="/about">
                    <button type="button" class="text-[#1C89FA] dark:text-white hover:underline">Learn more</button>
                </RouterLink>
            </div>
        </div> 
</template>

<style scoped>
.text {
    line-height: 1.6rem;
}

</style>
