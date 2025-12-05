<template>
  <div class="min-h-screen w-full p-6">
    <div class="flex gap-6 w-full">
      <!-- Main Content -->
      <div class="w-full space-y-6">
        <!-- My Cards -->
        <CardMain />
        <!-- Savings -->
        <SavingList />

        <!-- Transactions -->
        <TransactionList />
      </div>

      <!-- Right Sidebar -->
      <div class="min-w-sm space-y-6">
        <!-- Quick Actions -->
        <AppQuickActions />

        <!-- Statistics -->
        <AppStatistics />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>
