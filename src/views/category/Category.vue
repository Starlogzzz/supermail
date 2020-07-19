<template>
  <div class="wrapper">
    <left-hand class="lefthand" @tabClick="changepage"></left-hand>
    <classification class="righthand" v-if="this.page === 0"></classification>
    <classification2 class="righthand" v-if="this.page === 1"></classification2>
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
      page: 0
    };
  },
  methods:{
    changepage: function(data){
      this.page = data;
      console.log(this.page);   
    }
  }
};
</script>
  
<style scoped>

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