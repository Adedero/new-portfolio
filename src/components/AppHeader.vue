<script setup>
import HeaderLogo from './HeaderLogo.vue';
import DarkModeButton from './DarkModeButton.vue';
import LargeNav from './LargeNav.vue';

const emits = defineEmits([ 'open-nav' ])
</script>

<template>
    <header class="flex items-center justify-between p-5 fixed top-0 w-full bg-inherit bg-opacity-10 h-16 z-50 lg:px-10">
        <HeaderLogo />

        <div class="flex items-center gap-5">
            <div class="hidden md:flex">
                <LargeNav />
            </div>

            <DarkModeButton />

            <button type="button" class="h-8 md:hidden" @click="$emit('open-nav')">
                <span class="material-symbols-rounded text-4xl">menu</span>
            </button>
        </div>
    </header>
</template>