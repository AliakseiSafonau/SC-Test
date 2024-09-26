<script setup>
import HeaderView from './components/HeaderView.vue';
import FooterView from './components/FooterView.vue';
import AboutView from './components/assets/AboutView.vue';
import ApplicationsView from './components/assets/ApplicationsView.vue';
import ContactView from './components/assets/ContactView.vue';
import EventsView from './components/assets/EventsView.vue';
import FrameworksView from './components/assets/FrameworksView.vue';
import HomeView from './components/assets/HomeView.vue';
import ModalView from './components/ModalView.vue';

import { ref, provide } from 'vue';
const modal = ref(false)
const body = document.querySelector('body')

const updateModalStatus = () => {
  if (modal.value) {
    modal.value = false
    body.classList.toggle('modal-open')
    body.style.overflow = 'auto'
  } else {
    modal.value = true
    body.classList.toggle('modal-open')
    body.style.overflow = 'hidden'
  }
}

provide('modal', updateModalStatus)

</script>

<template>
  <div class="wrapper">
    <ModalView :modal="modal"/> 
    <HeaderView />
    <HomeView />
    <AboutView />
    <FrameworksView />
    <EventsView />
    <ApplicationsView />
    <ContactView />
    <FooterView />
  </div>
</template>

<style scoped>

</style>
