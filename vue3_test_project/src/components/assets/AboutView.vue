<script setup>

</script>

<template>
  <section class="about py-5" id="about">
    <div class="container">
      <div class="row align-items-center">
        <div class="col d-flex flex-column gap-3">
          <h3>About us</h3>
          <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
            Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
            when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
            It has survived not only five centuries, 
            but also the leap into electronic typesetting, remaining essentially unchanged. 
            It was popularised in the 1960s with the release of Letraset.</p>
          <div class="about__buttons">
            <button class="btn btn-primary" type="button">Read more</button>
            <button class="btn btn-outline-primary" type="button">Contact us</button>
          </div>
        </div>
        <div class="col p-5">
          <div class="ratio ratio-16x9">
            <iframe class="" src="https://www.youtube.com/embed/Upex8hM6wRs" allowfullscreen></iframe>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
    background: linear-gradient(90deg, rgba(0,0,0,0) 0%, rgba(255,255,255,0.95) 0%), 
    center / cover no-repeat url('../../assets/images/vector.jpeg');
  }
</style>