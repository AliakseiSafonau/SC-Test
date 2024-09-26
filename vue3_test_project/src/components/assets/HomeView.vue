<script setup>

</script>

<template>
  <section class="home text-white vh-100" id="home">
    <div class="container h-100">
      <div class="home__content d-flex flex-column justify-content-center align-items-center h-100">
        <h1 class="fs-1 text-center">Welcome to Test Page</h1>
        <span class="fs-2 text-center">Front-end developer</span>
      </div>
    </div>
  </section>
</template>

<style scoped>
  .home {
    font-family: 'GothicBold';
    background: center / cover no-repeat url('@/assets/images/image.jpg');
  }

  .home__content span {
    font-family: 'GothicRegular';
  }
</style>