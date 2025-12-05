<template>
  <div class="flex w-full h-screen bg-gradient-to-br from-gray-100 to-gray-200">
    <AppSidebar />
    <main class="w-full overflow-auto">
      <slot />
    </main>
  </div>
</template>

<script setup lang="ts"></script>
