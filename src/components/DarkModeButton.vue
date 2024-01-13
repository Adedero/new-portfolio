<script setup>
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <button type="button" @click="toggleDark()" class="h-8 flex">
    <span class="material-symbols-rounded text-4xl md:text-3xl">{{ isDark? 'dark_mode': 'light_mode'}}</span>
  </button>
</template>