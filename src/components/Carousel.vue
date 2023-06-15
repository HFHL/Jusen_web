<script setup>
import { ref } from 'vue';
import SubCard from './SubCard.vue';
const carouselRef = ref(null);
const handleHover = (index) => { carouselRef.value.setActiveItem(index); };
const activeIndex1 = ref(0);

</script>
<template>
    <div class="card">
        <el-carousel :autoplay="false" height="auto" ref="carouselRef" :active-index="activeIndex1" arrow="never"
            indicator-position="none">
            <el-carousel-item style="height: 300px;">
                <h3 text="2xl" justify="center">1</h3>
            </el-carousel-item>
            <el-carousel-item style="height: 300px;">
                <h3 text="2xl" justify="center">2</h3>
            </el-carousel-item>
            <el-carousel-item style="height: 300px;">
                <h3 text="2xl" justify="center">3</h3>
            </el-carousel-item>
        </el-carousel>
        <div class="indicator">
            <el-row gutter="50">
                <el-col :span="8">
                    <div class="indi-item" @mouseover="handleHover(0)">
                        <SubCard title="社群新环境" content="群聊sop、群内专属AI、增长裂变溯源、广告检测sop、群成员活跃检测...覆盖大量场景玩法！维护开发顾客！" />
                    </div>
                </el-col>
                <el-col :span="8">
                    <div class="indi-item" @mouseover="handleHover(1)">
                        <SubCard title="直播新玩法" content="专研美业，审美在线。更多直播间内互动玩法！每一场直播，每一个主题，都是为了成交！" />
                    </div>
                </el-col>
                <el-col :span="8">
                    <div class="indi-item" @mouseover="handleHover(2)">
                        <SubCard title="数据更直观" content="线上展示销售数据，让用户行为和商品信息一览无余，实时可以追踪跟单，转化成交就在这一步！" />
                    </div>
                </el-col>
            </el-row>



        </div>
    </div>
</template>
<style scoped>
.indicator {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 100;
    height: auto;
}

.indi-item {
    flex: 0.9;

    height: auto;
    margin-right: 10px;
}


.card {
    /* background-color: #475669; */
    height: auto;

    margin: 0 auto;
}
</style>
