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
          :color="tabIndex === i ? '#FFCDB2' : '#FFB4A2'"
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
      <img
        v-if="el.image"
        class="img-resp"
        :src="require(`/src/img/main/tabs/${el.image}.png`)"
        alt="lorem ipsum dates dates"
      />
      <TyphographyComponent textType="BODY" color="#6D6875" :text="el.text" />
      <div v-if="el.list" class="body-tab-content">
        <ul class="body-tab-list">
          <li v-for="(item, i) in el.list" :key="i">
            <img
              v-if="item.image"
              class="img-resp"
              :src="require(`/src/img/main/tabs/${item.image}.png`)"
              alt="lorem ipsum dates dates"
            />
            <TyphographyComponent
              textType="SMALL"
              :text="item.text"
              color="#6D6875"
            />
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
  img {
    width: 50px;
  }
  .header-tabs {
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: center;
    list-style: none;
    .header-tab {
      position: relative;
      padding: 0 15px;
      &::after {
        content: "";
        position: absolute;
        z-index: 1;
        bottom: 0;
        width: 90%;
        height: 0;
        background: rgba(#b5838d, 0.5);
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        transition: height 250ms ease, width 300ms, border-radius 200ms 200ms;
      }
      &:hover {
        &::after {
          height: 10px;
        }
      }
      &:not(:first-child, :last-child) {
        margin: 0 5px;
      }
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #6d6875;
      cursor: pointer;
      &.active {
        h4 {
          position: relative;
          z-index: 2;
        }
        &::after {
          width: 100%;
          height: 100%;
          border-radius: 0;
        }
        font-size: 20px;
        cursor: unset;
      }
    }
  }
  .body-tab {
    background: rgba(#b5838d, 0.2);
    width: 100%;
    height: 100%;
    box-shadow: 2px 2px 10px rgba(#000000, 0.2);
    margin-top: 5px;
    padding: 15px;
    transition: all 250ms ease;
    ul {
      display: flex;
      li {
        padding: 15px 0;
        list-style: none;
      }
    }
  }
}
</style>
