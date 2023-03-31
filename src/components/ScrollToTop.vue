<script setup lang="ts">
const { y } = useWindowScroll()
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
const scrollToBottom = () => {
  const pageHeight = document.documentElement.scrollHeight
  window.scrollTo({ top: pageHeight, behavior: 'smooth' })
}
</script>

<template>
  <Transition>
    <button
      v-show="y > 500" i-carbon:chevron-up
      box-border
      opacity-45
      hover-op-100
      w-6
      h-6
      text-sm
      rd-full
      fixed
      bottom-8
      right-16
      select-none
      @click="scrollToTop()"
    />
  </Transition>
  <Transition>
    <button
      v-show="y > 500"
      i-carbon:chevron-down
      box-border
      opacity-45
      hover-op-100
      w-6
      h-6
      text-sm
      rd-full
      fixed
      bottom-8
      right-8
      select-none
      @click="scrollToBottom()"
    />
  </Transition>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: all 1s ease;
}

.v-enter-from,
.v-leave-to {
  transform: translateY(100px);
}
</style>
