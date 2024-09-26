<script setup>
import frameworksList from '@/data/frameworks';
</script>

<template>
  <section class="frameworks bg-secondary py-5" id="frameworks">
    <div class="container">
      <div class="frameworks__content d-flex flex-column align-items-center">
        <h3>Frameworks</h3>
        <div class="frameworks__list-items">
          <div 
            class="frameworks__item mb-3 bg-white rounded"
            v-for="(item, index) in frameworksList"
            :key="item.id">
            <div  class="row" :class="[(index % 2) !== 0 ? 'flex-row-reverse' : '']">
              <div class="framework__image col-md-5 d-flex align-items-center">
                <img 
                  class="img-fluid rounded-start"
                  :src="item.image"
                  :alt="item.alt">
              </div>
              <div class="frameworks__about col-md-7 d-flex flex-column py-4 ps-3">
                <h4>{{ item.title }}</h4>
                <p>{{ item.text }}</p>
                <div class="buttons mt-auto">
                  <button class="btn btn-primary" type="button">Read more</button>
                  <button class="btn btn-outline-primary" type="button">Webinar</button>
                </div>
              </div>
            </div>
          </div>
        </div>  
      </div>
    </div>
  </section>
</template>

<style>
.frameworks__item:nth-child(1) .framework__image {
  background: center / cover no-repeat url('../../assets/images/image2.jpg');
}

.frameworks__item:nth-child(2) .framework__image {
  background: center / cover no-repeat url('../../assets/images/image1.jpg');
}

.frameworks__item:nth-child(3) .framework__image {
  background: center / cover no-repeat url('../../assets/images/image3.jpg');
}
</style>