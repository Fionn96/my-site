<script setup lang="ts">
import { isClient } from '~/utils'
import { bilibili, site } from '~/meta'

const navbar = ref<HTMLElement | null>(null)
const isLeave = ref(false)
const isVisible = ref(false)

if (isClient) {
  const { y, directions } = useScroll(document)

  watch(y, () => {
    if (directions.top) {
      // scrolling up
      if (y.value > 0 && isLeave.value) {
        isVisible.value = true
      }
      else {
        isVisible.value = false
        isLeave.value = false
      }
    }
    else if (directions.bottom) {
      // scrolling down
      isVisible.value = false
      if (navbar.value && y.value > navbar.value!.offsetHeight)
        isLeave.value = true
    }
  })
}
</script>

<template>
  <header
    ref="navbar"
    class="z-40 w-full transition-500 h-20 bg-c-bg bg-op-0 dark:bg-op-0 select-none"
    :class="[
      isLeave
        && 'fixed -top-20 left-0 transition-transform duration-500',
      isVisible && 'translate-y-full',
      !isLeave && !isVisible && 'absolute top-0 left-0',
    ]"
  >
    <div class="max-w-120ch m-auto flex justify-between items-center">
      <router-link class="box-border p-6 opacity-65 hover-op-100" to="/">
        <span text="lg">hi@fionn</span>
        <div i-fa6-solid:angle-right class="prompt inline-block" />
        <span class="blink">_</span>
      </router-link>

      <nav class="nav box-border p-8 flex items-center space-x-3">
        <a href="/posts" title="Posts" class="nav-item">
          <div i-carbon-blog />
        </a>
        <a href="/notes" title="Notes" class="nav-item">
          <div i-ph:pencil-simple-line-duotone />
        </a>
        <a href="/links" title="Links" class="nav-item">
          <div i-carbon-delivery-parcel />
        </a>
        <span class="nav-divider" />
        <a :href="bilibili" target="_blank" title="Bilibili" rel="noreferrer">
          <div i-ri:bilibili-line />
        </a>
        <a :href="`${site}/feed.xml`" target="_blank" title="RSS">
          <div i-ri:rss-line />
        </a>
        <span class="nav-divider" />
        <button title="Toggle Color Scheme" @click="toggleDark()">
          <div i="ri-sun-line dark:ri-moon-line" />
        </button>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.nav a,
.nav button{
  cursor: pointer;
  text-decoration: none;
  color: inherit;
  transition: opacity 0.2s ease;
  opacity: 0.6;
  outline: none;
}

.nav a:hover,
.nav button:hover{
  opacity: 1;
  text-decoration-color: inherit;
}
@keyframes blinker {
  50% {
    opacity: 0;
  }
}
.prompt {
  vertical-align: -0.2em;
  font-size: 0.85em;
}
.blink {
  animation: blinker 1s none infinite;
}
</style>
