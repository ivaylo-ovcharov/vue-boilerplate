<script setup>
const { fetchPlanet } = usePlanetLoader

const props = defineProps({
  selectedPersonId: { type: Number, required: true },
})

const planet = fetchPlanet(selectedPersonId)
</script>
<template>
  <SwModal title="Selected user name's modal">
    <p>Planet name: {{ planet.name }}</p>
    <p>Planet mass: {{ planet.mass }}</p>
    <SwButton variant="primary" @click="emit('close')">Got it</SwButton>
  </SwModal>
</template>
