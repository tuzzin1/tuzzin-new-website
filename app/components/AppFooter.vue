<script setup lang="ts">
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
</script>

<template>
   <UFooter :ui="{top: 'border-b border-default py-6 lg:py-8', bottom: 'py-2 lg:py-4'}">
    <!-- ROW 1 : Navigation -->
    <template #top>
      <UContainer>
        <!-- Desktop Navigation -->
        <UNavigationMenu
          :items="items"
          variant="link"
          class="hidden lg:flex justify-center"
        />

        <!-- Mobile Navigation -->
        <UNavigationMenu
          :items="items"
          variant="link"
          orientation="vertical"
          class="lg:hidden w-full"
          :ui="{
            list: 'w-full items-center',
            item: 'w-full flex justify-center',
            link: 'w-full text-center justify-center'
          }"
        />
      </UContainer>
    </template>

    <!-- ROW 2 : Copyright -->
    <template #bottom>
      <UContainer>
        <p class="text-sm text-muted text-center">
          Copyright © 2020–{{ new Date().getFullYear() }}.
          Tuzzin Infotech Pvt. Ltd.
        </p>
      </UContainer>
    </template>
  </UFooter>
  <!-- WhatsApp Widget -->
    <div id="sociocs-c2c" 
        data-channel="918460056525"   
        data-prompt-text="Hello there! Text us here for any questions." 
        data-prompt-profile-pic="https://static.sociocs.com/c2c-prompt-profile-pic.png" 
        data-prompt-delay="1s" 
        style="color-scheme:auto;"
    ></div>
</template>
