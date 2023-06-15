<script setup>
import { ref } from 'vue';
import point from '../components/point.vue'
// 生成时传值
const props = defineProps({
    title: String,
    content: String,
})





</script>
<template>
    <div class="box">
        <h1 class="textstyle">{{props.title}}</h1>
        <p class="textstyle">{{ props.content }}</p>
        <el-row>
            <el-col :span="6">
                <i class="textstyle">如何获得客户 </i>
            </el-col>
            <el-col :span="12">
                <point style="width: 30px;height: 24px;"></point>
            </el-col>
        </el-row>
    </div>
</template>
<style scoped>
.box {
    display: flex;
    flex-direction: column;
    margin: 30px auto;
}

.box .textstyle{
    color: #979393;
}

/* 鼠标悬浮box，改变h1 和 p标签字体颜色,*/
.box:hover .textstyle{
    cursor: pointer;
    color: rgb(236, 233, 230);
    /* 过渡效果 */
    transition: all 0.5s;
}


</style>