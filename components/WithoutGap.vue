<template>
  <div class="px-12 py-1.25">
    <div class="wrapper border-2 border-white rounded relative">
      <span class="absolute -top-1 right-1 text-sm text-amber-500">.grid</span>
      <div class="border-2 border-white rounded">
        <div class="item border-2 aspect-square grid place-items-center border-white/50 rounded">1</div>
      </div>
      <div class="border-2 border-white rounded">
        <div class="item border-2 aspect-square grid place-items-center border-white/50 rounded">2</div>
      </div>
      <div class="border-2 border-white rounded relative">
        <span class="absolute -top-.5 right-1 text-sm text-amber-500">.item</span>
        <div class="item border-2 aspect-square grid place-items-center border-white/50 rounded">3</div>
      </div>
    </div>

    <p>Thankfully we don't have to support IE11 anymore!</p>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-wrap: wrap;
  margin-inline: -2rem;
  padding: 1rem;

  &>div {
    flex: 1;
    padding: 1rem;

    .item {
      @apply bg-indigo-500;
      padding: 1rem;
      text-align: center;
    }
  }

}

p {
  text-wrap: balance;
}
</style>
