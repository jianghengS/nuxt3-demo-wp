<script lang="ts" setup>
defineProps<{
  title: string
  image: string
  excerpt?: string
  slug: string
}>()
</script>
<template>
  <div class="col-span-1 shadow-lg group">
    <!-- Blog Image -->
    <div v-if="image" class="w-full h-[180px] relative overflow-hidden">
      <img
        :src="image"
        alt=""
        class="w-full h-full absolute object-cover group-hover:scale-125 duration-200"
      />
    </div>
    <!-- Blog Contents -->
    <div class="p-5">
      <h3 class="text-xl font-semibold mb-3" v-html="title"></h3>
      <p v-if="excerpt" class="text-sm mb-3" v-html="excerpt"></p>
      <NuxtLink
        :to="`/${slug}`"
        class="inline-flex items-center border-b-2 border-blue-500"
      >
        Read More
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-4 h-4 ml-1 group-hover:ml-2 duration-200"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4.5 12h15m0 0l-6.75-6.75M19.5 12l-6.75 6.75"
          ></path>
        </svg>
      </NuxtLink>
    </div>
  </div>
</template>
