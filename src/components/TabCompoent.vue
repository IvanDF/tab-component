<template>
  <div class="tab-component" :style="TabComponentStyles">
    <ul class="header-tabs">
      <li
        v-for="(el, i) in infoList"
        :key="i"
        @click="setIndex(i)"
        :class="['header-tab', tabIndex === i ? 'active' : '']"
        :style="HeaderTabStyles"
      >
        <TyphographyComponent
          :color="tabIndex === i ? '#fff' : '#333'"
          textType="H4"
          :text="el.title"
        />
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
            <TyphographyComponent textType="SMALL" :text="item" color="#200" />
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
      this.tabIndex = index;
    },
  },
  computed: {
    TabComponentStyles() {
      return {
        width: this.fullWidth ? "100%" : "800px",
      };
    },
    HeaderTabStyles() {
      return {
        width: 100 / this.infoList.length + "%",
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
    width: 100%;
    align-items: center;
    justify-content: center;
    list-style: none;
    .header-tab {
      padding: 0 15px;
      &:not(:first-child, :last-child) {
        margin: 0 5px;
      }
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: gainsboro;
      cursor: pointer;
      &.active {
        background: gray;
        font-size: 20px;
        cursor: unset;
      }
    }
  }
  .body-tab {
    width: 100%;
    height: 100%;
    box-shadow: 2px 2px 10px rgba(#000000, 0.2);
    margin-top: 5px;
    padding: 15px;
    li {
      list-style: none;
    }
  }
}
</style>
