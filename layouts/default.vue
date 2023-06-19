<template>
  <div class="w-full min-h-screen bg-zinc-950 flex flex-col overflow-hidden">
    <!-- <Header /> -->
      <div class="w-auto select-none
        flex items-center justify-center relative text-center">
          <MouseShadow />
          <slot />
      </div>
    <Footer />
  </div>
</template>
<script setup lang="ts">
import MouseShadow from "~/components/generics/MouseShadow.vue";
</script>