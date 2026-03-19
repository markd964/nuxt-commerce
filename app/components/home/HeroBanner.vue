<template>
  <div class="relative min-h-[600px] overflow-hidden">

    <!-- Background glow effects -->
    <div class="absolute top-0 left-1/4 w-96 h-96 bg-primary-500/10 rounded-full blur-3xl pointer-events-none" />
    <div class="absolute bottom-0 right-1/4 w-72 h-72 bg-primary-400/5 rounded-full blur-3xl pointer-events-none" />

    <div class="md:flex md:flex-row-reverse md:justify-center mx-auto md:min-h-[600px] relative z-10">

      <!-- Image -->
      <div class="flex flex-col md:items-stretch md:overflow-hidden md:basis-1/2 relative">
        <div class="absolute inset-0 bg-gradient-to-r from-slate-950 via-transparent to-transparent z-10 md:block hidden" />
        <NuxtImg
          src="/hero.png"
          alt="Nuxt Commerce Hero"
          height="600"
          fetch-priority="high"
          preload
          width="800"
          class="h-full object-cover object-left opacity-90"
        />
      </div>

      <!-- Text Content -->
      <div class="md:flex md:flex-col md:justify-center md:items-start md:basis-1/2 text-left px-6 py-12 md:py-0 md:pr-12">

        <!-- Badge -->
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-primary-500/10 border border-primary-500/20 mb-6">
          <span class="w-2 h-2 rounded-full bg-primary-400 animate-pulse" />
          <span class="text-xs font-medium text-primary-400 tracking-wide uppercase">Now Available</span>
        </div>

        <!-- Heading -->
        <h1 class="text-5xl md:text-6xl md:leading-[1.1] font-bold mb-4 text-white">
          Nuxt
          <span class="text-primary-400 relative">
            Commerce
            <span class="absolute -bottom-1 left-0 w-full h-0.5 bg-gradient-to-r from-primary-400 to-transparent rounded-full" />
          </span>
        </h1>

        <!-- Description -->
        <p class="text-slate-400 text-lg leading-relaxed mb-8 max-w-md">
          A high-performance E-Commerce template built with
          
            href="https://nuxt.com/"
            target="_blank"
            class="text-white hover:text-primary-400 transition-colors duration-200 underline underline-offset-2 decoration-slate-600 hover:decoration-primary-400"
            aria-label="Link to Nuxt Home Page"
          >Nuxt</a>
          &amp;
          
            href="https://www.shopify.com/"
            target="_blank"
            class="text-white hover:text-primary-400 transition-colors duration-200 underline underline-offset-2 decoration-slate-600 hover:decoration-primary-400"
            aria-label="Link to Shopify Home Page"
          >Shopify</a>.
          Fast, modern, and ready to scale.
        </p>

        <!-- CTA Buttons -->
        <div class="flex flex-row flex-wrap gap-3">
          <UButton
            color="primary"
            size="xl"
            to="/collection/latest-stuff"
            class="shadow-lg shadow-primary-500/20 hover:shadow-primary-500/40 transition-shadow duration-300"
            trailing-icon="i-heroicons-arrow-right-20-solid"
          >
            Shop Now
          </UButton>

          <UButton
            color="neutral"
            variant="outline"
            size="xl"
            to="/about"
            class="border-slate-700 hover:border-slate-500 text-slate-300 hover:text-white transition-all duration-200"
          >
            Learn More
          </UButton>
        </div>

        <!-- Stats -->
        <div class="flex gap-8 mt-10 pt-8 border-t border-slate-800">
          <div>
            <p class="text-2xl font-bold text-white">100+</p>
            <p class="text-xs text-slate-500 mt-0.5">Products</p>
          </div>
          <div>
            <p class="text-2xl font-bold text-white">Fast</p>
            <p class="text-xs text-slate-500 mt-0.5">SSR Rendering</p>
          </div>
          <div>
            <p class="text-2xl font-bold text-white">Open</p>
            <p class="text-xs text-slate-500 mt-0.5">Source</p>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>