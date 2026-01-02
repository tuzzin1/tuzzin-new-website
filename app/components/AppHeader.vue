<script setup lang="ts">
// const nuxtApp = useNuxtApp()
const { activeHeadings, updateHeadings } = useScrollspy()

const items = computed(() => [{
  label: 'Home',
  to: '/',
  active: activeHeadings.value.includes('/') && !activeHeadings.value.includes('/about')
}, {
  label: 'About',
  to: '/about',
  active: activeHeadings.value.includes('/about')
}, {
  label: 'Solutions',
  to: '/solutions',
  active: activeHeadings.value.includes('/solutions')
}, {
  label: 'News',
  to: '/news',
  active: activeHeadings.value.includes('/news')
}, {
  label: 'Get in touch',
  to: '/getintouch',
  active: activeHeadings.value.includes('/getintouch')
}])

// nuxtApp.hooks.hookOnce('page:finish', () => {
//   updateHeadings([
//     document.querySelector('#features'),
//     document.querySelector('#pricing'),
//     document.querySelector('#testimonials')
//   ].filter(Boolean) as Element[])
// })
</script>

<template>
  <UHeader>
    <template #left>
      <NuxtLink to="/">
        <AppLogo class="w-auto h-8 shrink-0" />
      </NuxtLink>

      <TemplateMenu />
    </template>

    <template #right>
      <UNavigationMenu
        :items="items"
        variant="link"
        class="hidden lg:block px-4"
      />

      <!-- <UButton
        label="Download App"
        variant="subtle"
        class="hidden lg:block"
      /> -->

      <UColorModeButton />
    </template>

    <template #body>
      <UNavigationMenu
        :items="items"
        orientation="vertical"
        class="-mx-2.5"
      />
      <!-- <UButton
        class="mt-4"
        label="Download App"
        variant="subtle"
        block
      /> -->
    </template>
  </UHeader>
</template>
