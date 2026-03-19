<script lang="ts" setup>
const { cart, isCartOpen } = useShopifyCart()

const isCategoryMenuOpen = ref(false)

function closeCategoryMenu() {
  isCategoryMenuOpen.value = false
}

const links = [
  {
    label: 'Latest Stuff',
    to: '/collection/latest-stuff',
    onSelect: closeCategoryMenu,
  },
  {
    label: 'Casual Things',
    to: '/collection/casual-things',
    onSelect: closeCategoryMenu,
  },
  {
    label: 'Summer Clothes',
    to: '/collection/summer-collection',
    onSelect: closeCategoryMenu,
  },
]
</script>

<template>
  <header class="sticky top-0 z-50 w-full backdrop-blur-md bg-slate-950/80 border-b border-slate-800/60">
    <div class="max-w-7xl mx-auto px-6 h-16 flex items-center justify-between gap-4">

      <!-- Left: Hamburger + Logo -->
      <div class="flex items-center gap-3 flex-1">
        <UButton
          color="neutral"
          variant="ghost"
          aria-label="Category Menu Open Button"
          class="lg:hidden"
          icon="i-heroicons-bars-3-20-solid"
          @click="isCategoryMenuOpen = true"
        />
        <NuxtLink
          to="/"
          aria-label="Nuxt Commerce Homepage"
          class="flex items-center gap-2 shrink-0 focus-visible:outline focus-visible:outline-offset focus-visible:rounded-sm"
        >
          <picture>
            <source srcset="/logo-nuxt-commerce.svg" media="(min-width: 768px)">
            <NuxtImg
              src="/logo.svg"
              alt="Nuxt Commerce Logo"
              class="w-8 h-8 md:h-6 md:w-[176px] lg:w-[13.5rem] lg:h-[1.75rem]"
            />
          </picture>
        </NuxtLink>
      </div>

      <!-- Center: Nav Links -->
      <nav class="hidden lg:flex items-center gap-1">
        <NuxtLink
          v-for="link in links"
          :key="link.to"
          :to="link.to"
          class="px-4 py-1.5 rounded-full text-sm font-medium text-slate-400 hover:text-white hover:bg-slate-800 transition-all duration-200"
          active-class="text-white bg-slate-800"
        >
          {{ link.label }}
        </NuxtLink>
      </nav>

      <!-- Right: Search + Cart -->
      <div class="flex items-center gap-2 flex-1 justify-end">
        <LayoutSearchBar class="hidden sm:flex" />

        <UChip
          :text="cart?.lines.edges.length"
          :show="cart?.lines.edges.length ? true : false"
          size="3xl"
        >
          <UButton
            aria-label="Cart"
            :padded="false"
            color="neutral"
            variant="ghost"
            icon="i-heroicons-shopping-cart"
            class="relative w-9 h-9 rounded-full hover:bg-slate-800 transition-colors duration-200"
            @click="isCartOpen = true"
          />
        </UChip>
      </div>
    </div>

    <!-- Mobile Slideover -->
    <USlideover
      v-model:open="isCategoryMenuOpen"
      side="left"
      title="Navigation"
      description="Explore our categories"
      close-icon="i-heroicons-x-mark-20-solid"
    >
      <template #body>
        <div class="flex flex-col gap-4 p-4">
          <LazyLayoutSearchBar
            class="w-full"
            @item-selected="isCategoryMenuOpen = false"
          />
          <div class="flex flex-col gap-1 mt-2">
            <NuxtLink
              v-for="link in links"
              :key="link.to"
              :to="link.to"
              class="px-4 py-3 rounded-lg text-sm font-medium text-slate-400 hover:text-white hover:bg-slate-800 transition-all duration-200"
              active-class="text-white bg-slate-800"
              @click="closeCategoryMenu"
            >
              {{ link.label }}
            </NuxtLink>
          </div>
        </div>
      </template>
    </USlideover>
  </header>
</template>