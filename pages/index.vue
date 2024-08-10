<template>
  <div class="mx-auto px-4 sm:px-6 lg:px-8 max-w-2xl min-h-screen flex flex-col justify-center">
    <div
      class=" mx-auto p-6 border border-gray-200 rounded-lg shadow hover:bg-gray-100 bg-neutral-50 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700 rounded-lg  ring-1 ring-gray-200 shadow"
    >
      <p
        v-for="(line, index) in jokeArray"
        :key="index"
        class="text-2xl font-bold text-gray-900 dark:text-white text-balance"
      >
        {{ line }}
      </p>
    </div>
  </div>
</template>

<script setup>
const { data: joke } = await useFetch('https://punjokes.vercel.app')

const jokeArray = joke.value.joke.split('\n')
</script>
