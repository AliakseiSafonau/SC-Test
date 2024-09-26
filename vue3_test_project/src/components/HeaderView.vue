<script setup>
import headerNavList from '@/data/navigation';
import { provide, ref } from 'vue';

const checked = ref('false')

provide('radio', checked)

</script>

<template>
  <header class="header bg-white position-fixed z-1 top-0 start-0 w-100">
    <div class="header__container container">
      <div class="header__content d-flex justify-content-between align-items-center py-2">
        <a href="/" class="header__logo navbar-brand">
          <img src="../assets/images/logo-general.svg" alt="Success Craft">
        </a>
        <nav class="header__nav navbar navbar-expand-lg">
          <div class="header__nav-content container-fluid">
            <div class="collapse navbar-collapse">
              <ul class="header__nav-items navbar-nav gap-3 fs-6">
                <li 
                  class="header__nav-item nav-item" 
                  v-for="item in headerNavList"
                  :key="item.id">
                  <a 
                    class="header__nav-link nav-link" :href="item.href">{{ item.title }}</a>
                </li>
              </ul>
            </div>
            <div class="header__burger-menu navbar-toggler" data-bs-toggle="collapse">
              <label class="header__burger-toggler" for="header-burger">
                <span class="navbar-toggler-icon"></span>
                <input 
                  class="header__burger-checbox position-absolute invisible" 
                  type="checkbox" 
                  name="header-burger" 
                  id="header-burger"
                  v-model="checked">
              </label>
            </div>
          </div>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
  .header {
    font-family: 'RobotoRegular';
  }
</style>
