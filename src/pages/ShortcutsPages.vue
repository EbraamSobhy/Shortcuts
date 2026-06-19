<template>
  <div class="min-h-screen bg-black text-white">

    <Navbar v-model="search" />

    <div class="px-10 py-10 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
      <a
        v-for="(shortcut, index) in filteredShortcuts"
        :key="index"
        :href="shortcut.url"
        target="_blank"
        class="bg-black w-[450px] text-center hover:bg-zinc-800 transition rounded-xl overflow-hidden border border-zinc-800"
      >

        <div class="p-4">
          <h2 class="text-lg font-semibold mb-2">
            {{ shortcut.name }}
          </h2>

          <p class="text-sm text-zinc-400 break-all">
            {{ shortcut.url }}
          </p>
        </div>
      </a>
    </div>

  </div>
</template>

<script setup>
import { ref, computed } from "vue"
import Navbar from "../components/Navbar.vue"
import { shortcuts } from "../data/shortcuts"

const search = ref("")

const filteredShortcuts = computed(() => {
  return shortcuts.filter(s =>
    s.name.toLowerCase().includes(search.value.toLowerCase())
  )
})
</script>
