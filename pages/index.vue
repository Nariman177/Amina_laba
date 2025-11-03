<template>
  <div>
    <header class="flex flex-row w-full p-4 bg-blue-100 shadow-md">
      <div class="basis-1/4 flex items-center justify-start">
        <img src="/rose.png" class="w-16 h-16 rounded" alt="Logo">
      </div>
      <div class="basis-1/4"></div>
      <div class="basis-1/2 flex items-center justify-end">
        <nav class="flex flex-row gap-4">
          <NuxtLink to="/" class="p-2 bg-blue-500 text-white rounded hover:bg-blue-700">Home</NuxtLink>
          <NuxtLink to="/Lab3" class="p-2 bg-green-500 text-white rounded hover:bg-green-700">Lab3</NuxtLink>
          <a href="#" class="p-2 bg-yellow-500 text-white rounded hover:bg-yellow-700">LogIn</a>
          <a href="#" class="p-2 bg-red-500 text-white rounded hover:bg-red-700">LogOut</a>
        </nav>
      </div>
    </header>
    
    <main class="p-8 bg-gray-50 min-h-screen">
      <h1 class="text-4xl font-bold text-blue-800 mb-4">Welcome to my Nuxt.js Project!</h1>
      <p class="text-lg text-gray-700 mb-6">This is my custom designed home page for the web design lab.</p>
      
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-8">
        <div class="bg-white p-6 rounded-lg shadow-md">
          <h2 class="text-2xl font-semibold text-green-700 mb-3">About This Project</h2>
          <p class="text-gray-600">This project demonstrates the use of Nuxt.js with Tailwind CSS for modern web development.</p>
        </div>
        
        <div class="bg-white p-6 rounded-lg shadow-md">
          <h2 class="text-2xl font-semibold text-purple-700 mb-3">Features</h2>
          <ul class="list-disc list-inside text-gray-600">
            <li>Responsive Navigation</li>
            <li>Tailwind CSS Styling</li>
            <li>Vue.js Components</li>
          </ul>
        </div>
      </div>
    </main>
  </div>
</template>