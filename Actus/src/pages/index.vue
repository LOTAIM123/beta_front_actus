<template>
  <q-layout view="hHh lpR fFf">
    <ActusHeader />

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import ActusHeader from '@/components/ActusHeader.vue'
</script>
