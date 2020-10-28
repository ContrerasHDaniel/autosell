<template>
  <button class="button" @click="onClick()">
    <slot />
  </button>
</template>

<script>
export default {
  name: 'Button',
  methods: {
    onClick() {
      this.$emit('click');
    },
  },
};
</script>

<style lang="scss" scoped>
.button {
  all: unset;
  padding: 10px;
  background-color: var(--application-accent-color);
  color: var(--application-primary-color);
  //text-transform: uppercase;
  cursor: pointer;
}
</style>
