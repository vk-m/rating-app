<template>
  <div v-if="isOpen" class="modal-overlay">
    <div class="modal">
      <h2>Надіслати повідомлення</h2>
      <form @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="message">Повідомлення:</label>
          <textarea id="message" v-model="message" required></textarea>
        </div>
        <div class="form-actions">
          <button type="submit" class="btn btn-primary">Надіслати</button>
          <button type="button" class="btn btn-secondary" @click="closeModal">Закрити</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

defineProps({
  isOpen: {
    type: Boolean,
    required: true,
  },
});

const emit = defineEmits(['close', 'submit']);

const message = ref('');

const closeModal = () => {
  emit('close');
};

const handleSubmit = () => {
  emit('submit', message.value);
  message.value = '';
  closeModal();
};
</script>

<style scoped lang="scss">
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  width: 400px;
  max-width: 90%;

  .form-group {
    display: flex;
    align-items: center;
    justify-content: space-around;
  }

  ;

  .form-actions {
    margin-top: 20px;
  }

  input[type="text"],
  select,
  textarea {
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    margin-top: 6px;
    margin-bottom: 10px;
    align-content: center;
    padding: 0 10px;
  }
}
</style>