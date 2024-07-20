<template>
    <div>
      <h1>Profile</h1>
    </div>
</template>

<script setup>
import { definePage } from 'unplugin-vue-router/runtime'

definePage({
  name: 'Profile',
  meta: {
    title: 'Profile'
  }
})
</script>
