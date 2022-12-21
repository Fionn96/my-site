<script setup lang="ts">
import { isClient } from '~/utils'
import { bilibili, email, site } from '~/meta'

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
    class="z-40 w-full transition-500 h-20 bg-c-bg bg-op-20 dark:bg-op-20 select-none"
    :class="[
      isLeave
        && 'fixed -top-20 left-0 transition-transform duration-500',
      isVisible && 'translate-y-full',
      !isLeave && !isVisible && 'absolute top-0 left-0',
    ]"
  >
    <div class="max-w-120ch m-auto flex justify-between items-center">
      <!--       <router-link
        class="w-20 h-12 m-6 outline-none hover:op-70 transition-opacity" to="/"
      >
        <img v-show="isDark" h-12 src="/logo-dark.svg" alt="logo">
        <img v-show="!isDark" h-12 src="/logo-light.svg" alt="logo">
      </router-link> -->
      <router-link class="box-border p-6 opacity-65 hover-op-100" to="/">
        <span text="lg">hi@fionn</span>
        <div i-fa6-solid:angle-right class="prompt inline-block" />
        <span class="blink">_</span>
      </router-link>

      <nav class="nav box-border p-8 flex items-center space-x-3">
        <router-link to="/posts" title="Blog" class="nav-item">
          <div i-carbon-blog class="md:hidden" />
          <span class="lt-md:hidden">Blog</span>
        </router-link>
        <router-link to="/notes" title="Docs" class="nav-item">
          <div i-iconoir:google-docs class="md:hidden" />
          <span class="lt-md:hidden">Docs</span>
        </router-link>
        <router-link to="/links" title="Links" class="nav-item">
          <div i-carbon:ibm-cloud-direct-link-1-dedicated class="md:hidden" />
          <span class="lt-md:hidden">Links</span>
        </router-link>
        <span class="nav-divider" />

        <a :href="email" target="_blank" title="Email" rel="noreferrer">
          <div i-mdi:email-outline />
        </a>
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
