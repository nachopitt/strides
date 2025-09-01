<template>
  <div class="p-6">
    <h1 class="text-2xl font-bold">{{ message }}</h1>
    <p>Time to build something awesome 🚀</p>
    <div class="bg-white shadow p-6 rounded-lg">
        <p>My content is here!!!</p>
    </div>
  </div>
</template>

<script setup>
defineProps(['message']);
</script>
