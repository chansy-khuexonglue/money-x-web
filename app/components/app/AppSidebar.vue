<template>
  <div class="w-72">
    <div class="bg-white p-6 shadow-sm flex flex-col h-full">
      <!-- Profile -->
      <div class="mb-8">
        <div
          class="w-12 h-12 bg-gradient-to-br from-amber-200 to-amber-300 rounded-full mb-3 flex items-center justify-center text-2xl"
        >
          👩🏻
        </div>
        <h2 class="font-semibold text-gray-800">Hi, Nichole 👋</h2>
      </div>

      <!-- Menu -->
      <nav class="flex-1">
        <ul class="space-y-2">
          <li v-for="item in menuItems" :key="item.label">
            <NuxtLink :to="item.path">
              <button
                @click="selectedMenu = item.label"
                class="w-full flex items-center gap-3 px-4 py-3 rounded-xl transition-all"
                :class="
                  selectedMenu === item.label
                    ? 'bg-gray-900 text-white'
                    : 'text-gray-600 hover:bg-gray-100'
                "
              >
                <Icon :name="item.icon" size="20" />
                <span class="text-sm font-medium">{{ item.label }}</span>
              </button>
            </NuxtLink>
          </li>
        </ul>
      </nav>

      <!-- Settings -->
      <div class="">
        <button
          class="w-full flex items-center gap-3 px-4 py-3 text-gray-600 hover:bg-gray-100 rounded-xl transition-all mt-auto"
        >
          <Icon name="heroicons:cog-6-tooth" size="20" />
          <span class="text-sm font-medium">Setting</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const selectedMenu = ref("Dashboard");

const menuItems = [
  { icon: "heroicons:view-columns", label: "Dashboard", path: "/" },
  { icon: "heroicons:credit-card", label: "My cards", path: "/cards" },
  { icon: "heroicons:banknotes", label: "Savings", path: "/savings" },
  {
    icon: "heroicons:receipt-percent",
    label: "Transaction",
    path: "/transactions",
  },
  { icon: "heroicons:chart-bar", label: "Statistic", path: "/statistics" },
];
</script>

<style scoped></style>
