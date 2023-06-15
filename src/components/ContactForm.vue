<script setup>

</script>
<template>
    <el-row>
        <el-col :span="10">
            <div class="form">
                <h1>与我们联系</h1>
                <p>将有专人为您提供经营建议、解决方案、专业答疑等</p>
                <!-- elment输入框，提示输入手机号 -->
                <div style="width: 100%;margin: 0 auto;">
                    <el-input size="large" placeholder="请输入手机号" suffix-icon="el-icon-phone"></el-input>
                </div>
                <el-button type="primary" style="margin-top: 20px;">Primary</el-button>
                
            </div>
        </el-col>
        <el-col :span="14">
            <div class="img">
                
            </div>
        </el-col>

    </el-row>
</template>
<style scoped>
.img {
    width: 80%;
    height: 80%;
    margin: auto auto;
    background-color: azure;
}

.form {
    width: 80%;
    margin: 12px auto 30px auto;
    display: flex;
    flex-direction: column;
    color: #fff;
}

.form p {
    margin-top: -10px;
    font-size: 14px;
    
}
</style>
