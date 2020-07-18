<template>
  <div class="wrapper">
    <left-hand class="lefthand" @changepage1="changepage" @changepage2="changepage"></left-hand>
    <classification class="righthand" v-if="this.page === 1"></classification>
    <classification2 class="righthand" v-if="this.page === 2"></classification2>
  </div>
</template>

<script>
// import BScroll from "better-scroll";
import LeftHand from "./childComps/LeftHand"
import Classification from "./childComps/Classification"
import Classification2 from "./childComps/Classification2"

export default {
  name: "Category",
  components: {
    LeftHand,
    Classification,
    Classification2
  },
  data() {
    return {
      scroll: null,
      page: null
    };
  },
  methods:{
    changepage: function(data){
      this.page = data;
      console.log(this.page);   
    }
  },
  // created() {},
  // mounted() {
  //   this.scroll = new BScroll(document.querySelector(".wrapper"), {
  //     probeType: 3,
  //     pullUpLoad: true
  //   });

  //   this.scroll.on("scroll", position => {
  //     //console.log(position);
  //   });

  //   this.scroll.on("pullingUp", () => {
  //     console.log("上拉加载更多");
  //   });
  // }
};
</script>
  
<style scoped>
/* .wrapper {
  height: 150px;
  background-color: aqua;
  overflow: hidden;
} */

.lefthand{
  position: relative;
  left: 0;
  top: 0;
}
.righthand{
  position: absolute;
  right: -4px;
  top: 0;
}
</style>