<template>
  <div class="tab-component">
    <div class="course-info">
      <ul class="info-list">
        <li
          v-for="(el, i) in infoList"
          :key="i"
          @click="getIndexCourse(i)"
          :class="['info-item', tabIndex === i ? 'active' : '']"
        >
          <TyphographyComponent
            textType="H4"
            :isUpper="true"
            :text="el.title"
          />
        </li>
      </ul>
      <div
        v-for="(el, i) in infoList"
        :key="i"
        class="info-content"
        v-if="tabIndex === i"
      >
        <!-- <img
            class="img-resp"
            :src="require(`@/src/img/main/tabs/${el.image}.png`)"
            alt="lorem ipsum dates dates"
          /> -->
        <TyphographyComponent textType="BODY" :text="el.text" />
        <div class="content">
          <ul v-if="el.list" class="content-list">
            <li v-for="(item, i) in el.list" :key="i">
              <TyphographyComponent
                textType="SMALL"
                :text="item"
                color="#d2fd"
              />
            </li>
          </ul>
        </div>
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
  },
  data() {
    return {
      tabIndex: 0,
      menuList: [
        {
          title: "ciao",
        },
        {
          title: "ciao2",
        },
      ],
    };
  },
  methods: {
    // setting index
    setIndex(index) {
      this.tabIndex = index;
      console.log(index);
      console.log(this.tabIndex);
    },
    getIndexCourse(index) {
      this.tabIndex = index;
    },
  },
};
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
