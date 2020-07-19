<template>
    <ul class="lefthand">
        <li v-for="(item,index) in list" :key="'lh'+index" :class="{active: index === currentIndex}" @click="itemClick(index)">{{item}}</li>
    </ul>
</template>

<script>
export default {
    name: "LeftHand",
    data(){
        return {
            list: ["推荐分类","国际名牌","新品馆","潮流馆","淑女馆","国风馆","通勤馆","情侣装","泫雅风","闺蜜套装"],
            currentIndex: 0
        }
    },
    methods:{
        lione(){
            console.log("wwwwwwwwww");
            this.$emit("changepage1", 1)
        },
        litwo(){
            this.$emit("changepage2", 2)
        },
        itemClick(index) {
            //console.log(index);
            this.currentIndex = index;
            // console.log(index === this.currentIndex);
            this.$emit("tabClick", index);
        }
    }
}
</script>

<style scoped>
    .lefthand li{
        width: 100px;
        height: 50px;
        text-align: center;
        line-height: 50px;
        color: #fff;
        background-color: rgb(225,6,1);
        border: 1px solid #fff;
    }

    .lefthand .active{
        background-color: seashell;
        color: #000;
    }
</style>