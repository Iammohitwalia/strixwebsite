<script setup lang="ts">
import type { NavItem } from '@nuxt/content'

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))

const links = [{
  label: 'About',
  to: '/docs'
}, {
  label: 'Services',
  to: '/docs'
}, {
  label: 'Our Team',
  to: '/docs'
}, {
  label: 'Portfolio',
  to: '/docs'
}, {
  label: 'Gallery',
  to: '/pricing'
}, {
  label: 'Blog',
  to: '/blog'
},
{
  label: 'Contact',
  to: '/docs'
}]
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      Strix Development <UBadge
        label="Pvt. Ltd."
        variant="subtle"
        class="mb-0.5"
      />
    </template>

    <template #right>
      <UButton
        label="Sign in"
        color="gray"
        to="/login"
      />
      <UButton
        label="Sign up"
        icon="i-heroicons-arrow-right-20-solid"
        trailing
        color="black"
        to="/signup"
        class="hidden lg:flex"
      />
    </template>

    <template #panel>
      <UNavigationTree
        :links="mapContentNavigation(navigation)"
        default-open
      />
    </template>
  </UHeader>
</template>
