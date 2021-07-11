<template>
  <div class="tab-component" :style="TabComponentStyles">
    <ul class="header-tabs" :style="HeaderTabStyles">
      <li
        v-for="(el, i) in infoList"
        :key="i"
        @click="setIndex(i)"
        :class="['header-tab', tabIndex === i ? 'active' : '']"
        :style="TabItemsStyles"
      >
        <TyphographyComponent
          :color="tabIndex === i ? '#B2C9AB' : '#92B6B1'"
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
      <TyphographyComponent textType="BODY" color="#666A86" :text="el.text" />
      <div v-if="el.list" class="body-tab-content">
        <ul class="body-tab-list" :style="TabListStyles">
          <li v-for="(item, i) in el.list" :key="i" :style="TabListItemStyles">
            <img
              v-if="item.image"
              class="img-resp"
              :src="require(`/src/img/main/tabs/${item.image}.png`)"
              alt="lorem ipsum dates dates"
            />
            <TyphographyComponent
              textType="SMALL"
              :text="item.text"
              color="#666A86"
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
    TabItemsStyles() {
      return {
        width: innerWidth <= 768 ? "100%" : 100 / this.infoList.length + "%",
        marginRight: innerWidth <= 768 && "0",
      };
    },
    HeaderTabStyles() {
      return {
        flexDirection: innerWidth <= 768 ? "column" : "row",
      };
    },
    TabListItemStyles() {
      return {
        width:
          innerWidth <= 768
            ? "100%"
            : this.infoList[this.tabIndex].list
            ? 100 / this.infoList[this.tabIndex].list.length + "%"
            : "100%",
      };
    },
    TabListStyles() {
      return {
        flexDirection: innerWidth <= 768 ? "column" : "row",
      };
    },
  },
};
</script>

<style scoped lang="scss">
.tab-component {
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
        background: rgba(#788aa3, 0.5);
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        transition: height 250ms ease, width 300ms, border-radius 200ms 200ms;
      }
      &:hover {
        &::after {
          height: 10px;
        }
      }
      &:not(:last-child) {
        margin-right: 5px;
      }
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #666a86;
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
    background: rgba(#788aa3, 0.2);
    width: 100%;
    height: 100%;
    box-shadow: 2px 2px 10px rgba(#666a86, 0.2);
    margin-top: 5px;
    padding: 15px;
    transition: all 250ms ease;
    ul {
      display: flex;
      li {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 15px 0;
        list-style: none;
        img {
          margin-bottom: 15px;
        }
      }
    }
  }
}
</style>
