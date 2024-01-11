<script setup>
import { RouterLink } from 'vue-router'
import TheWelcome from "@/components/TheWelcome.vue";
</script>

<template>
    <header class="bg-white dark:bg-slate-700 w-[90%] p-3 rounded-2xl flex gap-2 shadow-lg">
        <TheWelcome />
    </header>

    <section class="h-full w-full overflow-y-scroll p-5 pt-2 text-sm text-gray-800 dark:text-white grid gap-4">

        <div class="explorer">
            <router-link to="/about" class="hover:shadow-lg hover:bg-[#F3F3F3] dark:hover:bg-gray-700">
                <img src="../assets/images/docx.svg" alt="" class="w-20 filter drop-shadow-md ">
                <h1>About Me.docx
                    <p class="text-xs text-gray-600 dark:text-gray-400">21.45KB</p>
                </h1>
            </router-link>

            <a href="../../public/adedero-resume.pdf" download class="hover:shadow-lg hover:bg-[#F3F3F3] dark:hover:bg-gray-700">
                <img src="../assets/images/adobe.svg" alt="adobe" class="w-20 filter drop-shadow-md translate-y-2">
                <h1>My Resume.pdf
                    <p class="text-xs text-gray-600 dark:text-gray-400">1.01MB</p>
                </h1>
            </a>
        </div>

        <div class="explorer">
            <router-link to="/skills" class="hover:shadow-lg hover:bg-[#F3F3F3] dark:hover:bg-gray-700">
                <svg viewBox="0 0 100 78" class="w-24 filter drop-shadow-md">
                    <g>
                        <path class="fill-[#f9b552] dark:fill-[#0D78C1]"
                            d="m43,5h38c3.31,0,6,2.69,6,6v24h-50V11c0-3.31,2.69-6,6-6Z" />
                        <path class="fill-[#ffcf5c] dark:fill-[#21B1E9]"
                        d="m88,13h-38v-5c0-4.42-3.58-8-8-8H8C3.58,0,0,3.58,0,8v58c0,6.63,5.37,12,12,12h76c6.63,0,12-5.37,12-12V25c0-6.63-5.37-12-12-12Z" />
                    </g>
                </svg>
                <h1>Skills
                    <p class="text-xs text-gray-600 dark:text-gray-400">7 files - 13.4MB</p>
                </h1>
            </router-link>

            <router-link to="/projets" class="hover:shadow-lg hover:bg-[#F3F3F3] dark:hover:bg-gray-700">
                <svg viewBox="0 0 100 78" class="w-24 filter drop-shadow-md">
                    <g>
                        <path class="fill-[#f9b552] dark:fill-[#0D78C1]"
                        d="m43,5h38c3.31,0,6,2.69,6,6v24h-50V11c0-3.31,2.69-6,6-6Z" />
                        <path class="fill-[#ffcf5c] dark:fill-[#21B1E9]"
                        d="m88,13h-38v-5c0-4.42-3.58-8-8-8H8C3.58,0,0,3.58,0,8v58c0,6.63,5.37,12,12,12h76c6.63,0,12-5.37,12-12V25c0-6.63-5.37-12-12-12Z" />
                    </g>
                </svg>
                <h1>Projects
                    <p class="text-xs text-gray-600 dark:text-gray-400">4 files - 2GB</p>
                </h1>
            </router-link>

            <router-link to="/contact" class="hover:shadow-lg hover:bg-[#F3F3F3] dark:hover:bg-gray-700">
                    <svg viewBox="0 0 100 78" class="w-24 filter drop-shadow-md">
                        <g>
                            <path class="fill-[#f9b552] dark:fill-[#0D78C1]"
                            d="m43,5h38c3.31,0,6,2.69,6,6v24h-50V11c0-3.31,2.69-6,6-6Z" />
                            <path class="fill-[#ffcf5c] dark:fill-[#21B1E9]"
                            d="m88,13h-38v-5c0-4.42-3.58-8-8-8H8C3.58,0,0,3.58,0,8v58c0,6.63,5.37,12,12,12h76c6.63,0,12-5.37,12-12V25c0-6.63-5.37-12-12-12Z" />
                        </g>
                    </svg>
                    <h1>Contact details
                        <p class="text-xs text-gray-600 dark:text-gray-400">5 files - 812.1KB</p>
                    </h1>
                </router-link>
        </div> 
    </section>
</template>

<style scoped>
.explorer {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(8rem, 0.8fr));
    grid-template-rows: repeat(auto-fill, minmax(10rem, 0.5fr));
    gap: 1rem;
}

a {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    gap: 0.5rem;
    padding: 0.5rem;
    border-radius: 1rem;
    transition: box-shadow .3s;
}

@media screen and (min-width: 1024px) {}
</style>
