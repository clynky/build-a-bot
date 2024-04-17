<!-- eslint-disable no-shadow -->
<template>
  <div>
    <h1>{{ part.title }}</h1>
    <div>
      {{ part.description }}
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue';

import { usePartsStore } from '../stores/partsStore';

const partsStore = usePartsStore();

const props = defineProps(['partType', 'id']);
// eslint-disable-next-line no-shadow
const part = computed(() => partsStore.parts[props.partType].find((part) => part.id === +props.id));
</script>
