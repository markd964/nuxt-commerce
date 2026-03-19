<script lang="ts" setup>
const cardDetails = [
  {
    title: 'Nuxt UI',
    description: 'A UI Library for Modern Web Apps',
    link: 'https://ui.nuxt.com/',
    icon: 'i-heroicons-squares-2x2',
  },
  {
    title: 'GraphQL Client',
    description: 'Minimal GraphQL Client + Code Generation',
    link: 'https://nuxt-graphql-client.web.app/',
    icon: 'i-heroicons-circle-stack',
  },
  {
    title: 'Image Optimization',
    description: 'Resize and transform your images using built-in optimizer or your favorite images CDN',
    link: 'https://image.nuxt.com/',
    icon: 'i-heroicons-photo',
  },
  {
    title: 'Scripts',
    description: 'Load third-party scripts with better performance, privacy, security and DX',
    link: 'https://scripts.nuxt.com/',
    icon: 'i-heroicons-code-bracket',
  },
  {
    title: 'Hybrid Rendering',
    description: 'Set different caching rules per route using Route Rules and decide how the server should respond',
    link: 'https://nuxt.com/docs/guide/concepts/rendering#hybrid-rendering',
    icon: 'i-heroicons-server',
  },
  {
    title: 'SEO',
    description: 'Simple configuration for Sitemap.xml, Robots.txt, and Meta',
    link: 'https://nuxtseo.com/',
    icon: 'i-heroicons-magnifying-glass',
  },
  {
    title: 'JSON-LD',
    description: 'Lightweight Linked Data format for products',
    link: 'https://json-ld.org/',
    icon: 'i-heroicons-document-text',
  },
]

useSeoMeta({
  title: 'About',
  description: 'E-Commerce application built with Nuxt & Shopify',
  ogTitle: 'Nuxt Commerce',
  ogDescription: 'E-Commerce application built with Nuxt & Shopify',
  twitterCard: 'summary_large_image',
})

defineOgImageComponent('Nuxt', {
  title: 'Nuxt Commerce',
  description: 'A high-performance, server-rendered E-commerce app built with Nuxt & Shopify',
  theme: '#4ADE80',
  headline: '',
  colorMode: 'dark',
})
</script>

<template>
  <section class="text-white max-w-7xl px-6 mx-auto">
    <!-- Header -->
    <div class="text-center py-16">
      <span class="text-xs font-semibold tracking-widest uppercase text-primary-400 mb-4 block">
        Built With
      </span>
      <h1 class="text-4xl md:text-5xl font-bold mb-4">
        Nuxt Commerce
      </h1>
      <p class="text-slate-400 max-w-xl mx-auto text-lg">
        A high-performance, server-rendered E-commerce app built with Nuxt & Shopify.
      </p>
    </div>

    <!-- Cards Grid -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5 pb-16">
      
        v-for="({ title, description, link, icon }, index) in cardDetails"
        :key="`${title}-${index}`"
        :href="link"
        target="_blank"
        :aria-label="`Link to documentation of ${title}`"
        class="group relative flex flex-col gap-3 p-6 rounded-xl border border-slate-700/60 bg-slate-900/60 hover:border-primary-500/60 hover:bg-slate-800/80 transition-all duration-300 backdrop-blur-sm"
      >
        <!-- Icon -->
        <div class="w-10 h-10 rounded-lg bg-primary-500/10 flex items-center justify-center group-hover:bg-primary-500/20 transition-colors duration-300">
          <UIcon :name="icon" class="text-primary-400 text-xl" />
        </div>

        <!-- Text -->
        <div>
          <p class="font-semibold text-white group-hover:text-primary-400 transition-colors duration-200">
            {{ title }}
          </p>
          <p class="mt-1 text-sm text-slate-400 leading-relaxed">
            {{ description }}
          </p>
        </div>

        <!-- Arrow -->
        <div class="mt-auto pt-2 flex items-center gap-1 text-xs text-slate-500 group-hover:text-primary-400 transition-colors duration-200">
          View docs
          <UIcon name="i-heroicons-arrow-top-right-on-square" class="text-sm" />
        </div>

        <!-- Glow effect -->
        <div class="absolute inset-0 rounded-xl opacity-0 group-hover:opacity-100 transition-opacity duration-300 pointer-events-none ring-1 ring-primary-500/20" />
      </a>
    </div>
  </section>
</template>