<template>
  <header class="flex justify-between border-b border-slate-200 px-10 py-8">
    <div class="flex items-center gap-4">
      <img src="/public/logo.png" alt="Logo" class="w-10" />

      <div>
        <h2 class="text-xl font-bold uppercase">vue sneakers</h2>
        <p class="text-slate-400">Магазин лучших кроссовок</p>
      </div>
    </div>
    <ul class="flex items-center gap-10">
      <li class="flex items-center gap-3 text-gray-300 hover:text-black cursor-pointer">
        <img src="/public/cart.svg" alt="" />
        <b>1285$</b>
      </li>
      <li class="flex items-center gap-3 text-gray-300 hover:text-black cursor-pointer">
        <img src="/public/heart.svg" alt="" />
        <span>закладки</span>
      </li>
      <li class="flex items-center gap-3 text-gray-300 hover:text-black cursor-pointer">
        <img src="/public/profile.svg" alt="" />
        <span>профиль </span>
      </li>
    </ul>
  </header>
</template>
