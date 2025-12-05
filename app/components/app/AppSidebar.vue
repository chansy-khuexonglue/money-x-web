<template>
  <div :class="['transition-all duration-200', collapsed ? 'w-16' : 'w-72']">
    <div class="bg-white p-4 sm:p-2 shadow-sm flex flex-col h-full relative">
      <!-- Header -->
      <div
        class="flex gap-2 items-center mb-6 transition-all"
        :class="collapsed ? 'justify-center' : 'justify-between'"
      >
        <!-- Profile -->
        <div
          class="flex items-center gap-3"
          :class="collapsed ? 'hidden justify-center items-center' : 'block'"
        >
          <div
            class="w-12 h-12 bg-linear-to-br from-amber-200 to-amber-300 rounded-full flex items-center justify-center text-2xl"
          >
            👩🏻
          </div>
          <h2 v-if="!collapsed" class="font-semibold text-gray-800">
            Hi, Nichole 👋
          </h2>
        </div>
        <!-- Collapse toggle -->
        <div class="flex items-center justify-center">
          <button
            @click="collapsed = !collapsed"
            class="size-8 rounded-xl hover:bg-gray-100 transition flex items-center justify-center cursor-pointer"
            :aria-expanded="!collapsed"
            :title="collapsed ? 'Expand' : 'Collapse'"
          >
            <Icon
              :name="
                collapsed ? 'heroicons:chevron-right' : 'heroicons:chevron-left'
              "
              size="18"
            />
          </button>
        </div>
      </div>

      <!-- Menu -->
      <nav class="flex-1">
        <ul class="space-y-2">
          <li v-for="item in menuItems" :key="item.label">
            <NuxtLink :to="item.path">
              <button
                class="w-full flex items-center gap-3 px-2 py-3 rounded-xl transition-all cursor-pointer"
                :class="[
                  item.isActive
                    ? 'bg-gray-900 text-white'
                    : 'text-gray-600 hover:bg-gray-100',
                  collapsed ? 'px-0 justify-center' : 'px-4',
                ]"
                :title="item.label"
              >
                <div :class="collapsed ? 'w-full flex justify-center' : ''">
                  <Icon :name="item.icon" size="20" />
                </div>
                <span v-show="!collapsed" class="text-sm font-medium"
                  >{{ item.label }}
                </span>
              </button>
            </NuxtLink>
          </li>
        </ul>
      </nav>

      <!-- Settings -->
      <div class="mt-auto">
        <button
          class="w-full flex items-center gap-3 px-4 py-3 text-gray-600 hover:bg-gray-100 rounded-xl transition-all"
        >
          <div :class="collapsed ? 'w-full flex justify-center' : ''">
            <Icon name="heroicons:cog-6-tooth" size="20" />
          </div>
          <span v-show="!collapsed" class="text-sm font-medium">Setting</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
const router = useRouter();
const collapsed = ref(false);

const menuItems = ref([
  {
    icon: "heroicons:view-columns",
    label: "Dashboard",
    path: "/",
    isActive: true,
  },
  {
    icon: "heroicons:credit-card",
    label: "My cards",
    path: "/cards",
    isActive: false,
  },
  {
    icon: "heroicons:banknotes",
    label: "Savings",
    path: "/savings",
    isActive: false,
  },
  {
    icon: "heroicons:receipt-percent",
    label: "Transaction",
    path: "/transactions",
    isActive: false,
  },
  {
    icon: "heroicons:chart-bar",
    label: "Statistic",
    path: "/statistics",
    isActive: false,
  },
]);

const isActivePath = () => {
  const { fullPath } = router.currentRoute.value;

  menuItems.value = menuItems.value.map((item) => {
    // const currentPath = localePath(item.link);
    const currentPath = item.path;
    return {
      ...item,
      isActive: currentPath === fullPath,
    };
  });
};

watch(
  () => route.path,
  () => {
    isActivePath();
  },
  {
    immediate: true,
  }
);

onMounted(() => {
  isActivePath();
});
</script>

<style scoped></style>
