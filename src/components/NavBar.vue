<script setup>
import NavLinks from './NavLinks.vue'

const props = defineProps({
    isOpen: Boolean
})

const emits = defineEmits([ 'close', 'nav-link-click' ])

</script>


<template>
    <nav :style="isOpen? 'transform: translateX(0);': ''" class="translate-x-[-110%] h-full w-72 overflow-y-scroll pb-10 bg-white bg-opacity-60 backdrop-blur-[200px] shadow-lg shadow-gray-900 fixed left-0 top-0 z-50 lg:relative lg:shadow-none lg:translate-x-0 lg:w-80 dark:bg-gray-900 dark:bg-opacity-70 dark:backdrop-blur-[200px]">
        <header class="p-5 flex items-center justify-between">
            <span class="material-symbols-rounded font-bold text-[#FF4302] cursor-pointer select-none lg:hidden" @click="$emit('close')">close</span>

            <svg viewBox="-2 -2 114 64" class="w-10">
                <g class="fill-slate-500 dark:fill-gray-50">
                    <circle cx="97.32" cy="47.41" r="13.59"/>
                    <polygon points="18.9 29.98 0 61 37.8 61 18.9 29.98"/>
                    <polygon points="25.36 18.83 51.82 61 75.42 61 37.14 0 25.36 18.83"/>
                </g>
            </svg>
        </header>

        <NavLinks @nav-link-click="$emit('nav-link-click')" />
    </nav>

</template>

<style scoped>
nav {
    transition:  .3s;
}
</style>
