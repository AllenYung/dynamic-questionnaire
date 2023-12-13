<script>
import { RouterLink, RouterView } from 'vue-router'
export default{
    data(){
        return{

        }
    },
    components:{
        RouterLink,
    }
}
</script>
<template>
<div class="headerShow">
    <RouterLink to="/" class="link">Home</RouterLink>
    <RouterLink to="/about" class="link">About</RouterLink>
    <RouterLink to="/Front" class="link">前台列表頁</RouterLink>
    <RouterLink to="/FrontInside" class="link">問卷填寫頁</RouterLink>
    <RouterLink to="/FrontChack" class="link">填寫確認頁</RouterLink>
    <RouterLink to="/FrontStatistics" class="link">前台統計</RouterLink>
    <RouterLink to="/Back" class="link">Back</RouterLink>
    <RouterLink to="/BackManage1" class="link">問卷</RouterLink>
    <RouterLink to="/BackManage2" class="link">題目</RouterLink>
    <RouterLink to="/BackManage3" class="link">問卷回饋</RouterLink>
    <RouterLink to="/BackManage4" class="link">問卷確認</RouterLink>
    <RouterLink to="/BackStatistics" class="link">統計</RouterLink>
</div>
</template>

<style scoped lang="scss">
.headerShow{
    width: 100%;
    height: 100%;
    background-color: rgb(192, 223, 234);
    display: flex;
    flex-wrap: wrap;
}
.link{
    text-decoration: none;
    font-size: 35px;
    margin: 20px;
    color: palevioletred;
}
</style>