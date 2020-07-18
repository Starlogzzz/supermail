<template>
    <ul class="lefthand">
        <li @click="lione">推荐分类</li>
        <li @click="litwo">国际名牌</li>
        <li>新品馆</li>
        <li>潮流馆</li>
        <li>淑女馆</li>
        <li>国风馆</li>
        <li>通勤馆</li>
        <li>情侣装</li>
        <li>泫雅风</li>
        <li>闺蜜套装</li>
    </ul>
</template>

<script>
export default {
    name: "LeftHand",
    methods:{
        lione(){
            console.log("wwwwwwwwww");
            this.$emit("changepage1", 1)
        },
        litwo(){
            this.$emit("changepage2", 2)
        },
    }
}
</script>

<style>
    .lefthand li{
        width: 100px;
        height: 50px;
        text-align: center;
        line-height: 50px;
        color: #fff;
        background-color: rgb(225,6,1);
        border: 1px solid #fff;
    }
</style>