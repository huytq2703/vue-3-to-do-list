<script setup lang="ts">
import type { PropType } from 'vue';

type ButtonTypes = 'button' | 'submit' | 'reset' | undefined;

defineProps({
  type: {
    type: String as PropType<ButtonTypes>,
    required: false,
    default: 'button',
    validator: (value: string) => {
      const buttonTypes = ['button', 'submit', 'reset'];
      return buttonTypes.includes(value);
    },
  },
});
</script>

<template>
  <button class="tqh-button" :type="type">
    <slot />
  </button>
</template>
