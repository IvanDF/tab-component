<template>
  <div class="tab-component" :style="CssVars">
    <ul class="header-tabs">
      <li
        v-for="(el, i) in infoList"
        :key="i"
        @click="setIndex(i)"
        :class="['header-tab', tabIndex === i ? 'active' : '']"
        :style="CssVars"
      >
        <TyphographyComponent textType="H4" :isUpper="true" :text="el.title" />
      </li>
    </ul>
    <div
      v-for="(el, i) in infoList"
      :key="i"
      class="body-tab"
      v-show="tabIndex === i"
    >
      <!-- <img
            class="img-resp"
            :src="require(`@/src/img/main/tabs/${el.image}.png`)"
            alt="lorem ipsum dates dates"
          /> -->
      <TyphographyComponent textType="BODY" :text="el.text" />
      <div v-if="el.list" class="body-tab-content">
        <ul class="body-tab-list">
          <li v-for="(item, i) in el.list" :key="i">
            <TyphographyComponent textType="SMALL" :text="item" color="#d2fd" />
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import TyphographyComponent from "./TyphographyComponent.vue";
export default {
  components: { TyphographyComponent },
  name: "TabCompoent",
  props: {
    msg: String,
    infoList: Array,
    fullWidth: { type: Boolean, default: false },
  },
  data() {
    return {
      tabIndex: 0,
    };
  },
  methods: {
    // setting index
    setIndex(index) {
      console.log(this.fullWidth);
      this.tabIndex = index;
    },
  },
  computed: {
    CssVars() {
      return {
        tabComponentWidth: this.fullWidth ? "100%" : "800px",
        headerTabsWidth: this.infoList.length,
      };
    },
  },
};
</script>

<style scoped lang="scss">
.tab-component {
  width: var(--tabComponentWidth);
  max-width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  .header-tabs {
    display: flex;
    align-items: center;
    justify-content: center;
    list-style: none;
    .header-tab {
      padding: 15px;
      width: calc(100% / var(--tabComponentWidth));
      border: solid red 1px;
      &.active {
        font-size: 20px;
      }
    }
  }
}
</style>
