<script setup>
import { reactive, inject } from 'vue';
import axios from 'axios';
import inputsList from '@/data/contacts';
import useVuelidate from '@vuelidate/core';
import { required, email, minLength, alpha, numeric, maxLength} from '@vuelidate/validators';


const updateModalStatus = inject('modal')


const dataV = reactive({
  firstName: '',
  lastName: '',
  company: '',
  email: '',
  jobTitle: '',
  country: '',
  state: '',
  zipCode: '',
})

const rules = { 
  firstName: {
    required: required,
    alpha: alpha,
    minLength: minLength(3),
    maxLength: maxLength(25)
  },
  lastName: {
    required: required,
    alpha: alpha,
    minLength: minLength(3),
    maxLength: maxLength(25)
  },
  company: {
    required: required,
    alpha: alpha,
    minLength: minLength(3),
    maxLength: maxLength(25)
  },
  email: {
    required: required,
    email: email
  },
  jobTitle: {
    required: required,
    alpha: alpha,
    minLength: minLength(3),
    maxLength: maxLength(25)
  },
  country: {
    alpha: alpha,
    minLength: minLength(3),
    maxLength: maxLength(25)
  },
  state: {
    alpha: alpha,
    required: required,
    minLength: minLength(3)
  },
  zipCode: {
    required: required,
    numeric: numeric,
    minLength: minLength(6),
    maxLength: maxLength(6)
  },
}

const resetForm = () => {
  dataV.company = ''
  dataV.country = ''
  dataV.email = ''
  dataV.firstName = ''
  dataV.jobTitle = ''
  dataV.lastName = ''
  dataV.state = ''
  dataV.zipCode = ''
}

const v = useVuelidate(rules, dataV)

const checkForm = () => {
  v.value.$touch();
  if (v.value.$pending || v.value.$error || !v.value.$dirty) return;

  axios.get('https://jsonplaceholder.typicode.com/todos/1')
  .then((response) => {
    updateModalStatus()
    const timer = setTimeout(() => {
      updateModalStatus()
      clearTimeout(timer)
    }, 3000)
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error);
  });

  v.value.$reset();
  resetForm();
}
</script>

<template>
  <section class="contact py-5" id="contact">
    <div class="container">
      <div class="contact__content d-flex flex-column align-items-center">
        <h2>Contact Us</h2>
        <form @submit.prevent="checkForm" class="form d-flex flex-column align-items-center pt-5 needs-validation" novalidate>
          <div class="form__inputs row row-cols-1 row-cols-md-4 g-2">
            <div
              class="mb-3"
              v-for="item in inputsList"
              :key="item.id">
              <label :for="item.forId" class="form-label">{{item.label}}</label>
              <input
                :type="item.type"
                class="form-control bg-secondary"
                :class="v[item.forId].$errors[0] ? 'is-invalid' : 'border-0'"
                :id="item.forId"
                :placeholder="item.placeholder"
                :required="item.required"
                v-model.trim="v[item.forId].$model"
                @blur="v[item.forId].$touch()"
              >
              <div v-if="v[item.forId].$errors[0]" class="invalid-feedback position-absolute">
                {{v[item.forId].$errors[0].$message}}
              </div>
            </div>
          </div>
          <button type="submit" class="btn btn-primary lg-5">Submit</button>
        </form>
      </div>
    </div>
  </section>
</template>

<style>
.invalid-feedback {
  width: min-content;
}
</style>