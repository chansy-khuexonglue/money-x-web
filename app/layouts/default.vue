<template>
  <div class="flex w-full h-screen bg-gradient-to-br from-gray-100 to-gray-200">
    <AppSidebar />
    <main class="w-full overflow-auto">
      <div class="mx-auto container">
        <slot />
      </div>
    </main>
  </div>
</template>

<script setup lang="ts"></script>
