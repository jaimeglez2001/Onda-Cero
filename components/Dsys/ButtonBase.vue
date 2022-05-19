<template>
  <button :class="classes">
    <slot />
  </button>
</template>

<script>
export default {
  props: {
      size: {type: String, default: "md"}, 
      context: {type: String, default: "primary"}
  },
  computed: {
    classes() {
      return {
        button_xl: this.size == "xl",
        button_sm: this.size == "sm",
        button_primary: this.context == "primary",
        button_secondary: this.context == "secondary",
      };
    },
  },
};
</script>

<style lang="postcss">
button {
  @apply bg-gray-500 text-white px-4 py-2 rounded-full;
}
button.button_xl {
  @apply px-8 py-4 text-xl;
}
button.button_sm {
  @apply text-sm;
}
button.button_primary {
  @apply bg-green-500;
}
button.button_secondary {
  @apply bg-purple-500;
}
</style>