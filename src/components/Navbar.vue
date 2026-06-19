<template>
  <nav class="flex items-center justify-between px-6 py-3 bg-black text-white border-b border-white">

    <div class="text-[40px] font-bold font-mono">
      Shortcuts
    </div>

    <div class="flex-1 flex justify-center">
      <input
        v-model="search"
        type="text"
        placeholder="Search..."
        class="w-full max-w-md px-4 py-2 rounded-md bg-white text-black placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-gray-400"
      />
    </div>

    <div class="w-[120px]"></div>
  </nav>
</template>

<script setup lang="ts">
const search = defineModel()
</script>
