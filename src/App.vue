<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="max-w-7xl mx-auto pt-5">
      <nav class="space-x-8">
        <RouterLink class="px-4 rounded-xl text-white font-semibold  py-2 bg-indigo-500 duration-175 hover:bg-indigo-700" to="/">Home</RouterLink>
        <RouterLink class="px-4 rounded-xl text-white font-semibold  py-2 bg-red-500 duration-175 hover:bg-red-700" to="/skills">Skills</RouterLink>
      </nav>
    </div>
  </header>
  <main class="max-w-7xl mx-auto min-h-screen">
    <RouterView />
  </main>
</template>
