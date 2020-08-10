<template>
  <div id="profile">
    <nav-bar class="home-nav">
      <div slot="center">个人中心</div>
    </nav-bar>

    <div class="container">
      <div style="grid-area: person">
        <div class="avatar">
          <div class="img" style="grid-area: img">
            <img src="../../../public/avater.jpg" alt="" title="头像">
          </div>
          <div class="personid" style="grid-area: myid">芜湖大司马</div>
        </div>
      </div>
      <div class="sonbox" style="grid-area: payment">
        <img class="icon" src="../../../public/pay.svg" alt="">
        <span>待付款</span>
      </div>
      <div class="sonbox" style="grid-area: deliver">
        <img class="icon" src="../../../public/send.svg" alt="">
        <span>待发货</span>
      </div>
      <div class="sonbox" style="grid-area: receiving">
        <img class="icon" src="../../../public/deliver.svg" alt="">
        <span>待收货</span>
      </div>
      <div class="sonbox" style="grid-area: evaluate">
        <img class="icon" src="../../../public/comment.svg" alt="">
        <span>评价</span>
      </div>
      <div class="sonbox" style="grid-area: aftersale">
        <img class="icon" src="../../../public/refund.svg" alt="">
        <span>售后/退款</span>
      </div>
      <div class="sonbox" style="grid-area: mygoods">
        <img class="icon" src="../../../public/form.svg" alt="">
        <span>我的订单</span>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
export default {
  name: "Profile",
  components: {
    NavBar,
  }
};
</script>
  
<style scoped>
.home-nav {
  background-color: var(--color-tint);
  color: #fff;

  /* position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9; */
}
.container {
  display: grid;
  width: 100%;
  height: 60vh;

  /* --button-width: 100% / 3;
            --button-height: 80px; */
  grid-template-areas:
    "person person person"
    "person person person"
    "payment deliver receiving"
    "evaluate aftersale mygoods";
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(4, 1fr);
  place-items: center center;
}

.avatar{
  display: grid;
  width: 160px;
  height: 160px;
  grid-template-areas: 'img img img'
  'img img img'
  'img img img'
  'myid myid myid';
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(4, 1fr);
  place-items: center center;
}
.personid{
  font-size: 18px;
  font-weight: 900;
}

.img{
  display: flex;
  justify-content: center;
  gap: 5px;
}
.img img{
  width: 70%;
  height: 100%;
  border: 1px solid #ccc;
  border-radius: 50%;

}

.icon{
  width: 40%;
}
.sonbox{
  display: grid;
  place-items: center center;
  gap: 10px;
}
</style>