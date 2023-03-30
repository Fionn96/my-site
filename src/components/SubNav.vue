<script setup lang="ts">
import { useRoute } from 'vue-router'

const inactiveStyle = 'opacity-20 hover:opacity-50'

const route = useRoute()
</script>

<template>
  <div class="prose m-auto mb-8 select-none">
    <div mb-0 flex="~ gap2 sm:gap3 wrap" text-xl sm:text-4xl>
      <router-link to="/notes" class="!border-none !font-800" :class="route.path.indexOf('/notes') !== -1 ? '' : inactiveStyle">
        Notes
      </router-link>
      <router-link to="/lifestyle" class="!border-none !font-800" :class="route.path.indexOf('/lifestyle') !== -1 ? '' : inactiveStyle">
        LifeStyle
      </router-link>
      <router-link to="/games" class="!border-none !font-800" :class="route.path.indexOf('/games') !== -1 ? '' : inactiveStyle">
        Games
      </router-link>
    </div>
  </div>
</template>
