<script setup>
import { ref } from 'vue'
import SubCard from './components/SubCard.vue'
import ContactForm from './components/ContactForm.vue';
import Footer from './components/Footer.vue';
import FloatingWindow from './components/FloatingWindow.vue';
import Carousel from './components/Carousel.vue';
import HeadNav from './components/HeadNav.vue';
import Carousel_blackback from './components/Carousel_blackback.vue';
import SubCardstatic from './components/SubCardstatic.vue';
import point from './components/point.vue';

import {
    Check,
    Delete,
    Edit,
    Message,
    Search,
    Star,
} from '@element-plus/icons-vue'


const activeIndex = ref('1')
const handleSelect = (key, keyPath) => {
    console.log(key, keyPath)
}

const carouselRef = ref(null);
const handleHover = (index) => { carouselRef.value.setActiveItem(index); };


// 轮播图片列表
const carouselList = ref([
    {
        img_url: '../src/assets/croimglist/幻灯片1.png',
    },
    {
        img_url: '../src/assets/croimglist/幻灯片2.png',
    },
    {
        img_url: '../src/assets/croimglist/幻灯片3.png',
    },
    {
        img_url: '../src/assets/croimglist/幻灯片4.png',
    }
])

</script>

<template>
    <FloatingWindow style="z-index: 100;"></FloatingWindow>
    <div class="flex">
        <!-- 导航栏 -->
        <HeadNav></HeadNav>
        
        <div class="main-display">
            <el-row class=" main-back" >
                <el-col :span="9">
                    <div class="left-show">
                        <span>更懂私域运营的服务商</span>
                        <span>维护好私域客户，发挥更多私域价值</span>
                        <div class="two-button" style="margin-top: 25px;">
                            <el-button style="height: 50px;width: 120px;" type="primary" size="large" round>免费试用</el-button>
                            <el-button  style="height: 50px;width: 120px;" size="large" round>了解详情</el-button>
                        </div>
                        
                    </div>
                </el-col>
                <el-col :span="14">
                    <div class="right-show">
                        <el-carousel height="auto" indicator-position="none" >
                            <!-- <el-carousel-item  style="height: 798px;width: 100%;margin: auto auto;border-radius: 0px;" v-for="item in 4" :key="item">   
                                    <h3  text="2xl" justify="center">{{ item }}</h3>
                            </el-carousel-item> -->
                            <!-- 轮播图显示轮播图列表里的图片 -->
                            <el-carousel-item style="height: 710px;width: 100%;" v-for="(item, index) in carouselList" :key="index">
                                <img :src="item.img_url" alt="" style="width: 850px;border-radius: 25px;background-size: cover;object-fit: cover;margin-top: 80px; ">
                            </el-carousel-item>
                        </el-carousel>
                    </div>
                </el-col>
            </el-row>

            <div class="sub-show">
                <div class="row-line" style="height:12px;"></div>
                <span class="title2">新前沿私域直播 找聚森 </span>
                <div class="row-line" style="height: 15px;"></div>
                <!-- 换行 -->
                <br />
                <span class="title1">新的社群触达、新的直播玩法，打造服务客户的私域直播</span>

                <p>
                    社群数据接通电商服务，社群维护接入AI客服，轻松打通数据壁垒，<br>全流程陪跑SOP，解放咨询师，手把手教会品牌社群运营。打造极致的客户转化与客户维护！
                </p>
                <div class="row-line" style="height: 17px;"></div>
                <!-- 轮播图2 -->

                <Carousel></Carousel>

            </div>

            <div class="dark">
                <div class="sub-show">
                    <div class="row-line" style="height:12px;"></div>
                    <span class="title2">企业专属AI 聚森一键部署</span>
                    <div class="row-line" style="height: 15px;"></div>
                    <!-- 换行 -->
                    <br />
                    <span class="title1">低成本获得关于企业的24小时专属客服-AI</span>

                    <p>快速喂养只属于企业的AI助手，并且可以直接部署到社群，<br>释放咨询师的生产力！表单和电话，同样不落下！</p>
                    <div class="row-line" style="height: 17px;"></div>
                    <!-- 轮播图2 -->
                    <Carousel_blackback></Carousel_blackback>

                </div>
            </div>

            <!-- block -->
            <div class="row-line"></div>
            <el-row>
                <el-col :span="24">
                    <h2 style="margin-left: 64px;">
                        保障和陪跑
                    </h2>
                    <h1 style="margin-left: 64px;margin-top: -15px;">为私域提供更可靠、前沿、安全的产品和服务</h1>
                    <!-- 水平卡片列表，展示服务 -->
                    <div class="server-card-list">
                        <div class="server-card"></div>
                        <div class="server-card"></div>
                        <div class="server-card"></div>
                        <div class="server-card"></div>
                        <div class="server-card"></div>
                    </div>


                </el-col>
            </el-row>

            <el-row style="margin-top: 70px;">
                <div style="width: 100vw;background-color: black;">
                    <div style="width: 80%;margin-left: 60px ">
                        <el-col :span="24" style="background-color: black;" class="dark">
                            <SubCardstatic style="" title="聚森私域与您一起做好私域" content="汇集可能，创造可能" />
                        </el-col>
                    </div>
                </div>
            </el-row>

            <el-row style="margin-top: -20px;">
                <el-col :span="24" style="background-color: black;" class="dark">
                    <ContactForm />
                </el-col>
            </el-row>
            <Footer></Footer>
        </div>
    </div>
</template>

<style scoped>

img::after {  content: "";  position: absolute;  top: 0;  bottom: 0;  left: 200px; /* 设置叠加层的宽度与图片宽度一致 */  right: 0;  background-image: inherit;  background-size: cover;  filter: blur(10px); /* 添加模糊效果 */}

.el-carousel__container {  border-radius: 10px;  overflow: hidden;}

.main-back {
    /* 背景图片 */
    background-image: url(../src/assets/2-1/1-1.gif);
    /* 背景拉伸 */
    background-size: cover;
    /* 背景图片底部虚化 */
    /* filter: blur(10px); */
}
/* .shadow {
    background: #e0e0e0;
box-shadow:  50px 50px 100px #a4a4a4,
             -50px -50px 100px #ffffff;
} */

.server-card {
    height: 150px;
    width: 200px;
    background-color: #0c60c1;
}

.server-card-list {
    width: 80%;
    height: 150px;
    
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.dark {
    color: #ffffff;
    width: 100%;
    background-color: #000;
}

.full-width {
    width: 100%;
    /* 居中 */
    margin: 0 auto;
    background-color: #000;
    /* 文字向左靠齐 */
    text-align: left;
}

/* full-width里是flex，纵向排列，要求里面的h标签左靠齐 */
.full-width h3 {
    text-align: left;
}

.scor-content {
    background-color: #000;
    width: 90%;
}

/* 指示器按钮 */
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
    height: auto;
    margin: 0 auto;
}

.title1 {
    font-size: 28px;
    /* 左对齐 */
    text-align: left;
}

.row-line {
    width: 100%;
    height: 20px;
}

.title2 {
    font-size: 19px;
    /* 左对齐 */
    text-align: left;
}

.sub-show {
    width: 90%;
    /* flex下，居中 */
    margin:70px auto;

    

}

.two-button {
    width: 90%;
    height: 100px;
    
    display: flex;
    flex-direction: row;
    /* 居中对齐设置间距 */
    justify-content: center;
    /* 设置到中轴的距离 */
    align-items: center;
}

/* two-button里的第一个button */
/* .two-button el-button:nth-child(1) {
    margin-right: 20px;
}

.two-button el-button:nth-child(2) {
    margin-left: -20px;
} */

main-display {
    margin-top: 20px;
}

.left-show {
    width: 100%;
    height: 720px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

/* left-show里的第一个span */
.left-show span:nth-child(1) {
    font-size: 45px;
    font-weight: bold;
    color: #2c3e50;
    /* 字体 */
    font-family: 'Helvetica Neue', Helvetica, 'PingFang SC', 'Hiragino Sans GB',
        'Microsoft YaHei', '微软雅黑', Arial, sans-serif;
}

/* left-show里的第二个span */
.left-show span:nth-child(2) {
    margin-top: 10px;
    font-size: 25px;
    font-weight: 100;
    color: #2c3e50;
}

.right-show {
    width: 100%;
    height: 720px;
}

.flex {
    display: flex;
    flex-direction: column;
    height: 100vh;

}

.flex-grow {
    flex-grow: 1;
}

.el-row {
    margin-bottom: 20px;
}

.el-row:last-child {
    margin-bottom: 0;
}

.el-col {
    border-radius: 4px;
}

.grid-content {
    border-radius: 4px;
    min-height: 36px;
    
}

/* 轮播图 */
/* .el-carousel__item h3 {
    display: flex;
    color: #475669;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
} */

/* .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
    background-color: #d3dce6;
} */
</style>
