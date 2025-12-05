<template>
  <div>
    <div class="bg-white rounded-3xl p-8 shadow-sm">
      <div class="flex justify-between items-start mb-6">
        <div>
          <h3 class="text-lg font-semibold text-gray-900 mb-1">Savings</h3>
          <p class="text-gray-400 text-sm">Total 7 wallets</p>
        </div>
        <div class="flex gap-2">
          <button
            class="w-10 h-10 bg-gray-100 rounded-full flex items-center justify-center hover:bg-gray-200 transition"
          >
            <Icon name="heroicons:plus" size="20" />
          </button>
          <button
            class="px-4 py-2 bg-gray-900 text-white rounded-full text-sm font-medium hover:bg-gray-800 transition"
          >
            View all
          </button>
        </div>
      </div>

      <div class="grid grid-cols-3 gap-4">
        <div
          v-for="goal in savingsGoals"
          :key="goal.name"
          class="bg-gray-50 rounded-2xl p-5"
        >
          <div class="flex justify-between items-start mb-3">
            <p class="text-sm text-gray-600">{{ goal.name }}</p>
            <button class="text-gray-400 hover:text-gray-600">
              <Icon name="heroicons:ellipsis-horizontal" size="16" />
            </button>
          </div>

          <p class="text-xl font-bold text-gray-900 mb-3">${{ goal.amount }}</p>

          <div class="w-full bg-gray-200 rounded-full h-2">
            <div
              :class="goal.color"
              class="h-2 rounded-full"
              :style="{ width: goal.progress + '%' }"
            ></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const savingsGoals = [
  { name: "Summer trip", amount: 370.52, progress: 75, color: "bg-yellow-400" },
  { name: "Gaming PC", amount: 461.22, progress: 45, color: "bg-indigo-500" },
  { name: "Vacation fund", amount: 120.5, progress: 30, color: "bg-red-500" },
];
</script>

<style scoped></style>
