<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
</script>

<template>
  <main p="x4 y10" text="center">
    <div text-4xl>
      <div i-carbon-warning inline-block />
    </div>
    <RouterView />
    <div mt-5>
      <NButton size="small" @click="router.back()">
        Go back
      </NButton>
    </div>
  </main>
</template>
