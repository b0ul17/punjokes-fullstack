<template>
  <div class="h-dvh">
    <div class="text-right p-4">
      <button
        @click="toggleColorMode"
      >
        <Icon
          v-if="$colorMode.preference ==='dark'"
          name="ion:android-sunny"
          class="text-white text-2xl"
        />
        <Icon
          v-else
          name="ion:moon-sharp"
          class="text-blak text-2xl"
        />
      </button>
    </div>
    <div class="flex flex-col justify-center h-5/6">
      <NuxtPage />
    </div>
  </div>
</template>

<script setup>
const colorMode = useColorMode()

function toggleColorMode() {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark'
}
</script>

<style>
body {
  @apply font-sans text-gray-950 bg-neutral-50;
}

.dark-mode body {
  @apply dark:bg-gray-950 dark:text-white
}
</style>
