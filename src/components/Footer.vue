<script setup lang="ts">
// import { author, email, site } from '~/meta'
</script>

<template>
  <footer
    class="flex items-center flex-col-reverse sm:flex-row lt-sm:gap-4 text-4 my-10 justify-between"
  >
    <div class="op-50 text-sm">
      ©
      <a
        class="item"
        target="_blank"
        href="mailto:fyx2500253355@gmail.com"
      >Fionn</a>
      {{ new Date().getFullYear() }}. Build with
      <a
        class="item"
        target="_blank"
        href="https://github.com/antfu/vitesse"
      >Vitesse</a>
      &
      <a
        class="item"
        target="_blank"
        href="https://github.com/Zhengqbbb/qbb.sh"
      >QB Template</a>
      .
    </div>
  </footer>
</template>

<style scoped>
footer a.item{
  --at-apply: pb-0.3 border-b border-transparent hover:border-c-fg transition-border-color-300;
}
</style>
