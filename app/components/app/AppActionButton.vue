<template>
  <div class="flex items-center justify-center">
    <button class="flex gap-2 flex-col items-center cursor-pointer">
      <div
        class="flex flex-col items-center gap-2 p-4 bg-purple-100 text-purple-600 rounded-2xl hover:bg-purple-200 transition"
      >
        <Icon name="heroicons:plus" size="20" />
      </div>
      <span class="text-sm font-medium text-gray-700">{{ title }}</span>
    </button>
  </div>
</template>

<script setup lang="ts">
type Props = {
  title: string;
};

const props = defineProps<Props>();
</script>

<style scoped></style>
