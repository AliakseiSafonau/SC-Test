<script setup>
import { eventsList } from '@/data/events';
</script>

<template>
  <section class="events" id="events">
    <div class="container">
      <div class="events__content row">
        <div 
          class="events__card col"
          v-for="item in eventsList"
          :key="item.id">
          <div class="row">
            <div class="events__img col">
              <img :src="item.image" :alt="item.alt">
            </div>
            <div class="events__discription col">
              <h3>{{ item.title }}</h3>
              <p>{{ item.text }}</p>
              <button class="btn btn-primary">{{ item.button }}</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
.events__card:nth-child(1) .events__img {
  background: center / cover no-repeat url('../../assets/images/image11.jpg');
}

.events__card:nth-child(2) .events__img {
  background: center / cover no-repeat url('../../assets/images/image12.jpg');
}
</style>