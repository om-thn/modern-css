<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    user: string;
    id: string;
    height?: string;
  }>(),
  {
    height: '550',
  },
);
</script>

<template>
  <iframe
    :height="props.height"
    style="width: 100%;"
    title="Codepen"
    :src="`https://codepen.io/${props.user}/embed/${props.id}?default-tab=result&editable=true`"
    loading="lazy"
    allowfullscreen="true"
  />
</template>