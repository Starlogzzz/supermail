<template>
  <div class="bottom-bar">
    <div class="check-content">
      <check-buttom :is-checked="isSelectAll" class="check-button" @click.native="checkClick" />
      <span>全选</span>
    </div>

    <div class="price">合计: {{totalPrice}}</div>

    <div class="calculate" @click="calcClick">去计算: {{checkLength}}</div>
  </div>
</template>

<script>
import CheckButtom from "components/content/checkButtom/CheckButtom";
import { mapGetters } from "vuex";

export default {
  name: "CarBottomBar",
  components: {
    CheckButtom
  },
  computed: {
    ...mapGetters(["cartList"]),
    totalPrice() {
      return (
        "￥" +
        this.$store.getters.cartList
          .filter(item => {
            return item.checked;
          })
          .reduce((pre, item) => {
            return pre + item.price * item.count;
          }, 0)
          .toFixed(2)
      );
    },
    checkLength() {
      return this.$store.getters.cartList.filter(item => item.checked).length;
    },
    isSelectAll() {
      if (this.cartList.length === 0) return false;
      return !this.cartList.find(item => !item.checked);
    }
  },
  methods: {
    checkClick() {
      if (this.isSelectAll) {
        this.cartList.forEach(item => {
          item.checked = false;
        });
      } else {
        this.cartList.forEach(item => {
          item.checked = true;
        });
      }
    },
    calcClick() {
      if (!this.isSelectAll) {
        this.$toast.show("请选择要购买的商品", 1500);
      }
    }
  }
};
</script>

<style scoped>
.bottom-bar {
  display: flex;
  height: 40px;
  background-color: #eee;
  position: relative;
  line-height: 40px;
}

.check-content {
  display: flex;
  align-items: center;
  margin-left: 10px;
}

.check-button {
  width: 20px;
  height: 20px;
  line-height: 20px;
  margin-right: 10px;
}

.price {
  margin-left: 10px;
}

.calculate {
  width: 90px;
  margin-left: 110px;
  background-color: red;
  color: #fff;
  text-align: center;
}
</style>