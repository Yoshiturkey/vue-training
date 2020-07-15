<template>
  <component :is="HeadComponent">
    <slot></slot>
  </component>
</template>
<script>
import Heading1 from "./Heading1";
import Heading2 from "./Heading2";
import Heading3 from "./Heading3";
export default {
  props: {
    scale: {
      type: Number,
      default: 1,
      validator(value) {
        return value < 6 && value !== 0;
      },
    },
  },
  components: {
    head1: Heading1,
    head2: Heading2,
    head3: Heading3,
  },
  computed: {
    HeadComponent() {
      return `head${this.scale}`;
    },
  },
};
</script>
