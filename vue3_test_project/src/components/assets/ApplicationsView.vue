<script setup>
import applicationsList from '@/data/applications';

</script>

<template>
  <section class="applications py-5 bg-secondary" id="applications">
    <div class="container">
      <div class="applications__content d-flex flex-column align-items-center">
        <h2>Applications</h2>
        <div class="applications-app w-100 pt-5">
          <div class="applications__cards row row-cols-1 row-cols-md-4 g-6">
            <div class="applications__card col" v-for="item in applicationsList" :key="item.id">
              <div class="applications__card__content card ratio ratio-4x3">
                <div class="applications__card__img"></div>
              </div>
            </div>
          </div>
        </div>  
      </div>
    </div>
  </section>
</template>

<style scoped>

.applications__card__content {
  position: relative;
}

.applications__card__content::after {
  content: 'app1';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 25%;
  background-color: black;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
}

.applications__card:nth-child(1) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image111.png');
}

.applications__card:nth-child(2) .applications__card__content::after {
  content: 'app2';
}

.applications__card:nth-child(3) .applications__card__content::after {
  content: 'app3';
}

.applications__card:nth-child(4) .applications__card__content::after {
  content: 'app4';
}

.applications__card:nth-child(5) .applications__card__content::after {
  content: 'app5';
}

.applications__card:nth-child(6) .applications__card__content::after {
  content: 'app6';
}

.applications__card:nth-child(7) .applications__card__content::after {
  content: 'app7';
}

.applications__card:nth-child(8) .applications__card__content::after {
  content: 'app8';
}

.applications__card:nth-child(2) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image112.png');
}

.applications__card:nth-child(3) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image113.png');
}

.applications__card:nth-child(4) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image114.png');
}

.applications__card:nth-child(5) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image115.png');
}

.applications__card:nth-child(6) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image116.png');
}

.applications__card:nth-child(7) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image117.png');
}

.applications__card:nth-child(8) .applications__card__content {
  background: center / cover no-repeat url('../../assets/images/image118.png');
}
</style>