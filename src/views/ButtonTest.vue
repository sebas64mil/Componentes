<template>
  <div>
    <BaseButton @click="handleClick">Guardar</BaseButton>
    <BaseButton variant="secondary">Cancelar</BaseButton>
    <BaseButton variant="danger">Eliminar</BaseButton>
  </div>
</template>

<script setup>
const handleClick = () => {
  alert('Botón presionado')
}
</script>