<template>
  <h4
    :class="`h4 ${isUpper && `is-upper`}`"
    v-if="textType === `H4`"
    :style="CssVars"
  >
    {{ text }}
  </h4>
  <small
    :class="`body ${isUpper && `is-upper`}`"
    v-else-if="textType === `SMALL`"
    :style="CssVars"
    >{{ text }}</small
  >
  <p
    :class="`body ${isUpper && `is-upper`}`"
    v-else-if="textType === `BODY`"
    :style="CssVars"
  >
    {{ text }}
  </p>
</template>

<script>
export default {
  name: "TyphographyComponent",
  props: {
    textType: {
      type: String,
      default: "BODY",
    },
    text: String,
    color: {
      type: String,
      default: "#000",
    },
    isUpper: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    CssVars() {
      return {
        color: this.color,
      };
    },
  },
};
</script>

<style scoped lang="scss">
.is-upper {
  text-transform: uppercase;
}
h4 {
  color: var(--color);
}
</style>
