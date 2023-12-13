<script>
export default {
    data(){

    },
}
</script>
<template>
        <div class="header">
        <RouterLink to="/BackManage1" class="link">問卷</RouterLink>
        <RouterLink to="/BackManage2" class="link">題目</RouterLink>
        <RouterLink to="/BackManage3" class="link">問卷回饋</RouterLink>
        <RouterLink to="/BackManage4" class="link">BackManage4</RouterLink>
    </div>
    <div class="content">
        <span>問卷名稱：</span>
        <input type="text" name="" id="">
        <span>問卷說明：</span>
        <textarea name="" id="" cols="30" rows="10"></textarea>
        <span>開始時間：</span>
        <input type="date" name="" id="">
        <span>結束時間：</span>
        <input type="date" name="" id="">
    </div>
    <div class="footer">
        <button type="submit"><RouterLink :to="`/Back`" class="rounterItem">取消</RouterLink></button>
        <!-- <button type="submit"><RouterLink :to="`/FrontInside`" class="rounterItem">下一步</RouterLink></button> -->
    </div>

</template>

<style scoped lang="scss">
.header{
    width: 90vw;
    height: 8vh;
    display: flex;
    justify-content: center;
    .link{
        text-decoration: none;
        margin-left: 10px;
    }
}
</style>