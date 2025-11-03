<template>
  <div class="max-w-md mx-auto">
    <h1 class="text-4xl font-bold text-yellow-800 mb-4">Login</h1>
    <div class="bg-white p-6 rounded-lg shadow-md">
      <form>
        <div class="mb-4">
          <label class="block text-gray-700 mb-2">Email</label>
          <input type="email" class="w-full p-2 border border-gray-300 rounded">
        </div>
        <div class="mb-4">
          <label class="block text-gray-700 mb-2">Password</label>
          <input type="password" class="w-full p-2 border border-gray-300 rounded">
        </div>
        <button type="submit" class="w-full bg-yellow-500 text-white p-2 rounded hover:bg-yellow-700">
          Login
        </button>
      </form>
    </div>
  </div>
</template>