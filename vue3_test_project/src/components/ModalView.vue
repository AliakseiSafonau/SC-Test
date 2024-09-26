<script setup>

const props = defineProps(['modal'])

</script>

<template>
  <div class="modal fade show bg-" tabindex="-1" :style="{'display': props.modal ? 'block' : 'none'}">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Attempt to send data</h5>
        </div>
        <div class="modal-body">
          <p>Form successfully sent!</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
  .modal {
    background-color: rgba(0, 0, 0, 0.7);
  }
</style>