<template>
  <div id="app">
    <TabCompoent msg="Welcome to Your Vue.js App" :infoList="infoList" />
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
          title: "Lorem ipsum dolor",
          list: [
            {
              image: "h12-tabs-icon-1",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-2",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-3",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-4",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-5",
              text: "We enrich throught learning.",
            },
          ],
        },
        {
          title: "Degree",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          image: "h12-tabs-icon-2",
        },
        {
          title: "Lorem ipsum",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          list: [
            {
              text: "We enrich throught learning.",
            },
            {
              text: "We enrich throught learning.",
            },
            {
              text: "We enrich throught learning.",
            },
            {
              text: "We enrich throught learning.",
            },
          ],
          image: "h12-tabs-icon-3",
        },
        {
          title: "Lorem ipsum",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          list: [
            {
              image: "h12-tabs-icon-1",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-2",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-3",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-4",
              text: "We enrich throught learning.",
            },
            {
              image: "h12-tabs-icon-5",
              text: "We enrich throught learning.",
            },
          ],
        },
        {
          title: "Lorem",
          text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta! Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, iusto? Nostrum, ducimus similique amet hic sunt at velit totam deserunt perspiciatis, repellendus minus suscipit tempore ullam numquam blanditiis cum dicta!",
          list: [
            {
              text: "We enrich throught learning.",
            },
            {
              text: "We enrich throught learning.",
            },
            {
              text: "We enrich throught learning.",
            },
            {
              text: "We enrich throught learning.",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss">
*,
*::before,
*::after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  background: #ddd;
  /* background: #333; */
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
