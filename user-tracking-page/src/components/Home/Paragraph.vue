<template>
  <p>{{ index }}. {{ paragraphText }}</p>
</template>

<script lang="ts" setup>
import { paragraphText } from './consts';
const props = defineProps({
  index: Number,
});
</script>
