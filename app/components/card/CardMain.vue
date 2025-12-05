<template>
  <div
    class="bg-gradient-to-br from-gray-900 via-gray-800 to-emerald-900 rounded-3xl p-8 text-white shadow-xl"
  >
    <div class="flex justify-between items-start mb-6">
      <div>
        <h3 class="text-lg font-semibold mb-1">My cards</h3>
        <p class="text-gray-400 text-sm">Total 4 cards</p>
      </div>
      <div class="flex gap-2">
        <button
          class="w-10 h-10 bg-white/10 rounded-full flex items-center justify-center hover:bg-white/20 transition"
        >
          <Icon name="heroicons:plus" size="20" />
        </button>
        <button
          class="px-4 py-2 bg-white text-gray-900 rounded-full text-sm font-medium hover:bg-gray-100 transition"
        >
          View all
        </button>
      </div>
    </div>

    <div class="flex gap-6">
      <!-- Card -->
      <div
        class="bg-gradient-to-br from-gray-700 to-gray-600 rounded-2xl p-6 w-64 backdrop-blur"
      >
        <div class="flex justify-between items-start mb-8">
          <div
            class="w-12 h-8 bg-gradient-to-br from-gray-400 to-gray-500 rounded flex items-center justify-center"
          >
            <div class="w-6 h-6 rounded-full bg-white/30"></div>
          </div>
        </div>
        <div class="mb-6">
          <p class="text-lg font-mono tracking-wider mb-2">
            7812 2139 0823 XXXX
          </p>
          <div class="flex gap-4 text-xs text-gray-300">
            <div>
              <p class="text-gray-400">VALID THRU</p>
              <p>05/24</p>
            </div>
            <div>
              <p class="text-gray-400">CVV</p>
              <p>09X</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Card Info -->
      <div class="flex-1 flex flex-col justify-between">
        <div>
          <p class="text-gray-400 text-sm mb-1">Available amount</p>
          <p class="text-3xl font-bold mb-4">$4561.80</p>
        </div>
        <div class="grid grid-cols-2 gap-4 text-sm">
          <div>
            <p class="text-gray-400 mb-1">Card balance</p>
            <p class="font-semibold">$3817.30</p>
          </div>
          <div>
            <p class="text-gray-400 mb-1">Credit limit</p>
            <p class="font-semibold">$1281.30</p>
          </div>
        </div>

        <!-- Card buttons -->
        <div class="flex gap-2 mt-4">
          <button
            class="w-10 h-10 bg-white/10 rounded-xl flex items-center justify-center hover:bg-white/20 transition"
          >
            <Icon name="heroicons:paper-airplane" size="18" />
          </button>
          <button
            class="w-10 h-10 bg-white/10 rounded-xl flex items-center justify-center hover:bg-white/20 transition"
          >
            <Icon name="heroicons:eye" size="18" />
          </button>
          <button
            class="w-10 h-10 bg-white/10 rounded-xl flex items-center justify-center hover:bg-white/20 transition"
          >
            <Icon name="heroicons:ellipsis-horizontal-circle" size="18" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped></style>
