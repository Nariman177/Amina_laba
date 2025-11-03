<template>
  <div>
    <!-- 头部 -->
    <header class="flex flex-row w-full p-4 bg-green-100 border-b border-green-300 justify-between items-center">
      <!-- Logo -->
      <div class="basis-1/4 max-sm:basis-auto flex items-center justify-start">
        <img src="/rose.png" class="w-16 h-16 bg-transparent" alt="Logo">
      </div>
      
      <!-- 空占位 -->
      <div class="basis-1/4 max-sm:hidden"></div>
      
      <!-- 汉堡菜单按钮 (只在移动端显示) -->
      <div class="hidden max-sm:block" @click="switch_burger">
        <div v-if="!burger" class="space-y-1 cursor-pointer">
          <div class="w-6 h-0.5 bg-gray-600"></div>
          <div class="w-6 h-0.5 bg-gray-600"></div>
          <div class="w-6 h-0.5 bg-gray-600"></div>
        </div>
        <div v-else class="cursor-pointer">
          <div class="w-6 h-0.5 bg-gray-600 rotate-45 translate-y-0.5"></div>
          <div class="w-6 h-0.5 bg-gray-600 -rotate-45 -translate-y-0.5"></div>
        </div>
      </div>

      <!-- 导航菜单 (桌面端) -->
      <div class="basis-1/2 max-sm:hidden flex items-center justify-end">
        <nav class="flex flex-row gap-4 items-center">
          <NuxtLink to="/" class="p-2 hover:bg-green-500 hover:text-white rounded">Home</NuxtLink>
          
          <!-- Labs 下拉菜单 -->
          <div class="relative">
            <button 
              @click="switch_labs" 
              class="p-2 hover:bg-green-500 hover:text-white rounded flex items-center"
            >
              Labs
              <svg class="w-4 h-4 ml-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
              </svg>
            </button>
            
            <!-- 子菜单 -->
            <div v-show="labsOpen" class="absolute top-full left-0 mt-1 bg-white shadow-lg rounded border min-w-32">
              <NuxtLink to="/Lab3" class="block p-2 hover:bg-green-100">Lab 3</NuxtLink>
              <NuxtLink to="/Lab4" class="block p-2 hover:bg-green-100">Lab 4</NuxtLink>
              <NuxtLink to="/Lab5" class="block p-2 hover:bg-green-100">Lab 5</NuxtLink>
              <NuxtLink to="/Lab6" class="block p-2 hover:bg-green-100">Lab 6</NuxtLink>
            </div>
          </div>
          
          <NuxtLink to="/login" class="p-2 hover:bg-green-500 hover:text-white rounded">LogIn</NuxtLink>
          <NuxtLink to="/logout" class="p-2 hover:bg-green-500 hover:text-white rounded">LogOut</NuxtLink>
        </nav>
      </div>
    </header>

    <!-- 移动端导航菜单 -->
    <div 
      :class="[
        'max-sm:bg-white max-sm:border-b max-sm:border-gray-200 max-sm:transition-all max-sm:duration-300',
        burger ? 'max-sm:max-h-64 max-sm:py-4' : 'max-sm:max-h-0 max-sm:overflow-hidden'
      ]"
    >
      <nav class="hidden max-sm:flex flex-col items-center gap-2 px-4">
        <NuxtLink to="/" class="w-full text-center p-2 hover:bg-green-100 border-b">Home</NuxtLink>
        
        <!-- 移动端 Labs 菜单 -->
        <div class="w-full">
          <button 
            @click="switch_labs_mobile" 
            class="w-full p-2 hover:bg-green-100 border-b flex justify-between items-center"
          >
            Labs
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
            </svg>
          </button>
          
          <div v-show="labsOpenMobile" class="bg-gray-50">
            <NuxtLink to="/Lab3" class="block p-2 pl-6 hover:bg-green-100 border-b">Lab 3</NuxtLink>
            <NuxtLink to="/Lab4" class="block p-2 pl-6 hover:bg-green-100 border-b">Lab 4</NuxtLink>
            <NuxtLink to="/Lab5" class="block p-2 pl-6 hover:bg-green-100 border-b">Lab 5</NuxtLink>
            <NuxtLink to="/Lab6" class="block p-2 pl-6 hover:bg-green-100 border-b">Lab 6</NuxtLink>
          </div>
        </div>
        
        <NuxtLink to="/login" class="w-full text-center p-2 hover:bg-green-100 border-b">LogIn</NuxtLink>
        <NuxtLink to="/logout" class="w-full text-center p-2 hover:bg-green-100 border-b">LogOut</NuxtLink>
      </nav>
    </div>

    <!-- 页面内容 -->
    <main class="p-8 bg-gray-50 min-h-screen">
      <slot />
    </main>
  </div>
</template>

<script setup>
// 响应式数据
const burger = ref(false) // 汉堡菜单状态
const labsOpen = ref(false) // 桌面端 Labs 菜单状态
const labsOpenMobile = ref(false) // 移动端 Labs 菜单状态

// 切换汉堡菜单
const switch_burger = () => {
  burger.value = !burger.value
}

// 切换桌面端 Labs 菜单
const switch_labs = () => {
  labsOpen.value = !labsOpen.value
}

// 切换移动端 Labs 菜单
const switch_labs_mobile = () => {
  labsOpenMobile.value = !labsOpenMobile.value
}

// Google Analytics 代码
useHead({
  script: [
    {
      async: true,
      src: 'https://www.googletagmanager.com/gtag/js?id=G-QYTN9QYRG0'
    },
    {
      innerHTML: `
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'G-QYTN9QYRG0');
      `
    }
  ]
})
</script>