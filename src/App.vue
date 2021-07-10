<template>
  <div id="app">
    <TabCompoent
      :fullWidth="true"
      msg="Welcome to Your Vue.js App"
      :infoList="infoList"
    />
  </div>
</template>

<script>
import TabCompoent from "./components/TabCompoent.vue";

export default {
  name: "App",
  components: {
    TabCompoent,
  },
  data() {
    return {
      infoList: [
        {
          title: "Learn Possibilities",
          list: [
            "We enrich throught learning.",
            "Maximizing potential through individual attention.",
            "The trusted name for specialized training.",
            "People teach. People learn. This in whewe they connect.",
          ],
          image: "h12-tabs-icon-1",
        },
        {
          title: "Degree",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          image: "h12-tabs-icon-2",
        },
        {
          title: "Achievements",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          list: [
            "We enrich throught learning.",
            "Oke potential through individual attention.",
            "The trusted name for specialized training.",
            "People teach. People learn. This in whewe they connect.",
          ],
          image: "h12-tabs-icon-3",
        },
        {
          title: "Managment",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          list: [
            "We enrich throught learning.",
            "Maximizing potential through individual attention.",
            "The trusted name for specialized training.",
            "People teach. People learn. This in whewe they connect.",
          ],
          image: "h12-tabs-icon-4",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
