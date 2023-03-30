<script setup lang="ts">
const loadState = ref('')
onMounted(() => {
  const avatar = new Image()
  avatar.src = '/favicon/home-favicon.png'
  avatar.onload = () => loadState.value = 'loaded'
  avatar.onerror = () => loadState.value = 'unload'
})
</script>

<template>
  <div flex items-end justify-between lt-sm="flex-col-reverse items-start gap-3">
    <div>
      <h1 class="text-linear">
        <slot />
      </h1>
    </div>
    <div
      class="w-35 h-35 border rounded-full overflow-hidden z-1 flex justify-center items-center"
      :class="{ 'op-0': loadState === 'unload' }"
      shadow="slate-200 dark:slate-800"
      style="display: flex; justify-content: center; align-items: center; margin: auto;"
    >
      <img
        alt="avatar"
        width="100"
        height="100"
        class="m-0! not-zoom avatar"
        :class="{ loaded: loadState === 'loaded' }"
        :src="loadState === 'loaded' ? '/favicon/home-favicon.png' : ''"
        style="margin: auto;"
      >
    </div>
  </div>
</template>

<style scoped>
.text-linear {
  background: #6d6d6d;
  -webkit-text-fill-color: transparent;
  --at-apply: bg-clip-text;
}

.avatar.loaded{
  opacity: 1;
  transform: scale(1.5);
  filter: blur(0);
}

.avatar{
  opacity: 0;
  transform: scale(3);
  filter: blur(8px);
  transition: 1s ease;
  transition-property: filter,opacity,transform;
  will-change: filter,transform;
  margin: auto;
}
</style>
