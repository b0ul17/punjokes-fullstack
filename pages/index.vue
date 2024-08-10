<template>
  <div class="mx-auto px-4 sm:px-6 lg:px-8 max-w-2xl min-h-screen flex flex-col justify-center">
    <div
      class=" mx-auto max-w-[800px] p-6 border border-gray-200 rounded-lg shadow hover:bg-gray-100 bg-neutral-50 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700 rounded-lg  ring-1 ring-gray-200 shadow"
    >
      <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
        {{ jokeArray[0] }}
      </h5>
      <p class="font-normal text-gray-700 dark:text-gray-400 text-center">
        {{ jokeArray[1] }}
      </p>
    </div>
  </div>
</template>

<script setup>
const { data: joke } = await useFetch('https://punjokes.vercel.app')

const jokeArray = joke.value.joke.split('\n')
</script>
