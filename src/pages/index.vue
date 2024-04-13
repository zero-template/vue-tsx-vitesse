<script setup lang="ts">
import { loadLanguageAsync } from '~/modules/i18n'

defineOptions({
  name: 'IndexPage',
})

const { locale } = useI18n()
const stack = ['Vitesse', 'Vue', 'Naive UI', 'Vite', 'TypeScript']
</script>

<template>
  <div mt-9xl flex flex-col items-center gap-3>
    <div flex>
      <div class="i-carbon-campsite cursor-pointer text-size-5xl text-#63E2B8 transition-all hover:transform-scale-110" />
      <div class="i-simple-icons-vuedotjs cursor-pointer text-size-5xl text-#63E2B8 transition-all hover:transform-scale-110" />
    </div>
    <div flex>
      <div v-for="(item, index) in stack" :key="index">
        <div inline-block>
          {{ item }}
        </div>
        <NDivider v-if="index !== stack.length - 1" vertical />
      </div>
    </div>
    <div>{{ locale === 'zh-CN' ? '世界，你好' : 'Hello world' }}</div>
    <div flex>
      <NButton :type="locale === 'zh-CN' ? 'info' : 'default'" text @click="loadLanguageAsync('zh-CN')">
        ZH
      </NButton>
      <NDivider vertical />
      <NButton :type="locale === 'zh-CN' ? 'default' : 'info'" text @click="loadLanguageAsync('en')">
        EN
      </NButton>
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: default
</route>
