<template>
  <button
    :class="['base-button', variantClass]"
    :type="type"
    @click="$emit('click', $event)"
  >
    <slot />
  </button>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  type: {
    type: String,
    default: 'button',
  },
  variant: {
    type: String,
    default: 'primary', // primary | secondary | danger
  },
})

const variantClass = computed(() => {
  return {
    primary: 'btn-primary',
    secondary: 'btn-secondary',
    danger: 'btn-danger',
  }[props.variant]
})
</script>

<style scoped>
.base-button {
  padding: 0.5rem 1rem;
  border-radius: 6px;
  font-weight: 500;
  transition: background-color 0.2s ease;
  border: none;
  cursor: pointer;
}

/* Variantes */
.btn-primary {
  background-color: #3b82f6;
  color: white;
}
.btn-primary:hover {
  background-color: #2563eb;
}

.btn-secondary {
  background-color: #e5e7eb;
  color: #111827;
}
.btn-secondary:hover {
  background-color: #d1d5db;
}

.btn-danger {
  background-color: #ef4444;
  color: white;
}
.btn-danger:hover {
  background-color: #dc2626;
}
</style>
