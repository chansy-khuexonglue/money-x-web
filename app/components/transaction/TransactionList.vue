<template>
  <div>
    <div class="bg-white rounded-3xl p-8 shadow-sm">
      <div class="flex justify-between items-start mb-6">
        <h3 class="text-lg font-semibold text-gray-900">Transaction</h3>
        <button
          class="px-4 py-2 bg-gray-900 text-white rounded-full text-sm font-medium hover:bg-gray-800 transition"
        >
          View all
        </button>
      </div>

      <div class="space-y-4">
        <div
          v-for="t in transactions"
          :key="t.id"
          class="flex items-center justify-between p-4 hover:bg-gray-50 rounded-xl transition"
        >
          <div class="flex items-center gap-4">
            <div
              :class="t.color"
              class="w-12 h-12 rounded-full flex items-center justify-center text-xl"
            >
              {{ t.icon }}
            </div>

            <div>
              <p class="font-semibold text-gray-900">{{ t.name }}</p>
              <p class="text-sm text-gray-400">{{ t.date }}</p>
            </div>
          </div>

          <div class="flex items-center gap-3">
            <p
              :class="t.amount > 0 ? 'text-green-600' : 'text-gray-900'"
              class="font-semibold"
            >
              {{ t.amount > 0 ? "+" : "" }}${{ Math.abs(t.amount) }}
            </p>

            <button class="text-gray-400 hover:text-gray-600">
              <Icon name="heroicons:arrow-path" size="18" />
            </button>

            <button class="text-gray-400 hover:text-gray-600">
              <Icon name="heroicons:arrow-down-tray" size="18" />
            </button>

            <button class="text-gray-400 hover:text-gray-600">
              <Icon name="heroicons:ellipsis-horizontal" size="18" />
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const transactions = [
  {
    id: 1,
    name: "Monthly Groceries",
    date: "Oct 24, 2021",
    amount: -33.6,
    icon: "🛒",
    color: "bg-yellow-400",
  },
  {
    id: 2,
    name: "Lazada Cashback",
    date: "Oct 9, 2021",
    amount: 2.5,
    icon: "💜",
    color: "bg-purple-500",
  },
];
</script>

<style scoped></style>
