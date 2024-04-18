<template>
  <--carousel--!>
    <div class="carousel-wrapper">
      <div class="scroll-ml-6 snap-x flex space-x-2">
        <slot/>
      </div>
    </div>
  
  <--grid--!>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-0">
      <slot/>
    </div>

  <--list--!>
    <div class="grid">
      <slot/>
    </div>
  </template>
  
  <script>

  </script>