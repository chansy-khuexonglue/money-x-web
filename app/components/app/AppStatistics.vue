<template>
  <div>
    <div class="bg-white rounded-3xl p-6 shadow-sm">
      <div class="flex justify-between items-center mb-6">
        <h3 class="text-lg font-semibold text-gray-900">Statistics</h3>
        <button class="text-sm text-gray-500 flex items-center gap-1">
          Dec 2021
          <Icon name="heroicons:chevron-down" size="14" />
        </button>
      </div>

      <div class="space-y-4">
        <div
          v-for="s in statistics"
          :key="s.label"
          class="flex items-center justify-between p-4 bg-gray-50 rounded-2xl"
        >
          <div class="flex items-center gap-3">
            <div
              :class="s.color"
              class="w-10 h-10 rounded-full flex items-center justify-center text-xl"
            >
              {{ s.icon }}
            </div>

            <div>
              <p class="text-xs text-gray-500">{{ s.label }}</p>
              <p class="font-semibold text-gray-900">${{ s.amount }}</p>
            </div>
          </div>

          <span :class="s.changeColor" class="text-sm font-semibold">
            {{ s.change }}
          </span>
        </div>
      </div>

      <button
        class="w-full mt-6 py-3 bg-gray-900 text-white rounded-2xl font-medium hover:bg-gray-800 transition"
      >
        View all
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
const statistics = [
  {
    label: "Total income",
    amount: 120.5,
    change: "+20%",
    icon: "😊",
    color: "bg-yellow-400",
    changeColor: "text-blue-500",
  },
  {
    label: "Total expenses",
    amount: 120.5,
    change: "+8%",
    icon: "📊",
    color: "bg-purple-500",
    changeColor: "text-blue-500",
  },
  {
    label: "Total savings",
    amount: 120.5,
    change: "-12%",
    icon: "🎯",
    color: "bg-gray-300",
    changeColor: "text-red-500",
  },
];
</script>

<style scoped></style>
