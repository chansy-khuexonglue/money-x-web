<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-100 to-gray-200 p-6">
    <div class="max-w-7xl mx-auto">
      <div class="grid grid-cols-12 gap-6">
        <!-- Sidebar -->
        <AppSidebar />
        <!-- Main Content -->
        <div class="col-span-12 lg:col-span-7 space-y-6">
          <!-- My Cards -->
          <CardMain />
          <!-- Savings -->
          <SavingList />

          <!-- Transactions -->
          <TransactionList />
        </div>

        <!-- Right Sidebar -->
        <div class="col-span-12 lg:col-span-3 space-y-6">
          <!-- Quick Actions -->
          <AppQuickActions />

          <!-- Statistics -->
          <AppStatistics />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>
