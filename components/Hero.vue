<template>
  <motion.div
    class="flex flex-col justify-start pt-10 mt-5 mb-36"
    :initial="{ opacity: 0, scale: 0 }"
    :animate="{ opacity: 1, scale: 1 }"
    :transition="{
      duration: 0.5,
      scale: { type: 'spring', visualDuration: 0.5, bounce: 0.5 },
    }"
  >
    <div class="flex flex-col items-center lg:px-16">
      <div class="flex items-center gap-2 text-sm">
        <NuxtLink to="https://github.com/sersi-project/sersi/releases/tag/v0.0.0-alpha"><div class="text-center p-1 px-2 border border-gray-700 rounded-full text-xs">v0.0.0-alpha</div></NuxtLink>    
        <code
          >powered by
          <NuxtLink to="https://vitejs.dev/" target="_blank" class="underline"
            >vite</NuxtLink
          ></code
        >
        <UIcon name="i-devicon-vitejs" class="size-4" />
        
      </div>
      <h1
        class="text-[3.5rem] lg:text-[4rem] xl:text-[5.5rem] font-bold tracking-tight text-center leading-tight"
      >
        Kickstart modern apps in seconds. Your
        <span class="whitespace-nowrap text-purplish">stacks</span>, your
        <span class="text-primary">rules</span>.
      </h1>
    </div>
    <div
      class="flex flex-col lg:flex-row lg:space-x-5 space-y-5 lg:space-y-0 justify-center items-center my-10 font-bold"
    >
      <NuxtLink to="/docs">
        <UButton
          leading-icon="i-lucide-book-open"
          size="lg"
          :class="mode.value === 'dark' ? 'bg-white' : 'bg-black'"
          :ui="{
            base: 'w-52 h-16 text-xl justify-center ',
          }"
        >
          Documentation
        </UButton>
      </NuxtLink>

      <NuxtLink to="https://github.com/sersi-project" target="_blank">
        <UButton
          trailing-icon="i-lucide-github"
          size="lg"
          :class="mode.value === 'dark' ? 'bg-white' : 'bg-black'"
          :ui="{
            base: 'text-xl w-52 lg:w-36 justify-center h-16',
          }"
        >
          Github
        </UButton>
      </NuxtLink>
    </div>
    <DependencyLabel command="create" />
  </motion.div>
</template>

<script lang="ts" setup>
import { motion } from 'motion-v';

const mode = useColorMode();
</script>
