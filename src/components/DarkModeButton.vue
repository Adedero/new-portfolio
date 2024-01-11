<script setup>
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <button type="button" @click="toggleDark()" class="bg-zinc-200 dark:bg-gray-700 h-8 flex items-center justify-center p-1 rounded-md">
    <span class="material-symbols-rounded">{{ isDark? 'dark_mode': 'light_mode'}}</span>
  </button>
</template>